Aquí tienes el README completo con el cambio:

Real-time database health monitoring + automated backup verification via ephemeral Docker containers.

⚡ Get the full setup
Full source code + Docker Compose + Grafana dashboards + Nginx config — €10 on Gumroad:https://operao.gumroad.com/l/ytuyep

What it does:

-Monitoring: Connects to MySQL, PostgreSQL, MongoDB, Redis and SQLite. Checks connectivity and response times every 30 seconds. Streams live status to a web dashboard via WebSocket. Alerts Discord, Slack or Telegram only when state changes.

-Backup verification: Every week, takes your most recent backup, spins up an isolated Docker container, restores it, runs integrity checks, and destroys the container. Every month, audits a random sample of the last 6 months. A backup is not marked valid until it has been restored in a live environment.

The problem it solves:

Most backup scripts confirm the dump was written to disk. That's not enough — you find out the backup is corrupt during the emergency, not before it.
Stack

Python + asyncio
Docker SDK
WebSocket (live dashboard)
REST API with API key auth and rate limiting
Prometheus metrics + Grafana dashboards included

Supported databases:

MySQL · MariaDB · PostgreSQL · SQLite · MongoDB · Redis

Quick start:

bashgit clone https://github.com/alberto35325/database-guardian.git

cd database-guardian
cp config/config.example.json config/config.json
docker-compose up -d
Dashboard available at http://127.0.0.1:8080

Manual backup verification:

bash./tools/restore_check/restore_check.sh backup.sql

License:

Commercial license available on Gumroad — includes full source code, Docker Compose setup, Grafana dashboards, and Nginx config. https://operao.gumroad.com/l/ytuyep
