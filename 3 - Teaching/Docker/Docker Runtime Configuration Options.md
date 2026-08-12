**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #runtime #configuration #options

**Links / Tags:**
- **Relevance Links:**
	- Running Containers %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Docker Runtime Configuration Options

> Settings applied when a container is created without changing the image itself.

## Key Ideas

- Configuration includes commands, environment, ports, mounts, networks, users, capabilities, resources, health checks, and restart policies.
- Runtime configuration should express environment-specific choices while the image remains reusable.
- Prefer `--mount` for explicit storage syntax and bind published development ports to `127.0.0.1` when public access is unnecessary.
- Changing create-time settings generally requires recreating the container.

## Deep Dive
## Configuration Belongs at the Correct Layer

| Concern | Usually belongs in | Example |
|---|---|---|
| Application binary/runtime | Image | Node runtime and compiled app |
| Safe default command | Image metadata | `CMD ["node", "server.js"]` |
| Environment-specific endpoint | Runtime | `DATABASE_URL` |
| Sensitive credential | Secret mechanism | Mounted secret file |
| Durable state | Volume/external service | Database data directory |
| Host exposure | Runtime/platform | Published port or ingress |
| Resource policy | Runtime/platform | Memory and CPU limits |

Environment variables are convenient but visible through process/container inspection to privileged users and often leak through logs. They are configuration, not automatically a secure secret store.

Health checks report the container’s health state but do not restart a standalone unhealthy container by themselves. Restart policy reacts primarily to process exit. Design the application to exit on unrecoverable state, expose meaningful readiness, and tolerate dependency reconnection.

Inspect the effective configuration with `docker inspect`; do not infer it only from the command you remember typing.

## Practical Check

- Explain **Docker Runtime Configuration Options** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it

- [[Docker Port Publishing]] %% Conceptual overlap; intentionally reciprocal %%

- [[Docker Containers]] %% Conceptual overlap; intentionally reciprocal %%

---
# References
- [Docker documentation](https://docs.docker.com/)
