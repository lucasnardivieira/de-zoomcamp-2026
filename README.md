# DE Zoomcamp 2026 — homework & notes

My work for the [DataTalks.Club Data Engineering Zoomcamp](https://github.com/DataTalksClub/data-engineering-zoomcamp), part of my [learning journey](https://github.com/lucasnardivieira/learning-journey) toward Data + AI Engineering.

| Module | Topic | Status |
|---|---|---|
| [01](01-docker-terraform/) | Docker, Postgres, Terraform, GCP | 🟨 |
| [02](02-workflow-orchestration/) | Workflow orchestration (Kestra) | ⬜ |
| [workshop](workshop-dlt/) | Data ingestion with dlt | ⬜ |
| [03](03-data-warehouse/) | Data warehouse (BigQuery) | ⬜ |
| [04](04-analytics-engineering/) | Analytics engineering (dbt) | ⬜ |
| [05](05-data-platforms/) | Data platforms (Bruin) — skim | ⬜ |
| [06](06-batch/) | Batch processing (Spark) | ⬜ |
| [07](07-streaming/) | Streaming (Kafka) — intro | ⬜ |

## Conventions
- Python with `uv` + `ruff`; one environment per module.
- Datasets are downloaded by scripts, never committed.
- Secrets live in `.env` / service-account keys, all gitignored.
- Every cloud resource is created with Terraform and torn down with `terraform destroy`.
