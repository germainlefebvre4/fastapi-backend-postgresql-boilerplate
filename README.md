# Python FastAPI with PostgreSQL boilerplate

Python FastAPI with PostgreSQL boilerplate based on [https://github.com/tiangolo/full-stack-fastapi-postgresql](https://github.com/tiangolo/full-stack-fastapi-postgresql).

## Getting started

Install required packages:

```bash
sudo apt update
sudo apt install python3-pip python3-dev
pip install poetry
```

Setup the database:

```bash
docker compose up -d db
```

Run the app:

```bash
poetry install
poetry run alembic upgrade head
poetry run python app/initial_data.py
poetry run uvicorn app.main:app --port=8080 --reload
```

### Troubleshooting

Some distributions might miss some packages. These are some hints if needed:

```bash
# cryptography/cffi
sudo apt install build-essential libssl-dev libffi-dev libpq-dev
```

## Development

### Setup workspace

```bash
sudo apt update
sudo apt install python3-pip python3-dev
pip install poetry
poetry install
```

### Run locally

This section use docker database called `bspauto`.

```bash
docker compose up -d db
poetry run alembic upgrade head
poetry run python app/initial_data.py
poetry run uvicorn app.main:app --port=8080 --reload
```

### Run tests

This section use docker database called `bspauto_test`.

```bash
docker compose up -d db_test
poetry run pytest -sv app/tests/
```
