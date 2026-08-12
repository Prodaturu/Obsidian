**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #images

**Links / Tags:**
- **Relevance Links:**
	- Docker Basics %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Docker Images

> An immutable, content-addressed package containing filesystem layers and metadata needed to create a container.

## Key Ideas

- Images are built from Dockerfiles or pulled from registries.
- A repository may have several tags; a digest identifies exact content.
- Layers are reused between related images, reducing build and transfer work.
- An image is not a running process and does not hold the mutable state of a container.

## Deep Dive
## Anatomy of an Image Reference

```text
registry.example.com/team/api:1.4.2
└──── registry ─────┘└repository┘└tag┘
```

If the registry is omitted, Docker applies its default registry rules. If the tag is omitted, `latest` is commonly assumed; `latest` does not mean newest and does not update itself.

An image contains filesystem layers and a configuration object: default command, entrypoint, environment, working directory, user, labels, and declared ports. Inspect rather than guess:

```bash
docker image inspect nginx:alpine
docker image history nginx:alpine
docker image ls --digests
```

### Tag versus digest

A tag is a mutable pointer useful for humans. A digest such as `sha256:...` identifies exact content. Production systems often record a readable release tag and deploy the resolved digest.

### Architecture

A tag can point to a multi-platform manifest whose entries select different image content for `linux/amd64`, `linux/arm64`, and other targets. “Same tag” can therefore resolve to architecture-specific images with equivalent intent but different digests.

## Practical Check

- Explain **Docker Images** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it

- [[Docker Image Commands]] %% Conceptual overlap; intentionally reciprocal %%

- [[Union Filesystems]] %% Conceptual overlap; intentionally reciprocal %%

---
# References
- [Docker documentation](https://docs.docker.com/)
