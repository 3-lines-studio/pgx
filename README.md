# pgx

Read-only PostgreSQL tool for AX.

## Install

```sh
curl -fsSL https://ax.3lines.studio/install.sh | sh -s -- pgx
```

## Configure

```sh
export DATABASE_URL=postgres://user:password@host/database
export AX_TOOLS=pgx
```

The legacy `ALFRED_PICSEL_DATABASE_URL` name remains supported during migration.

## Protocol

```sh
pgx ax-tools
printf '{"sql":"SELECT 1"}' | pgx ax-run postgres_query
```

Every query runs in a PostgreSQL read-only transaction. Results stop at 1,000 rows.

## Test

```sh
go test ./...
```
