**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #bind #mounts

**Links / Tags:**
- **Relevance Links:**
	- Docker Data Persistence %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Docker Bind Mounts

> A mapping from a specific host file or directory into a container.

## Key Ideas

- Mount with `--mount type=bind,src=/host/path,dst=/app`.
- Excellent for source-code development and injecting local configuration.
- The container can affect host files when the mount is writable, so use `readonly` when possible.
- Host paths reduce portability and can behave differently across Docker Desktop and native Linux.

## Example

```bash
docker run --rm \
  --mount type=bind,src="$PWD",dst=/workspace,readonly \
  -w /workspace alpine ls -la
```

## Deep Dive
## Bind-Mount Semantics

A bind mount delegates storage and access control to a host path. The same container definition may fail on another machine because the path is absent, has different case sensitivity, belongs to another UID, or is not shared into Docker Desktop.

Prefer the explicit syntax:

```bash
docker run --rm \
  --mount type=bind,src="$PWD",dst=/workspace,readonly \
  -w /workspace alpine:3.21 find . -maxdepth 1 -type f
```

`--mount` normally errors if the source path does not exist. The shorter `-v` syntax can create a missing source directory, sometimes hiding a typo.

### Permissions

The kernel checks numeric UID/GID ownership. A process running as UID 1000 in the container can usually write files owned by host UID 1000, even if usernames differ. In development, run with an appropriate user or configure ownership rather than applying broad `chmod 777` permissions.

### Security

A writable mount gives the container authority over that host path. Mount the smallest path, use `readonly`, and never casually mount `/`, credential directories, SSH keys, or the Docker socket.

## Practical Check

- Explain **Docker Bind Mounts** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it

- [[Hot Reloading with Docker]] %% Conceptual overlap; intentionally reciprocal %%

---
# References
- [Docker documentation](https://docs.docker.com/)
