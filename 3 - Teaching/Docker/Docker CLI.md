**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #map

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers #mapofcontent
- **Topic Tags:**
	- #docker

**Links / Tags:**
- **Relevance Links:**
	- Docker %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	- [[Docker Image Commands]]
	- [[Docker Container Commands]]
	- [[Docker Volume Commands]]
	- [[Docker Network Commands]]

---

# Docker CLI

> The command-line interface for managing Docker objects through the Engine API.

## Key Ideas

- Use object-oriented commands: `docker image`, `docker container`, `docker volume`, and `docker network`.
- Inspect state before deleting resources and prefer targeted cleanup over broad prune commands.
- Use `--help`, structured `--format`, and `docker inspect` when diagnosing behaviour.

## Learning Path

- [[Docker Image Commands]]
	- Commands that pull, build, inspect, tag, list, push, and remove images.
- [[Docker Container Commands]]
	- Commands that create and operate container instances.
- [[Docker Volume Commands]]
	- Commands for Docker-managed persistent storage.
- [[Docker Network Commands]]
	- Commands for creating and inspecting container connectivity boundaries.

## Deep Dive
## A Repeatable CLI Method

Most investigations follow **list → inspect → logs/observe → act**:

```bash
docker container ls -a
docker container inspect app
docker container logs --tail 100 app
docker container stats --no-stream app
```

### Contexts and targets

The CLI can target different engines. `docker context show` and `docker context ls` prevent accidental operations against the wrong daemon. Treat a production context like remote administrative access.

### Output for humans and scripts

Use `--format` rather than parsing decorative table output:

```bash
docker container ls --format '{{.Names}}\t{{.Status}}\t{{.Ports}}'
docker inspect --format '{{.State.ExitCode}}' app
```

Commands such as `prune`, volume removal, and force removal can destroy state. Filter and inspect exact targets first. Prefer object-qualified modern commands in notes and automation because `docker container rm` communicates intent more clearly than the shorter alias `docker rm`.

## Practical Check

- Explain how each child topic contributes to this part of the Docker workflow, then follow the links in order.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it


---
# References
- [Docker CLI reference](https://docs.docker.com/reference/cli/docker/)
