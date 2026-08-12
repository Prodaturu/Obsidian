**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #linux #namespaces

**Links / Tags:**
- **Relevance Links:**
	- Docker Underlying Technologies %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Linux Namespaces

> A Linux kernel feature that gives processes isolated views of system resources.

## Key Ideas

- PID namespaces isolate process identifiers; network namespaces isolate interfaces and routing.
- Mount namespaces isolate filesystem mount tables; UTS namespaces isolate hostnames.
- IPC and user namespaces isolate inter-process resources and user/group identifiers.
- Namespaces limit visibility, but they are only one part of container security.

## Deep Dive
## Namespace Types

| Namespace | Isolated view | Docker-visible effect |
|---|---|---|
| PID | Process identifiers | Container sees its own PID tree |
| NET | Interfaces, routes, ports, firewall state | Container gets a network stack |
| MNT | Mount points | Image root and mounts appear as its filesystem |
| UTS | Hostname/domain name | `--hostname` can differ per container |
| IPC | Shared memory and IPC objects | IPC resources can be separated |
| USER | User/group ID mapping | Container root can map to an unprivileged host ID |
| CGROUP | Cgroup view | Hides unrelated control-group structure |

Namespaces provide isolation of **views**, not automatic permission. A process that can access a dangerous host resource through a bind mount or socket remains dangerous. Conversely, sharing a namespace explicitly—such as `--network host` or `--pid host`—removes that dimension of isolation.

Useful observation command on Linux:

```bash
docker run --rm alpine readlink /proc/self/ns/pid
readlink /proc/self/ns/pid
```

The identifiers normally differ because the shell and container process belong to different PID namespaces.

## Practical Check

- Explain **Linux Namespaces** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it


- [[What Are Containers]] %% Conceptual overlap; intentionally reciprocal %%

---
# References
- [Docker documentation](https://docs.docker.com/)
