**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #network #drivers

**Links / Tags:**
- **Relevance Links:**
	- Docker Networking %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Docker Network Drivers

> Drivers implement different connectivity models for Docker networks.

## Key Ideas

- `bridge` is the common single-host model; user-defined bridges provide DNS and isolation.
- `host` shares the host network namespace on supported platforms and removes normal port mapping.
- `none` gives a container no external network interface.
- `overlay` connects services across Docker hosts in Swarm; `macvlan` and `ipvlan` address specialised network integration.

## Deep Dive
## Driver Selection

| Driver | Scope/model | Main use |
|---|---|---|
| User-defined `bridge` | Single Docker host | Normal local applications and Compose |
| `host` | Shares host network namespace | Special performance/integration needs |
| `none` | Loopback-only isolation | Workloads needing no network |
| `overlay` | Multiple Swarm nodes | Swarm service communication |
| `macvlan` | Container appears on physical L2 network | Legacy/network-appliance integration |
| `ipvlan` | L2/L3 integration with fewer MACs | Specialised infrastructure |

Start with a user-defined bridge. It provides service discovery and a clear isolation boundary. Advanced drivers carry operational assumptions about routing, host support, security tooling, and address management.

Host networking removes the normal port-namespace boundary; `-p` is not meaningful in the usual way. It is not a universal “fix networking” option and behaves differently across platform environments.

## Practical Check

- Explain **Docker Network Drivers** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it


---
# References
- [Docker documentation](https://docs.docker.com/)
