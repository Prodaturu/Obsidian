**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #other #container #registries

**Links / Tags:**
- **Relevance Links:**
	- Container Registries %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Other Container Registries

> OCI-compatible alternatives such as GitHub Container Registry, Amazon ECR, Google Artifact Registry, Azure Container Registry, and self-hosted registries.

## Key Ideas

- Choose based on identity integration, geography, scanning, retention, cost, and platform proximity.
- Fully qualify image names, for example `ghcr.io/org/app:1.4.2`.
- CI should use short-lived or scoped credentials where supported.
- OCI compatibility makes the basic pull, tag, and push workflow portable.

## Deep Dive
## What Changes and What Stays Portable

The image format and basic workflow remain familiar:

```bash
docker login ghcr.io
docker tag app:1.0 ghcr.io/example/app:1.0
docker push ghcr.io/example/app:1.0
```

What varies is identity, repository creation, network locality, pricing, retention, scanning, signing integrations, replication, and deletion semantics. Cloud registries often integrate with workload identity so a deployed service can pull without a long-lived password.

Use fully qualified names in Dockerfiles, Compose files, CI, and deployments. A short `app:1.0` can mean only a local image; `registry.example.com/team/app:1.0` identifies the distribution location and namespace.

When migrating registries, copy manifests and all referenced platform content, preserve immutable release digests where possible, and update trust/signature policy—not just login credentials.

## Practical Check

- Explain **Other Container Registries** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it


---
# References
- [Docker documentation](https://docs.docker.com/)
