**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #docker

**Links / Tags:**
- **Relevance Links:**
	- Running Containers %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# docker run

> The primary command for creating and starting one container.

## Key Ideas

- Pattern: `docker run [OPTIONS] IMAGE [COMMAND] [ARG...]`.
- Common flags include `--name`, `--rm`, `-d`, `-it`, `-p`, `-e`, `--mount`, and `--network`.
- Example: `docker run --rm -p 127.0.0.1:8080:80 nginx:alpine`.
- Options before the image configure Docker; arguments after the image normally replace the image command.

## Deep Dive
## Parse the Command Correctly

```text
docker run [DOCKER OPTIONS] IMAGE [COMMAND] [ARGUMENTS]
```

Everything before `IMAGE` configures the container. Everything after normally replaces the image’s `CMD` (while preserving its entrypoint unless `--entrypoint` is used).

```bash
docker run --rm \
  --name web-lab \
  --publish 127.0.0.1:8080:80 \
  --memory 256m \
  --cpus 0.5 \
  --read-only \
  --tmpfs /var/cache/nginx \
  --tmpfs /var/run \
  nginx:1.27-alpine
```

Useful option groups:

| Concern | Options |
|---|---|
| Lifecycle | `--rm`, `-d`, `--restart`, `--stop-timeout` |
| Interaction | `-i`, `-t`, `--attach` |
| Identity | `--name`, `--hostname`, `--label`, `--user` |
| Configuration | `--env`, `--env-file`, `--workdir`, `--entrypoint` |
| Storage | `--mount`, `--tmpfs`, `--read-only` |
| Network | `--network`, `--publish`, `--network-alias` |
| Resources | `--memory`, `--cpus`, `--pids-limit` |
| Security | `--cap-drop`, `--security-opt`, `--device` |

Avoid `--privileged` as a troubleshooting shortcut. It changes the security question rather than solving the original configuration problem.

## Practical Check

- Explain **docker run** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it


---
# References
- [Docker documentation](https://docs.docker.com/)
