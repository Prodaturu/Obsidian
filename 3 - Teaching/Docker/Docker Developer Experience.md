**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #map

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers #mapofcontent
- **Topic Tags:**
	- #developer #experience

**Links / Tags:**
- **Relevance Links:**
	- Docker %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	- [[Hot Reloading with Docker]]
	- [[Debugging Containers]]
	- [[Testing with Docker]]
	- [[Docker in Continuous Integration]]

---

# Docker Developer Experience

> Using containers to make local feedback loops, debugging, tests, and automation consistent.

## Key Ideas

- Development containers may mount source and enable debug tooling; production images should remain minimal.
- Optimise for fast rebuilds, understandable logs, deterministic dependencies, and easy cleanup.

## Learning Path

- [[Hot Reloading with Docker]]
	- Running a development process that detects mounted source changes and reloads without rebuilding the image each time.
- [[Debugging Containers]]
	- A systematic workflow for understanding failed builds, starts, health checks, networking, and application behaviour.
- [[Testing with Docker]]
	- Using disposable containers to provide repeatable test environments and real service dependencies.
- [[Docker in Continuous Integration]]
	- Building, testing, scanning, and publishing images in an automated pipeline.

## Deep Dive
## Development and Production Have Different Optimisations

| Development | Production |
|---|---|
| Fast feedback and source mounts | Immutable tested artifact |
| Debugger and watcher tools | Minimal runtime content |
| Convenient local ports | Explicit ingress/network policy |
| Seeded disposable data | Managed durable state and backups |

Keep these differences explicit through Dockerfile stages, Compose profiles/overrides, or separate commands—without changing the application’s fundamental runtime contract.

```mermaid
flowchart LR
    E[Edit source] --> W[Watcher reloads]
    W --> T[Run focused tests]
    T --> B[Build production image]
    B --> IT[Integration/security tests]
    IT --> P[Publish digest]
```

A good containerised developer experience has one documented startup command, deterministic versions, understandable logs, quick rebuilds, safe cleanup, and behaviour close enough to deployment to expose real integration bugs.

## Practical Check

- Explain how each child topic contributes to this part of the Docker workflow, then follow the links in order.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it


---
# References
- [Docker documentation](https://docs.docker.com/)
