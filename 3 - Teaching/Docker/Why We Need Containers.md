**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #need #containers

**Links / Tags:**
- **Relevance Links:**
	- Introduction to Docker %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Why We Need Containers

> Containers make an application environment reproducible and portable across development, testing, and deployment.

## Key Ideas

- Dependencies are packaged with the application instead of being manually installed on every host.
- Process isolation reduces conflicts between applications.
- Images provide a versioned deployment unit, while fast startup supports scaling and disposable environments.
- Containers do not remove the need for monitoring, backups, security, or operating-system knowledge.

## Deep Dive
## Benefits and Their Conditions

| Benefit | Why it happens | What can break it |
|---|---|---|
| Reproducibility | Dependencies are encoded in an image | Floating tags and unpinned package installs |
| Portability | OCI image/runtime contracts are standardised | CPU, kernel, storage, and platform assumptions |
| Isolation | Namespaces and runtime restrictions separate processes | Privileged mode, broad mounts, shared host namespaces |
| Fast startup | No guest OS boot is normally required | Slow application initialisation still remains |
| Consistent CI | The tested image can become the released artifact | Rebuilding separately for every environment |

Containers are especially valuable when a system has several services with conflicting dependencies, developers use different operating systems, CI must reproduce local behaviour, or environments must be created and destroyed frequently.

They are less magical than marketing implies. Containerisation does not design service boundaries, migrate state, provide backups, make an application observable, or secure unsafe code. It moves environmental assumptions into explicit build and runtime definitions so those problems become visible and automatable.

## Practical Check

- Explain **Why We Need Containers** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it


---
# References
- [Docker documentation](https://docs.docker.com/)
