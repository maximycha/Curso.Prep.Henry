# Base44 Dev Environment

## What this repo is
Henry prep course — a collection of JavaScript/HTML/CSS homework exercises with Jest tests. There is no web application, frontend framework, or backend API. The repo is educational content (markdown READMEs, JS homework files, HTML/CSS demos).

## How it runs here
Since there is no web server, the repo is served as static files via `serve` (npm) on port 3000 with directory listing enabled. The user can browse all course modules, open HTML demos, and view source files directly in the preview.

- **Compose file:** `docker-compose.base44.yml`
- **Base image:** `node:22-alpine`
- **Command:** `npm install` (project deps) → `npm install -g serve@14` → `serve . -l 3000 --no-clipboard`
- **Source:** bind-mounted at `/app` (changes appear immediately; `serve` reads from disk)
- **Healthcheck:** `wget http://localhost:3000/`

## Running tests
The project uses Jest. To run tests for a specific homework:
```
docker compose -f docker-compose.base44.yml exec web npm test <homework-file>.test.js
```

## Secrets
None required. No external services.
