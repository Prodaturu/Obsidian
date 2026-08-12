**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #files

**Links / Tags:**
- **Relevance Links:**
	- Building Container Images %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Dockerfiles

> A declarative recipe that BuildKit uses to construct an image.

## Key Ideas

- `FROM` selects a base; `WORKDIR`, `COPY`, and `RUN` assemble the filesystem.
- `CMD` supplies default arguments; `ENTRYPOINT` defines the executable contract.
- Use `.dockerignore` to exclude secrets, build output, and irrelevant files from the build context.
- Prefer exec-form commands such as `CMD ["node", "server.js"]` for predictable signals.

## Example

```dockerfile
FROM node:22-alpine AS dependencies
WORKDIR /app
COPY package*.json ./
RUN npm ci --omit=dev

FROM node:22-alpine
WORKDIR /app
COPY --from=dependencies /app/node_modules ./node_modules
COPY . .
USER node
CMD ["node", "server.js"]
```

## Deep Dive
## Instruction Mental Model

| Instruction | Job | Common mistake |
|---|---|---|
| `FROM` | Starts a build stage | Floating base with no refresh policy |
| `WORKDIR` | Sets a clear absolute working directory | Repeated `RUN cd ...` |
| `COPY` | Copies build-context files | Copying secrets or the whole repo too early |
| `RUN` | Executes during image build | Expecting it to run at container startup |
| `ENV` | Sets image/runtime environment defaults | Baking secrets into the image |
| `ARG` | Supplies build-time values | Treating it as secret storage |
| `USER` | Selects runtime/build user for later instructions | Running the application as root by default |
| `ENTRYPOINT` | Defines executable contract | Shell wrapper that loses signals |
| `CMD` | Defines default command/arguments | Confusing it with build-time `RUN` |

### `RUN`, `CMD`, and `ENTRYPOINT`

`RUN` creates image content during build. `CMD` and `ENTRYPOINT` become image configuration used when a container starts. With exec form:

```dockerfile
ENTRYPOINT ["python", "-m", "http.server"]
CMD ["8000"]
```

`docker run image` runs port 8000; `docker run image 9000` replaces `CMD` and runs port 9000. `--entrypoint` replaces the entrypoint.

### Production-oriented example

```dockerfile
# syntax=docker/dockerfile:1
FROM node:22-alpine AS build
WORKDIR /src
COPY package*.json ./
RUN --mount=type=cache,target=/root/.npm npm ci
COPY . .
RUN npm test && npm run build

FROM node:22-alpine AS runtime
ENV NODE_ENV=production
WORKDIR /app
COPY --from=build --chown=node:node /src/dist ./dist
COPY --from=build --chown=node:node /src/node_modules ./node_modules
USER node
EXPOSE 8080
CMD ["node", "dist/server.js"]
```

Build with `docker build --pull -t example/app:dev .`, then test with a runtime configuration close to deployment.

## Practical Check

- Explain **Dockerfiles** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it


- [[Docker in Continuous Integration]] %% Conceptual overlap; intentionally reciprocal %%

---
# References
- [Dockerfile reference](https://docs.docker.com/reference/dockerfile/)
