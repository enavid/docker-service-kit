# Nginx Proxy Manager + MariaDB Docker Stack

This project provides a full Docker Compose setup for running **Nginx Proxy Manager (NPM)** with **MariaDB**. It allows developers and system administrators to manage Nginx proxy hosts and SSL certificates via a clean and user-friendly web UI — with zero need to manually edit config files.

## 📦 What's Included

- **Nginx Proxy Manager (jc21/nginx-proxy-manager)**: A powerful interface for managing Nginx-based reverse proxies, redirections, and SSL.
- **MariaDB (jc21/mariadb-aria)**: Reliable and optimized database backend for NPM.

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/enavid/docker-service-kit.git
cd docker-service-kit/nginx-proxy-manager
```

### 2. Configure Environment (Optional)

The `.env` file contains default settings such as database credentials and port mappings. You can modify it to fit your environment:

```env
MYSQL_ROOT_PASSWORD=...
NGINX_PORT_HTTP=80
NPM_UI_PORT=81
...
```

### 3. Start the Stack

```bash
docker-compose --env-file .env up -d
```

### 4. Access the Web UI

Open your browser and go to:

```
http://localhost:81
```

> Default credentials (only on first launch):
>
> - **Email**: `admin@example.com`
> - **Password**: `changeme`

> You will be prompted to change the default login after signing in.

## 🔐 Features

- Reverse proxy for any local or remote service
- Free SSL certificate provisioning using Let's Encrypt
- HTTP to HTTPS redirection
- Access control (basic auth)
- Easily manage wildcard or custom domains

## 💾 Data Persistence

- All persistent data is stored under `./docker-volumes/data`, `./docker-volumes/mysql`, and `./docker-volumes/letsencrypt`
- You can safely stop and restart the stack without losing configuration

## 📚 Use Cases

- Hosting multiple services behind a secure reverse proxy
- Automating SSL certificate management
- Centralized control panel for self-hosted applications

---

This stack is perfect for self-hosters, developers, and DevOps engineers who want an easy and maintainable reverse proxy solution.

🔧 **Built with simplicity and power in mind.**
