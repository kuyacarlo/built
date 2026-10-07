# Built API

FastAPI backend for Built. The app is defined in `main.py`, with SQLModel models under `src/models/` and routers under `src/routes/`.

## Local setup

```sh
uv venv
uv pip install -r requirements.txt
uv run fastapi dev main.py
```

## Checks

```sh
uv run pytest
uv run ruff check . --exclude tests,__pycache__
uv run basedpyright
```

The default database URL is `sqlite:///./app.db`; remove local `app.db` when you need a fresh manual run.
