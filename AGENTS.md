# Base44 dev environment

## What this is
A single-file static site (`index.html`) — an interactive yellow flower garden in Spanish. No build step, no backend, no package manager, no external services or credentials.

## How it runs
Served by `nginx:alpine` via `docker-compose.base44.yml`, bind-mounting `index.html` as the only document. The web entry point is host port 3000.

## Verify it works
```sh
docker compose -f docker-compose.base44.yml up -d
curl -s http://localhost:3000/ | head -5   # should print <!doctype html> ... <title>Flores amarillas
```

## Editing
Edit `index.html` directly. Changes appear on reload (no live-reload dev server; call `reload_preview` after edits for the user to see them).
