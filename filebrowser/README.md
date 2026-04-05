# Filebrowser

Docker and Docker Compose must be installed on your system. Your user ID and group ID are needed to set correct file ownership, run `id -u` and `id -g` to find them.

---

## Configuration

Before starting, edit `.env` to match your environment:

```env
PUID=1000      # your user id  →  run: id -u
PGID=1000      # your group id →  run: id -g
FB_PORT=8095   # port exposed on the host
TZ=Asia/Tehran # your timezone
```

The `filebrowser.json` file controls internal settings such as the database path, root folder, and branding. You generally do not need to touch it.

---

## First-Time Setup

Docker requires the database file to exist as a regular file before the container starts. If it is missing, Docker will silently create a directory in its place and the container will fail. Run the following commands exactly once, in order, to initialize everything correctly:

```bash
# Create the database file before Docker can claim the path
touch filebrowser.db
chmod 666 filebrowser.db

# Initialize the database schema
docker compose run --rm filebrowser config init --database /database/filebrowser.db

# Create the admin user
docker compose run --rm filebrowser users add admin admin --perm.admin --database /database/filebrowser.db

# Start the service
docker compose --env-file .env up -d
```

Once running, open your browser at `http://<server-ip>:8095` and log in with `admin` / `admin`. **Change the password immediately** from the Settings panel.

---

## Day-to-Day Operations

```bash
# Start
docker compose --env-file .env up -d

# Stop
docker compose down

# Restart
docker compose restart filebrowser

# View live logs
docker compose logs -f filebrowser

# Pull the latest image and restart
docker compose pull && docker compose --env-file .env up -d
```

---

## Resetting the Admin Password

If you ever lose access, reset the password directly through the container without stopping the service:

```bash
docker exec -it filebrowser /filebrowser users update admin --password "NewPassword123" --database /database/filebrowser.db
```

---

## File Layout

```
.
├── docker-compose.yml    # service definition
├── filebrowser.json      # filebrowser configuration
├── .env                  # environment variables (PUID, PGID, port, timezone)
├── filebrowser.db        # SQLite database — back this up regularly
└── srv/                  # files served by filebrowser
```

Back up `filebrowser.db` and `srv/` regularly. The database holds all users, settings, and shares — everything else is stateless.

---

## Production Hardening

Place Filebrowser behind a reverse proxy (Nginx, Caddy, or Traefik) with a valid TLS certificate rather than exposing it directly. Restrict port `8095` at the firewall level so it is not reachable from the public internet. Use a strong, unique password and consider disabling the default `admin` account once you have created a personal account with admin privileges.

---

## Why the `touch filebrowser.db` Step Matters

Docker's bind-mount behavior creates a directory when the target path does not exist on the host. Filebrowser then fails with `open /database/filebrowser.db: is a directory`. Creating an empty file with `touch` before any `docker` command runs prevents this and ensures the mount behaves correctly.
