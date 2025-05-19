
# MariaDB Docker Stack

This project provides a complete, ready-to-run Docker Compose setup for running **MariaDB** — a popular open-source relational database. It is designed for developers who want a fast and easy way to run MariaDB locally.

## 📦 What's Included

- **MariaDB:** A community-developed fork of MySQL providing an open-source relational database solution.

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/enavid/docker-service-kit.git
cd docker-service-kit/mariadb
```

### 2. Configure Environment (optional)

Edit the `.env` file to change the database name, user, or password.

### 3. Start the service

```bash
docker-compose --env-file .env up -d
```

## 🔄 Data Persistence

MariaDB data will be stored locally in:

```
./docker-volumes/mariadb
```

This ensures that your data is preserved across container restarts.

## 🧠 Notes

- MariaDB listens on port `3306` for host access.
- You can connect using any MySQL-compatible client with the credentials defined in the `.env` file.

## 📚 Use Cases

- Developing and testing MySQL-compatible apps locally
- Learning SQL and relational databases
- Lightweight alternative to MySQL for local environments

---

This setup gives you a ready-to-use MariaDB server in seconds with zero manual installation.
