
# PostgreSQL + pgAdmin Docker Stack

This project provides a complete, ready-to-run Docker Compose setup for running **PostgreSQL** and **pgAdmin** — a web-based UI for managing PostgreSQL databases. It is designed for developers and testers who need a quick and convenient way to spin up a PostgreSQL environment locally.

## 📦 What's Included

- **PostgreSQL:** An advanced open-source relational database system.
- **pgAdmin:** A browser-based tool for managing PostgreSQL with a visual interface.

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/enavid/docker-service-kit.git
cd docker-service-kit/postgres-pgadmin
```

### 2. Configure Environment (optional)

Edit the `.env` file if you want to change database credentials or pgAdmin login info.

### 3. Start the services

```bash
docker-compose --env-file .env up -d
```

### 4. Access the pgAdmin UI

Once all containers are running, open your browser and navigate to:

```
http://localhost:8081
```

Login using the credentials from your `.env` file:
- **Email:** `PGADMIN_DEFAULT_EMAIL`
- **Password:** `PGADMIN_DEFAULT_PASSWORD`

## 🔄 Data Persistence

PostgreSQL data will be stored locally in `./docker-volumes/postgres`. This volume can be reused or deleted based on your needs.

## 🧠 Notes

- PostgreSQL listens on `5432` for host access.
- pgAdmin connects to PostgreSQL via internal Docker networking (`postgres-db`).

## 📚 Use Cases

- Ideal for developing PostgreSQL-based apps
- Testing queries and schema migrations
- Learning PostgreSQL with a visual tool

---

This setup eliminates the complexity of local DB configuration and gives you a full PostgreSQL environment in minutes.
