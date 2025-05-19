
# Redis + RedisInsight Docker Stack

This project provides a complete, ready-to-run Docker Compose setup for running **Redis** and **RedisInsight** — a web-based UI for managing Redis databases. It is designed for developers who want a simple and visual local Redis environment.

## 📦 What's Included

- **Redis:** An in-memory data store used as a database, cache, and message broker.
- **RedisInsight:** A browser-based tool for visualizing and managing Redis data structures.

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/enavid/docker-service-kit.git
cd docker-service-kit/redis-redisinsight
```

### 2. Start the services

```bash
docker-compose up -d
```

### 3. Access RedisInsight UI

Once the containers are running, open your browser and navigate to:

```
http://localhost:8082
```

Then:
- Add a new Redis database connection using `redis` as the hostname and `6379` as the port.

## 🔄 Data Persistence

Redis data will be stored locally in:

```
./docker-volumes/redis
```

RedisInsight data will be stored in:

```
./docker-volumes/redis-insight
```

## 🧠 Notes

- Redis is exposed on port `6379` for direct access.
- RedisInsight provides powerful visualization for keys, memory, and performance stats.

## 📚 Use Cases

- Debugging Redis-based applications
- Visual monitoring of keyspace and memory usage
- Learning and exploring Redis features with an intuitive UI

---

This setup lets you run Redis locally with full visibility and zero hassle.
