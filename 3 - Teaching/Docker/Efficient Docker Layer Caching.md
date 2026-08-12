**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #efficient #layer #caching

**Links / Tags:**
- **Relevance Links:**
	- Building Container Images %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Efficient Docker Layer Caching

> Structuring builds so unchanged expensive steps can reuse cached results.

## Key Ideas

- Copy dependency manifests before application source, install dependencies, then copy frequently changing code.
- Combine cache-aware ordering with a small `.dockerignore` file.
- Use BuildKit cache mounts for package-manager caches when appropriate.
- Do not blindly combine every instruction: readable, reusable layers often outperform one giant layer.

## Deep Dive
## Cache Invalidation

BuildKit can reuse an instruction only when the instruction and relevant inputs still match. Once an early layer changes, dependent later work often rebuilds.

```mermaid
flowchart LR
    A[Base image] --> B[Copy lockfiles]
    B --> C[Install dependencies]
    C --> D[Copy changing source]
    D --> E[Compile/test]
```

This order is deliberate. Source changes frequently; dependency manifests change less often. Copying the entire repository before dependency installation invalidates the expensive install step on every source edit.

### Cache types

- **Layer cache:** reuses output from Dockerfile instructions.
- **Cache mount:** preserves package-manager download caches without placing them in the final layer.
- **External cache:** exports/imports build cache for CI or other builders.

```dockerfile
RUN --mount=type=cache,target=/root/.cache/pip \
    pip install --requirement requirements.txt
```

`--no-cache` reruns Dockerfile steps but does not itself pull a newer base; combine with `--pull` when testing a fully fresh build. Optimise after correctness: a fast cache must not conceal missing dependency locks or accidental network dependence.

## Practical Check

- Explain **Efficient Docker Layer Caching** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it


- [[Docker in Continuous Integration]] %% Conceptual overlap; intentionally reciprocal %%

---
# References
- [Docker documentation](https://docs.docker.com/)
