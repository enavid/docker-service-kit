
# 🐳 Docker Service Kit

A curated collection of ready-to-run Docker Compose stacks for common development and infrastructure services. This kit provides simple, consistent, and well-documented configurations to help developers spin up essential tools quickly.

## 📦 What's Inside

Each folder in this repository contains a separate Docker Compose stack with:

- `docker-compose.yml`
- `.env` (or `.env.example`)
- `README.md` with full usage instructions
- Optional configuration files (e.g., JSON, volume folders)

| Service Stack              | Description                                        |
|---------------------------|----------------------------------------------------|
| [filebrowser](https://github.com/enavid/docker-service-kit/tree/main/filebrowser) | Web-based file manager                     |
| [kafka-kafdrop-zookeeper](https://github.com/enavid/docker-service-kit/tree/main/kafka-kafdrop-zookeeper) | Kafka stack with Kafdrop UI and Zookeeper |
| [kafka-zookeeper-kafka-ui](https://github.com/enavid/docker-service-kit/tree/main/kafka-zookeeper-kafka-ui) | Kafka stack with modern Kafka UI         |
| [mariadb](https://github.com/enavid/docker-service-kit/tree/main/mariadb)       | Lightweight MariaDB SQL server             |
| [mysql-phpmyadmin](https://github.com/enavid/docker-service-kit/tree/main/mysql-phpmyadmin) | MySQL with phpMyAdmin UI                 |
| [nginx-proxy-manager](https://github.com/enavid/docker-service-kit/tree/main/nginx-proxy-manager) | Simple Nginx reverse proxy manager UI   |
| [postgresql-pgadmin](https://github.com/enavid/docker-service-kit/tree/main/postgresql-pgadmin) | PostgreSQL with pgAdmin for DB management |
| [redis-redis-insight](https://github.com/enavid/docker-service-kit/tree/main/redis-redis-insight) | Redis with RedisInsight visualization tool |

> ✨ More stacks will be added soon. Feel free to contribute or request additions!

---

## 🚀 Getting Started

1. Clone the repository:

```bash
git clone https://github.com/enavid/docker-service-kit.git
cd docker-service-kit
```

2. Choose a service folder (e.g., `redis-redis-insight`)

3. Follow the instructions in that folder’s `README.md`

---

## 📁 Folder Structure

```
docker-service-kit/
├── filebrowser/
├── kafka-kafdrop-zookeeper/
├── kafka-zookeeper-kafka-ui/
├── mariadb/
├── mysql-phpmyadmin/
├── nginx-proxy-manager/
├── postgresql-pgadmin/
├── redis-redis-insight/
└── ...
```

Each directory is self-contained and ready to be started using:

```bash
docker-compose --env-file .env up -d
```

---

## 🤝 Contributing

Want to add a new service or improve existing ones?

- Fork the repo
- Add your stack in a new folder
- Include a clear `README.md` and optionally an `.env.example`
- Open a pull request 🚀

---

## 🧠 Why Use This Kit?

- 🔧 Pre-configured and easy to launch
- 📚 Fully documented for beginners and pros
- 🧪 Perfect for testing, dev environments, or prototyping
- 💡 Easily extendable for any stack or service

---

## 📜 License

This project is licensed under the [GNU General Public License v3.0 (GPL-3.0)](https://www.gnu.org/licenses/gpl-3.0.html).

---

Made with ❤️ by [@enavid](https://github.com/enavid)
