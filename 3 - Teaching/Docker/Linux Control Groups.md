**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #linux #control #groups

**Links / Tags:**
- **Relevance Links:**
	- Docker Underlying Technologies %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Linux Control Groups

> Control groups, or cgroups, organise processes and account for or limit their resource use.

## Key Ideas

- Docker can constrain CPU, memory, process count, and other resources.
- A namespace answers “what can this process see?”; a cgroup answers “how much can it use?”
- Limits reduce noisy-neighbour problems but must be tested under realistic load.
- An out-of-memory limit can cause a container process to be killed rather than gracefully slowed.

## Deep Dive
## Limits, Accounting, and Pressure

Namespaces prevent a process from seeing unrelated resources; cgroups organise processes so the kernel can account for and control consumption. Docker flags are a convenient interface over those controls.

```bash
docker run --rm --memory=256m --cpus=0.5 alpine sh -c 'cat /sys/fs/cgroup/memory.max 2>/dev/null || true'
```

### Important behaviours

- Without explicit constraints, a container may compete for as much CPU or memory as the host permits.
- `--memory` is a hard ceiling. Exceeding it may trigger the OOM killer.
- `--cpus=0.5` limits CPU time; it does not make half a physical CPU exclusively available.
- CPU shares influence relative priority under contention rather than imposing a hard maximum.
- `--pids-limit` limits process creation and helps contain fork bombs.

Limits require measurement. A memory limit below normal peak use creates instability; no limit allows one workload to threaten its neighbours. Observe `docker stats`, application latency, and host pressure together.

## Practical Check

- Explain **Linux Control Groups** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it


- [[What Are Containers]] %% Conceptual overlap; intentionally reciprocal %%

---
# References
- [Docker documentation](https://docs.docker.com/)
