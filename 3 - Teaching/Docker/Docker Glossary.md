**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers #glossary
- **Topic Tags:**
	- #vocabulary #reference

**Links / Tags:**
- **Relevance Links:**
	- Docker %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Docker Glossary

> The minimum precise vocabulary needed to reason about Docker.

| Term | Meaning |
|---|---|
| Build context | Files made available to a Docker build, filtered by `.dockerignore` |
| BuildKit | Modern build backend used for Docker image builds |
| cgroup | Linux mechanism for resource accounting and control of process groups |
| Compose | Declarative model and CLI for multi-container applications |
| Container | Isolated runtime process environment created from an image |
| Container port | Port on which a process listens inside the container network namespace |
| Container registry | Service storing and distributing image manifests and blobs |
| Copy-on-write | Layer behaviour where modifications are written to an upper layer |
| Digest | Content-derived immutable identifier such as `sha256:...` |
| Docker CLI | `docker` client that calls an Engine API |
| Docker daemon | Engine service that manages images, containers, networks, and volumes |
| Docker Desktop | Integrated workstation product that manages the local Docker environment |
| Docker Engine | Client/server container platform commonly run directly on Linux |
| Dockerfile | Declarative build recipe for an image |
| Entrypoint | Image/runtime setting defining the executable contract |
| Health check | Command whose result classifies container health; not the same as process existence |
| Host port | Port on a Docker host that may forward to a container port |
| Image | Immutable package of filesystem layers and runtime defaults |
| Layer | Content-addressed filesystem change set used by an image |
| Manifest | Registry object describing image configuration/layers or a platform index |
| Mount | Storage made visible at a path inside a container |
| Namespace | Linux mechanism providing a process an isolated view of a resource |
| Named volume | Docker-managed persistent storage independent of a container lifecycle |
| OCI | Open Container Initiative, maintainer of interoperable image/runtime/distribution specifications |
| PID 1 | Main process inside a container namespace whose exit stops the container |
| Published port | Host-to-container port forwarding configured at runtime |
| Repository | Registry namespace containing related image manifests/tags |
| Restart policy | Engine/platform rule deciding whether to restart an exited container |
| Service | Compose/orchestrator abstraction describing desired container configuration |
| Tag | Human-readable, normally mutable name pointing to image content |
| Writable layer | Per-container filesystem layer above read-only image layers |

## Frequently Confused Pairs

- **Image vs container:** package/template versus runtime instance.
- **Stop vs remove:** terminate the process versus delete the container object and writable layer.
- **Tag vs digest:** mutable human name versus immutable content identity.
- **Volume vs bind mount:** Docker-managed storage versus exact host path.
- **`RUN` vs `CMD`:** build-time execution versus runtime default.
- **`EXPOSE` vs `-p`:** image documentation versus host publication.
- **Container port vs host port:** service’s internal listening port versus external forwarding endpoint.
- **Running vs healthy vs ready:** process exists versus health check passes versus application can safely receive the intended work.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it

---
# References
- [Docker documentation](https://docs.docker.com/)
