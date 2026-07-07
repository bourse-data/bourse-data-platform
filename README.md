# Bourse Data Platform

Local platform for running `bourse-data-ui`, `bourse-data-api`, `codal-api`, and Redis with Docker Compose.

## Prerequisites

- Docker + Docker Compose
- `codal-api` must exist at `../codal-api`
- `bourse-data-api` must exist at `../bourse-data-api`
- `bourse-data-ui` must exist at `../bourse-data-ui`

## Quick start

```bash
cp ../bourse-data-ui/.env.example ../bourse-data-ui/.env
./platform.sh start
```

`platform.sh` loads `bourse-data-ui/.env` for both the Vite build and the
`codal-api` container. `VITE_CODAL_REFRESH_INTERVAL_MS` is therefore the single
refresh/cache interval for the UI, financial-notice cache, and financial-statement cache.

For direct Compose usage, pass the same file explicitly:

```bash
docker compose --env-file ../bourse-data-ui/.env up -d --build
```

## Stop

```bash
docker compose down
```

## Endpoints

- UI: `http://localhost:8080`
- Symbol search API: `http://localhost:9003/api/v1/market-search/symbols?query=فملی`
- API: `http://localhost:9002/codal`
- Swagger: `http://localhost:9002/codal/doc.html`
- Redis: `localhost:6379`
