**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #running #commandline #utilities

**Links / Tags:**
- **Relevance Links:**
	- Using Third-Party Container Images %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Running Command-Line Utilities in Docker

> Using a container as a disposable, versioned CLI without installing the tool directly on the host.

## Key Ideas

- Use `--rm` so the temporary container is deleted after it exits.
- Bind-mount the working directory and set `-w` when the tool must read or write project files.
- Match user IDs where necessary to avoid root-owned output on Linux.
- Example: `docker run --rm -v "$PWD:/work" -w /work node:22 npm test`.

## Deep Dive
## The Disposable Tool Pattern

```bash
docker run --rm -it \
  --mount type=bind,src="$PWD",dst=/work \
  --workdir /work \
  --user "$(id -u):$(id -g)" \
  node:22-alpine npm test
```

Read the command from left to right: run a temporary interactive container; mount the current project; make it the working directory; use the caller’s numeric identity; start from a versioned Node image; replace the default command with `npm test`.

### When this pattern shines

- Trying a compiler, formatter, migration utility, or cloud CLI without host installation.
- Reproducing a CI toolchain version.
- Processing files while keeping the tool isolated from unrelated host paths.

### Limits

- Every mount and environment variable expands what the tool can access.
- Shell aliases should not hide important security options or floating image tags.
- Interactive terminal flags are inappropriate in non-interactive CI.
- Performance may be lower when a tool performs heavy filesystem I/O through Docker Desktop bind mounts.

## Practical Check

- Explain **Running Command-Line Utilities in Docker** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it


---
# References
- [Docker documentation](https://docs.docker.com/)
