**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #runtime #security

**Links / Tags:**
- **Relevance Links:**
	- Container Security %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Docker Runtime Security

> Restricting what a running container and its processes can do.

## Key Ideas

- Run as a non-root user and drop unnecessary Linux capabilities.
- Avoid `--privileged`, host namespaces, unrestricted devices, writable host mounts, and the Docker socket.
- Use read-only filesystems, resource limits, seccomp/AppArmor/SELinux controls, and isolated networks where appropriate.
- Treat access to the Docker daemon socket as highly privileged because it can usually control the host.

## Deep Dive
## Least-Privilege Runtime Example

```bash
docker run --rm \
  --user 10001:10001 \
  --read-only \
  --tmpfs /tmp:rw,noexec,nosuid,size=64m \
  --cap-drop ALL \
  --security-opt no-new-privileges=true \
  --memory 256m --cpus 0.5 --pids-limit 100 \
  example/app:1.0
```

Apply controls incrementally and test functionality. Some applications legitimately need a writable path or capability; grant the smallest required scope rather than falling back to `--privileged`.

### Dangerous integrations

- Docker socket: normally allows control of the daemon and effective host takeover.
- Writable bind mounts: allow modification of host files in the mounted scope.
- `--privileged`: grants broad device/capability access and weakens isolation.
- Host PID/network namespaces: expose host-level views and interactions.
- Secrets in command-line arguments/environment: may be visible through inspection or logs.

On supported Linux systems, seccomp, AppArmor or SELinux, user namespaces/rootless mode, and read-only filesystems add defence in depth. Their exact behaviour depends on host policy.

## Practical Check

- Explain **Docker Runtime Security** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it


- [[Docker Port Publishing]] %% Conceptual overlap; intentionally reciprocal %%

- [[Docker Engine on Linux]] %% Conceptual overlap; intentionally reciprocal %%

---
# References
- [Docker documentation](https://docs.docker.com/)
