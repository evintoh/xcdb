# xcdb

Manage database schema using python alembic migration

## Local postgresql instance

For testing purpose, run a local instance of postgresql using docker.

```bash
docker run --name postgres \
-e POSTGRES_USER=scott \
-e POSTGRES_PASSWORD=tiger \
-e POSTGRES_DB=test \
-p 5432:5432 \
-d postgres
```

## Install Alembic and Psycopg2 (the Postgress driver)

```bash
pip install -r requirements.txt
```

## Initialize alembic environment

```bash
alembic init [folder]
```

## Create a migration script

```bash
alembic revision -m "create account table"
```

## Upgrade/Downgrade the database

```bash
alembic upgrade head
alembic upgrade ae1
alembic upgrade +2
alembic downgrade base
alembic downgrade -1
alembic current
alembic history --verbose
```