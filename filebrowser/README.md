# Filebrowser

A self-hosted web-based file manager running in Docker. Browse, upload, download, and manage files through a clean UI from any browser.

## Requirements

- Docker and Docker Compose installed
- A Linux host with `sudo` access

## Quick Start

```bash
# 1. Create and set ownership of the srv directory
mkdir -p ./srv
sudo chown -R $USER:$USER ./srv

# 2. Create the database file (must exist before Docker starts)
touch filebrowser.db
chmod 666 filebrowser.db

# 3. Initialize the database
docker compose run --rm filebrowser config init --database /database/filebrowser.db

# 4. Create the admin user
docker compose run --rm filebrowser users add admin admin --perm.admin --database /database/filebrowser.db

# 5. Start the service
docker compose up -d
```

Open `http://<server-ip>:8095` and log in with `admin` / `admin`.  
**Change the password immediately** from Settings → User Management.

---

## Configuration

Before starting, edit `.env` to match your environment:

```env
PUID=1000       # your user ID  →  run: id -u
PGID=1000       # your group ID →  run: id -g
FB_PORT=8095    # port exposed on the host
TZ=Asia/Tehran  # your timezone
```

`filebrowser.json` controls internal settings such as branding, database path, and root folder. You generally do not need to edit it.

---

## File Layout

```
.
├── docker-compose.yml    # service definition
├── filebrowser.json      # internal configuration
├── .env                  # environment variables (PUID, PGID, port, timezone)
├── filebrowser.db        # SQLite database — back this up regularly
└── srv/                  # files served by Filebrowser — back this up regularly
```

---

## Common Commands

```bash
# Start
docker compose up -d

# Stop
docker compose down

# Restart
docker compose restart filebrowser

# View live logs
docker compose logs -f filebrowser

# Pull latest image and restart
docker compose pull && docker compose --env-file .env up -d
```

---

## Reset Admin Password

If you lose access, reset the password without stopping the service:

```bash
docker exec -it filebrowser /filebrowser users update admin \
  --password "NewPassword123" \
  --database /database/filebrowser.db
```

---

## Production Hardening

- Place Filebrowser behind a reverse proxy (Nginx, Caddy, or Traefik) with a valid TLS certificate.
- Block port `8095` at the firewall so it is not reachable from the public internet.
- Use a strong, unique password and disable the default `admin` account after creating a personal admin account.
- Back up `filebrowser.db` and `srv/` on a regular schedule.

---

## Troubleshooting

**Container fails to start with "is a directory" error**  
Docker created a directory at `filebrowser.db` instead of a file. Remove it and re-run the setup:
```bash
sudo rm -rf filebrowser.db
touch filebrowser.db && chmod 666 filebrowser.db
```

**Cannot upload files**  
The `srv/` directory may have incorrect ownership. Fix it with:
```bash
sudo chown -R $USER:$USER ./srv
```

**Port already in use**  
Change `FB_PORT` in `.env` to a free port and restart:
```bash
docker compose down && docker compose up -d
```
