**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #ephemeral #container #filesystem

**Links / Tags:**
- **Relevance Links:**
	- Docker Data Persistence %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Ephemeral Container Filesystem

> The default writable layer exists only as part of one container and should be treated as temporary.

## Key Ideas

- Writes survive a stop/start of the same container but not removal of that container.
- The writable layer is appropriate for caches and temporary files, not irreplaceable state.
- Recreating a container from the same image starts with a fresh writable layer.
- Externalise databases, uploads, and durable configuration through mounts or managed services.

## Deep Dive
## What Actually Persists

The writable layer belongs to the container object, not to the running process. Therefore:

- stopping and starting the **same** container retains the layer;
- removing and recreating the container loses it;
- committing a container can capture changes into a new image, but is not a maintainable build workflow;
- an attached named volume follows its own lifecycle and can outlive the container.

```bash
docker run --name ephemeral alpine sh -c 'date > /created-at'
docker start -a ephemeral
docker cp ephemeral:/created-at -
docker rm ephemeral
# A new alpine container has no /created-at file.
```

Applications should write logs to stdout/stderr for collection, place caches in explicitly disposable locations, and write durable state to mounted or external storage. A read-only root filesystem (`--read-only`) is a useful test: it reveals hidden assumptions about writable paths. Supply explicit writable tmpfs or volumes for legitimate needs.

## Practical Check

- Explain **Ephemeral Container Filesystem** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it


- [[Container Lifecycle]] %% Conceptual overlap; intentionally reciprocal %%

---
# References
- [Docker documentation](https://docs.docker.com/)
