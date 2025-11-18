# Gatus Self-Hosted with Docker

![gatus-self-hosted](https://repository-images.githubusercontent.com/1074217939/09fc4ac8-aaa1-4457-bfe8-99c6537993b9)

This repository provides a Docker Compose setup for running a self-hosted [Gatus](https://github.com/TwiN/gatus) instance, a beautiful and automated service health dashboard.

## Features

- **Works out of the box:** Just configure the `.env` file and run the start script.
- **Persistent Storage:** Uses PostgreSQL to store health check results and history.
- **Ready-to-use Scripts:** Includes simple scripts to restart and update the application.
- **Database Backups:** Comes with a script to easily back up the PostgreSQL database.
- **Shared Network:** Pre-configured to use a shared network for easy integration with other services.

## Getting Started

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/AiratTop/gatus-self-hosted
    cd gatus-self-hosted
    ```

2.  **Create the shared network:**
    If you haven't already, create the shared Docker network:
    ```bash
    docker network create shared_network
    ```

3.  **Configure the environment:**
    Create a `.env` file and set the `PSQL_PWD` variable for your PostgreSQL database password.

4.  **Start the service:**
    ```bash
    docker compose up -d
    ```

## Usage

-   **Start:** `docker compose up -d`
-   **Restart:** `./restart-docker.sh`
-   **Update:** `./update-docker.sh` (Pulls the latest Docker image and restarts the container)
-   **Backup:** `./backup.sh` (Creates a compressed backup in the `backups` directory)

## Backup

This project includes a script to back up the Gatus database.

To create a backup, run:
```bash
./backup.sh
```
This will create a compressed SQL dump of your PostgreSQL database in the `backups/` directory. It is recommended to run this script regularly (e.g., using a cron job).

## Connecting to Other Services

This Gatus setup is part of a larger ecosystem of self-hosted services that can all run on the same `shared_network`. This allows Gatus to monitor them securely using their container names as hostnames.

## See Also

Check out other self-hosted solutions:

-   [**postgresql-self-hosted**](https://github.com/AiratTop/postgresql-self-hosted): A simple and robust PostgreSQL setup.
-   [**mysql-self-hosted**](https://github.com/AiratTop/mysql-self-hosted): A self-hosted MySQL instance.
-   [**clickhouse-self-hosted**](https://github.com/AiratTop/clickhouse-self-hosted): High-performance columnar database for analytics.
-   [**metabase-self-hosted**](https://github.com/AiratTop/metabase-self-hosted): Self-hosted Metabase on Docker for business intelligence and analytics.
-   [**qdrant-self-hosted**](https://github.com/AiratTop/qdrant-self-hosted): A vector database for AI applications.
-   [**redis-self-hosted**](https://github.com/AiratTop/redis-self-hosted): A fast in-memory data store, often used as a cache or message broker.
-   [**caddy-self-hosted**](https://github.com/AiratTop/caddy-self-hosted): A modern, easy-to-use web server with automatic HTTPS.
-   [**wordpress-self-hosted**](https://github.com/AiratTop/wordpress-self-hosted): Production-ready WordPress stack with MySQL, phpMyAdmin, and WP-CLI.
-   [**n8n-self-hosted**](https://github.com/AiratTop/n8n-self-hosted): Scalable n8n with workers, Caddy for auto-HTTPS, and backup scripts.
-   [**monitoring-self-hosted**](https://github.com/AiratTop/monitoring-self-hosted): Self-hosted monitoring stack with Prometheus and Grafana.
-   [**ollama-self-hosted**](https://github.com/AiratTop/ollama-self-hosted): Ready-to-use solution for running Ollama with the Open WebUI on Docker.
-   [**authentik-self-hosted**](https://github.com/AiratTop/authentik-self-hosted): Authentik is a flexible, open-source Identity & Access Management (IAM) solution.
-   [**gatus-self-hosted**](https://github.com/AiratTop/gatus-self-hosted): Automated service health dashboard with a PostgreSQL backend and backup scripts.
-   [**beszel-self-hosted**](https://github.com/AiratTop/beszel-self-hosted): Ready-to-run Beszel hub + agent stack for monitoring your infrastructure.

## Services

- `gatus`: The Gatus health dashboard application.
- `gatus-psql`: PostgreSQL database for data storage.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Author

**AiratTop**

- Website: [airat.top](https://airat.top)
- GitHub: [@AiratTop](https://github.com/AiratTop)
- Email: [mail@airat.top](mailto:mail@airat.top)
- Repository: [gatus-self-hosted](https://github.com/AiratTop/gatus-self-hosted)
