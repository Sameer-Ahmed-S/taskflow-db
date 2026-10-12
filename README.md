# taskflow-db

TaskFlow database repo — owns the **data model** (ADR-001). Part of a spec-driven, multi-repo demo:

| Repo | Role |
|------|------|
| **taskflow-db** (this) | Postgres schema + migrations |
| [taskflow-backend](https://github.com/Sameer-Ahmed-S/taskflow-backend) | Express API implementing the contract |
| [taskflow-frontend](https://github.com/Sameer-Ahmed-S/taskflow-frontend) | React SPA |

The authoritative spec is **not in GitHub** — it lives locally at `..\spec\` (relative to this repo, i.e. `taskflow-demo\spec\`).

## Run locally

```sh
docker compose up -d
```

Postgres 16 on `localhost:5432`, db/user/password: `taskflow`. Migrations in `migrations/` auto-apply on first start.

## Change process (SDD)

Schema changes start in the **spec** (`..\spec\`, local only), then land here as a new numbered migration (ADR-002). Never edit an applied migration — add a new one.
