**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #reloading #with

**Links / Tags:**
- **Relevance Links:**
	- Docker Developer Experience %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Hot Reloading with Docker

> Running a development process that detects mounted source changes and reloads without rebuilding the image each time.

## Key Ideas

- Bind-mount source code into the container while keeping dependencies in an image or named volume.
- The application’s own watcher performs reloads; Docker only provides the files and process environment.
- File notification behaviour and performance differ across native Linux and Docker Desktop.
- Keep the production image and command independent of development-only watchers.

## Deep Dive
## Separate Image Dependencies from Changing Source

```yaml
services:
  app:
    build:
      context: .
      target: development
    command: npm run dev
    volumes:
      - .:/workspace
      - node-modules:/workspace/node_modules
    ports:
      - "127.0.0.1:3000:3000"
volumes:
  node-modules:
```

The source bind mount updates immediately. The named volume prevents the host’s dependency directory from replacing container-installed dependencies. Exact patterns differ by language.

If reload fails, test whether the file changed inside the container, whether the watcher observes that filesystem, whether polling mode is needed on Docker Desktop, and whether the server listens on `0.0.0.0` rather than container loopback.

Do not put a development watcher in the production command. Build a production stage and verify that it starts independently from host source mounts.

## Practical Check

- Explain **Hot Reloading with Docker** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it

- [[Docker Bind Mounts]] %% Conceptual overlap; intentionally reciprocal %%

---
# References
- [Docker documentation](https://docs.docker.com/)
