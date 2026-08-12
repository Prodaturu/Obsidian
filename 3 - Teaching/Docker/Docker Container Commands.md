**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #container #commands

**Links / Tags:**
- **Relevance Links:**
	- Docker CLI %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Docker Container Commands

> Commands that create and operate container instances.

## Key Ideas

- Use `docker container ls -a`, `inspect`, `logs`, `stats`, and `top` to understand state.
- `exec` starts another process in a running container; it does not replace the main process.
- Use `stop`, `start`, `restart`, and `rm` deliberately according to lifecycle needs.
- Avoid debugging by permanently changing a running container; capture fixes in the image or configuration.

## Example

```bash
docker container ls -a
docker container logs --follow app
docker container exec -it app sh
docker container stop app
docker container rm app
```

## Deep Dive
## Observation Before Mutation

`docker container ls` shows running containers; add `-a` to include exited ones. A crash loop or immediate exit can otherwise look like “nothing started.”

```bash
docker container inspect --format '{{json .State}}' app
docker container logs --timestamps --tail 200 app
docker container top app
docker container stats --no-stream app
docker container diff app
```

`exec` requires a running container and an executable present in its filesystem. Minimal images may not include `bash`; try the documented shell or use a diagnostic container joined to the same network/namespace where appropriate.

`docker cp` can retrieve a file for diagnostics, but persistent data should use a declared mount. `docker commit` captures a container’s writable changes but bypasses a reviewable Dockerfile; reserve it for exceptional forensic experiments, not normal development.

## Practical Check

- Explain **Docker Container Commands** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it

- [[Docker Containers]] %% Conceptual overlap; intentionally reciprocal %%

---
# References
- [Docker documentation](https://docs.docker.com/)
