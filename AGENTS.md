# AGENTS.md

## Purpose
Public self-hosted deployment template for Gatus status page and uptime checks with PostgreSQL storage.

## Repository Role
- Category: `*-self-hosted` (public GitHub repository).
- Related local stack: `../gatus-docker`.
- Main entrypoint: `docker-compose.yml`.

## Stack Summary
- Services: `gatus-psql`, `gatus`.
- Exposed port: `8080`.
- External network: `shared_network`.

## Data and Config
- Gatus config: `./config/config.yaml`.
- Gatus app data: `./data/gatus`.
- PostgreSQL data: `./data/gatus-psql`.

## Operations
- Restart stack: `./restart-docker.sh`.
- Update images and restart: `./update-docker.sh`.
- Backup helper: `./backup.sh`.

## AI Working Notes
- Keep check/alert credentials in `.env` (`PSQL_PWD`, Telegram, OIDC, SMTP vars).
- Preserve dependency on healthy `gatus-psql` before starting `gatus`.
- Treat `config/config.yaml` as source of truth for probes and alert rules.
