**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #image #size #security

**Links / Tags:**
- **Relevance Links:**
	- Building Container Images %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Docker Image Size and Security

> Reducing shipped content also reduces transfer time and often the attack surface.

## Key Ideas

- Use a minimal trusted base suitable for the workload, not merely the smallest possible image.
- Use multi-stage builds so compilers and build secrets do not enter the runtime image.
- Remove unnecessary packages and run as a non-root user.
- Pin and regularly refresh base images, then scan the final image and test it.

## Deep Dive
## Size and Attack Surface Are Related, Not Identical

A smaller image usually transfers and starts distribution faster and may contain fewer packages. But “small” is not automatically secure: an unpatched tiny image, unknown binary, or image without debugging metadata can still be risky.

### Reduction techniques

1. Use multi-stage builds and copy only runtime artifacts.
2. Exclude build output, VCS data, credentials, and local caches with `.dockerignore`.
3. Install only required OS packages and clean package-manager metadata in the same layer where needed.
4. Choose a maintained runtime base matching operational needs.
5. Inspect with `docker image history` and image-analysis tooling.

### Base-image trade-off

“Distroless” or `scratch` images minimise runtime content but lack shells and package managers. This improves some security properties yet changes debugging and certificate/timezone/library assumptions. Use separate diagnostic containers or debug stages rather than installing tools into production at incident time.

Security comes from provenance, patching, scanning, least privilege, secret hygiene, and runtime restrictions—not from megabytes alone.

## Practical Check

- Explain **Docker Image Size and Security** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it

- [[Docker Image Security]] %% Conceptual overlap; intentionally reciprocal %%

---
# References
- [Docker documentation](https://docs.docker.com/)
