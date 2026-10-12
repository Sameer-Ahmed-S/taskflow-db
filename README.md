# taskflow-db

TaskFlow database repo — owns the **data model** (ADR-001). Part of a spec-driven, multi-repo demo:

| Repo | Role |
|------|------|
| **taskflow-db** (this) | Postgres schema + migrations |
| [taskflow-backend](https://github.com/Sameer-Ahmed-S/taskflow-backend) | Express API + authoritative spec (`/spec`) |
| [taskflow-frontend](https://github.com/Sameer-Ahmed-S/taskflow-frontend) | React SPA |

## Run locally

```sh
docker compose up -d
```

Postgres 16 on `localhost:5432`, db/user/password: `taskflow`. Migrations in `migrations/` auto-apply on first start.

## Change process (SDD)

Schema changes start in the **spec** ([taskflow-backend/spec](https://github.com/Sameer-Ahmed-S/taskflow-backend/tree/main/spec)), then land here as a new numbered migration (ADR-002). Never edit an applied migration — add a new one.
