
# Filebrowser Docker Stack

This project provides a Docker Compose setup for running **Filebrowser** — a simple, beautiful web interface to browse and manage files on your server.

## 📦 What's Included

- **Filebrowser:** Web-based file manager with role-based access and editing features.

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/enavid/docker-service-kit.git
cd docker-service-kit/filebrowser
```

### 2. Configure Environment (optional)

Edit the `.env` file to set correct UID and GID for your user:

```env
PUID=1000
PGID=1000
```

You can find your UID and GID with:

```bash
id -u
id -g
```

### 3. Start the service

```bash
docker-compose --env-file .env up -d
```

### 4. Access the Web UI

Open your browser and go to:

```
http://localhost:8095
```

Default credentials:
- **User:** `admin`
- **Password:** `admin`

You can change them in the Filebrowser settings panel.

## 🧠 Notes

- Filebrowser data is stored in `filebrowser.db`
- The `filebrowser.json` configures the port, root folder, and other settings
- Files are served from the local `./srv` folder

## 📚 Use Cases

- Managing files on remote/dev servers
- Replacing traditional FTP with modern web-based alternative
- Lightweight file management for internal networks

---

This setup allows you to run a beautiful file management UI locally with minimal effort.
