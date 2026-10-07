# Built

Built is a construction-company asset and cost management prototype. It combines a FastAPI backend with a Next.js frontend for projects, tasks, materials, activity logs, and user records.

This repository is suitable as a finalized hackathon/showcase artifact after local verification; it is not production-ready without auth, migrations, deployment hardening, and environment-specific persistence decisions.

## Repository layout

| Path | Purpose |
| --- | --- |
| `api/` | FastAPI API, SQLModel models, routes, and pytest suite |
| `frontend/` | Next.js frontend shell |
| `.github/workflows/ci.yml` | Backend lint/type/test workflow |

## Backend

```sh
cd api
uv venv
uv pip install -r requirements.txt
uv run fastapi dev main.py
```

Useful checks:

```sh
cd api
uv run pytest
uv run ruff check . --exclude tests,__pycache__
uv run basedpyright
```

The API currently uses SQLite at `api/app.db` by default; tests patch database state where needed but may leave local coverage artifacts.

## Frontend

```sh
cd frontend
pnpm install --frozen-lockfile
pnpm lint
pnpm run build
pnpm run dev
```

## Docker Compose

The historical README mentioned `docker compose up -d`, but this checkout does not currently include a `docker-compose.yml`. Use the backend/frontend commands above unless a compose file is added.

## Finalization status

- Backend test and CI commands are discoverable in `.github/workflows/ci.yml`.
- Frontend has standard Next.js scripts in `frontend/package.json`.
- Remaining blockers before public archive: add screenshots/demo link if desired, decide whether to remove committed IDE metadata, and avoid claiming a Compose workflow until a compose file exists.
