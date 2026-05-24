# Data Generator for CDC Postgres Demo

Simulates random data generation with INSERTs, UPDATEs and DELETEs across 3 tables (`customers`, `orders`, `order_items`). Use in combination with the CDC PostgreSQL Connector.

## How It Works

The flow automatically creates the required Postgres schema, tables, and publication on first run via an init ExecuteScript processor. No manual SQL setup is needed.

## Parameters

| Parameter | Description |
|-----------|-------------|
| `Database Connection URL` | JDBC URL to the Postgres instance |
| `Database Name` | Postgres database name |
| `Database User` | Postgres username |
| `Database Password` | Postgres password (sensitive) |
| `Schema Name` | Schema for the generated tables (used in CREATE SCHEMA, CREATE TABLE, and CREATE PUBLICATION) |
| `Publication Name` | Name of the PostgreSQL publication created for CDC. Must match the publication name configured in the CDC connector. Default: `demo_publication` |
| `Database Driver` | JDBC driver asset (postgresql-42.7.10.jar) |

## Deployment

Deploy via `environments/example/config.yaml` using the nifihub CD pipeline. See the [environments README](../../environments/README.md) for details.
