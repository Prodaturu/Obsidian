**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #network #commands

**Links / Tags:**
- **Relevance Links:**
	- Docker CLI %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Docker Network Commands

> Commands for creating and inspecting container connectivity boundaries.

## Key Ideas

- Use `docker network create`, `ls`, `inspect`, `connect`, `disconnect`, and `rm`.
- Prefer user-defined bridge networks over the legacy default bridge for service-name DNS and isolation.
- A container can join multiple networks for tiered architectures.
- Removing a network requires disconnecting its attached containers.

## Deep Dive
## Network Inspection Workflow

```bash
docker network ls
docker network inspect project_default
docker container inspect --format '{{json .NetworkSettings.Networks}}' app
```

A network object defines an address space and driver configuration; container endpoints attach to it. `docker network connect` can attach a running container to an additional network, but reproducible systems should declare membership in Compose or deployment configuration.

For connectivity failure, check both endpoints share a network, use the correct DNS name and container port, and ensure the application listens on the container interface—not only `127.0.0.1` inside its own namespace.

Network pruning removes unused networks, including deliberately pre-created networks if no container currently attaches. Inspect first, especially for external Compose networks.

## Practical Check

- Explain **Docker Network Commands** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it


---
# References
- [Docker documentation](https://docs.docker.com/)
