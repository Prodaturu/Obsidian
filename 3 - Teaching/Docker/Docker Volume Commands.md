**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #volume #commands

**Links / Tags:**
- **Relevance Links:**
	- Docker CLI %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Docker Volume Commands

> Commands for Docker-managed persistent storage.

## Key Ideas

- Use `docker volume create`, `ls`, `inspect`, and `rm`.
- `docker volume rm` fails while a container references the volume.
- Anonymous volumes can accumulate when container lifecycle is not managed carefully.
- Confirm ownership and backups before removing storage; volume deletion can destroy important data.

## Deep Dive
## Safe Volume Administration

```bash
docker volume ls
docker volume inspect db-data
docker container ls -a --filter volume=db-data
```

Before removal, identify every consumer and confirm whether the data has a tested backup. A stopped container can still reference a volume and protect it from deletion.

Compose-generated volume names are commonly project-scoped. `docker compose down` keeps them; `docker compose down --volumes` deletes them. The latter is useful for resetting disposable development state and dangerous when the volume contains the only database copy.

Do not edit Docker’s internal volume directory directly. Attach the volume to a purpose-built utility container for inspection, migration, backup, or restore, with read-only access whenever writes are unnecessary.

## Practical Check

- Explain **Docker Volume Commands** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it

- [[Docker Volumes]] %% Conceptual overlap; intentionally reciprocal %%

---
# References
- [Docker documentation](https://docs.docker.com/)
