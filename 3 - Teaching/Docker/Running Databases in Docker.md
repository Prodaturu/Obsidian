**Created:** *<span class ="color-green">11.08.26, 12:00</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #docker #containers
- **Topic Tags:**
	- #running #databases

**Links / Tags:**
- **Relevance Links:**
	- Using Third-Party Container Images %% Parent; plain text prevents a child-to-parent graph edge %%
- **Topic Links:**
	-

---

# Running Databases in Docker

> Running a database image with persistent storage and explicit configuration.

## Key Ideas

- Attach a named volume to the database data directory.
- Use secrets or protected environment sources for credentials; do not commit passwords.
- Publish the port only when host access is required; services on the same Docker network use the container port.
- Plan backups, upgrades, health checks, and graceful shutdown just as for a non-containerised database.

## Deep Dive
## Development Database Pattern

```yaml
services:
  db:
    image: postgres:17
    environment:
      POSTGRES_DB: app
      POSTGRES_USER: app
      POSTGRES_PASSWORD_FILE: /run/secrets/db-password
    secrets:
      - db-password
    volumes:
      - db-data:/var/lib/postgresql/data
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U app -d app"]
      interval: 5s
      timeout: 3s
      retries: 10
secrets:
  db-password:
    file: ./secrets/db-password.txt
volumes:
  db-data:
```

The application should connect to hostname `db` and PostgreSQL’s container port `5432` when both services share the Compose network. Publishing `5432` is only required for a host-side client.

### Lifecycle responsibilities

- The image version and the on-disk data format may have upgrade constraints. Read the database image’s upgrade documentation before changing major versions.
- A health check reports readiness more accurately than “the process exists,” but clients still need retry logic.
- A named volume preserves state; database-native dumps or consistent snapshots provide backups.
- Containers do not make a single database highly available. Production replication, failover, encryption, monitoring, and recovery remain database/platform concerns.

## Practical Check

- Explain **Running Databases in Docker** in your own words and identify one situation where it matters in a real container workflow.

---

# Related Notes
> Things you might want to think about alongside this note, but not because of it


- [[Docker Volumes]] %% Conceptual overlap; intentionally reciprocal %%

- [[Testing with Docker]] %% Conceptual overlap; intentionally reciprocal %%

---
# References
- [Docker documentation](https://docs.docker.com/)
