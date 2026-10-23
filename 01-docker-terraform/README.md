# Module 1 — Docker, Postgres, Terraform, GCP

Study notes (PT-BR, with diagrams): [DE Zoomcamp M1 — Docker](https://app.notion.com/p/402d2dc61bf481b5bf71c3e2d09a1263) on Notion.

| Block | Topic | Status |
|---|---|---|
| 1 | Images, containers & layers | ✅ |
| 2 | Volumes (named volume vs bind mount) | ✅ |
| 3 | Ingest NY Taxi data into Postgres | ⬜ |
| 4 | Docker Compose (Postgres + pgAdmin) | ⬜ |
| 5 | Terraform + GCP | ⬜ |

## Postgres with a named volume

```bash
docker run -d \
  -e POSTGRES_USER="root" \
  -e POSTGRES_PASSWORD="root" \
  -e POSTGRES_DB="ny_taxi" \
  -v ny_taxi_pgdata:/var/lib/postgresql \
  -p 5432:5432 \
  --name m1 \
  postgres:18

docker exec -it m1 psql -U root -d ny_taxi
```

- **Named volume** (`ny_taxi_pgdata:`) instead of the course's bind mount (`$(pwd)/ny_taxi_postgres_data:`): Docker manages it, so there are no UID 999 permission issues on the host.
- **Postgres 18+ mounts at `/var/lib/postgresql`** (PGDATA is `/var/lib/postgresql/18/docker`). The `/var/lib/postgresql/data` path from older tutorials only applies to ≤ 17.
- Data survives `docker rm -f m1`: a new container started with the same `-v` sees the same tables.

## Cleanup

```bash
docker rm -f m1
docker volume rm ny_taxi_pgdata   # deletes the data
```
