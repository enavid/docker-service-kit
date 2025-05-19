
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
| [`kafka-kafdrop-zookeeper`](./kafka-kafdrop-zookeeper) | Kafka stack with Kafdrop UI and Zookeeper |
| [`postgres-pgadmin`](./postgres-pgadmin)             | PostgreSQL with pgAdmin for DB management |
| [`redis-redisinsight`](./redis-redisinsight)         | Redis with RedisInsight visualization tool |
| [`mariadb`](./mariadb)                               | Lightweight MariaDB SQL server             |
| [`kafka-zookeeper-kafka-ui`](./kafka-zookeeper-kafka-ui) | Kafka stack with modern Kafka UI         |
| [`filebrowser`](./filebrowser)                       | Web-based file manager                     |

> ✨ More stacks will be added soon. Feel free to contribute or request additions!

---

## 🚀 Getting Started

1. Clone the repository:

```bash
git clone https://github.com/enavid/docker-service-kit.git
cd docker-service-kit
```

2. Choose a service folder (e.g., `redis-redisinsight`)

3. Follow the instructions in that folder’s `README.md`

---

## 📁 Folder Structure

```
docker-service-kit/
├── kafka-kafdrop-zookeeper/
├── postgres-pgadmin/
├── redis-redisinsight/
├── mariadb/
├── kafka-zookeeper-kafka-ui/
├── filebrowser/
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

This project is open-source under the [MIT License](LICENSE).

---

Made with ❤️ by [@enavid](https://github.com/enavid)
