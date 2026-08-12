**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #docker

**Links / Tags:**
- **Relevance Links:**
	- Container Registries %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Docker Hub

> Docker’s public registry and ecosystem for official, verified, community, and private image repositories.

## Key Ideas

- Authenticate with `docker login`, pull with `docker pull`, and push to a repository you can access.
- Review publisher identity, supported tags, architectures, update cadence, and usage instructions.
- Rate limits and organisation policies may affect automated pulls.
- A familiar name or `latest` tag is not a substitute for trust and version control.

## Deep Dive
## Selecting an Image on Docker Hub

Not all repositories carry the same assurance. Docker Official Images, verified publisher content, and arbitrary community images differ in governance. For any candidate, inspect:

- exact publisher and repository spelling;
- supported tags and whether they are mutable;
- image architectures;
- environment variables, default user, ports, mounts, and command;
- source repository and build transparency;
- maintenance cadence and upgrade notes.

```bash
docker pull nginx:1.27-alpine
docker image inspect nginx:1.27-alpine --format '{{json .Config}}'
docker image ls nginx --digests
```

Rate limits, retention, organisation access controls, and automated builds can affect CI and production reliability. Mirror or use a private registry when policy and availability require it. Always use the fully qualified reference when ambiguity matters.

## Practical Check

- Explain **Docker Hub** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it


---
# References
- [Docker documentation](https://docs.docker.com/)
