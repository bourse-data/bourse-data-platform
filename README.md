# Codal Platform

Standalone platform repository for running `CodalApi` + `codal-ui` + Redis with Docker Compose.

## Prerequisites

- Docker + Docker Compose
- `CodalApi` repository must exist at `../CodalApi`
- `codal-ui` repository must exist at `../codal-ui`

## Quick start

```bash
cp .env.example .env
docker compose up -d --build
```

## Stop

```bash
docker compose down
```

## Endpoints

- UI: `http://localhost:5174`
- API: `http://localhost:9002/codal`
- Swagger: `http://localhost:9002/codal/doc.html`
- Redis: `localhost:6379`
