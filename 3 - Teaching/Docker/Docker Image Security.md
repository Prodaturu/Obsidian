**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #image #security

**Links / Tags:**
- **Relevance Links:**
	- Container Security %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Docker Image Security

> Protecting the software supply chain and reducing vulnerabilities before a container starts.

## Key Ideas

- Use trusted sources, pin versions or digests, and rebuild regularly with patched bases.
- Scan images and generate or retain software bills of materials where appropriate.
- Do not bake credentials into build arguments, copied files, environment defaults, or layers.
- Use multi-stage builds and a non-root runtime user, then sign or attest release artifacts when the pipeline supports it.

## Deep Dive
## Supply-Chain Questions

For every production image, be able to answer: Who built it? From which source revision? Which base and dependencies entered it? Was it tested and scanned? Has its digest changed? Can the result be rebuilt and patched?

### Secrets during build

`ARG`, `ENV`, copied credentials, and shell command text can appear in metadata, cache, or layers. Use BuildKit secret mounts:

```dockerfile
# syntax=docker/dockerfile:1
RUN --mount=type=secret,id=npmrc,target=/root/.npmrc \
    npm ci
```

```bash
docker build --secret id=npmrc,src="$HOME/.npmrc" -t app:test .
```

The command avoids persisting the secret in the resulting layer, but the build process and dependency source must still be trusted.

### Vulnerabilities

A scanner reports known issues in detectable components; it cannot prove absence of vulnerabilities or unsafe application logic. Prioritise reachable/exploitable issues, runtime exposure, fix availability, and base-image maintenance. Rebuild after dependency/base fixes—the old immutable image does not patch itself.

## Practical Check

- Explain **Docker Image Security** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it

- [[Docker Image Size and Security]] %% Conceptual overlap; intentionally reciprocal %%

---
# References
- [Docker documentation](https://docs.docker.com/)
