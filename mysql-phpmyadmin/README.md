# MySQL + phpMyAdmin Docker Stack

This project provides a quick and easy setup for running **MySQL** alongside **phpMyAdmin** using Docker.
It’s ideal for development environments where you need a visual database interface to interact with your MySQL server.

## 📦 What's Included

- **MySQL (latest):** runs on Docker with persistent storage
- **phpMyAdmin:** accessible via your browser to manage your database easily

## 🚀 How to Use

### 1. Clone the repository:

```bash
git clone https://github.com/enavid/docker-service-kit.git
cd docker-service-kit/mysql-phpmyadmin
```

### 2. Update `.env` file if needed

Edit database name, root password, and port in `.env`.

### 3. Run the stack:

```bash
docker-compose up -d
```

### 4. Access phpMyAdmin:

Open your browser and navigate to:

```
http://localhost:8080
```

- **Username:** `root`
- **Password:** from your `.env` file

You can now manage your MySQL database visually.

## 🧊 Data Persistence

All MySQL data is stored locally in `./docker-volumes/mysql_data`. You can safely stop and restart containers without losing data.
