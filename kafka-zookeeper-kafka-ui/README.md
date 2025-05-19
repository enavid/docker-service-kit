
# Kafka + Zookeeper + Kafka UI Docker Stack

This project provides a complete Docker Compose setup for running **Apache Kafka**, **Zookeeper**, and **Kafka UI** — a modern web-based interface for managing Kafka clusters. Ideal for developers working with real-time data pipelines.

## 📦 What's Included

- **Zookeeper:** Manages coordination for Kafka brokers.
- **Kafka:** A distributed streaming platform.
- **Kafka UI:** A lightweight, user-friendly web interface to inspect and manage Kafka clusters.

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/enavid/docker-service-kit.git
cd docker-service-kit/kafka-zookeeper-kafka-ui
```

### 2. Configure Environment (optional)

Edit the `.env` file to adjust port numbers or Kafka connection settings.

### 3. Start the services

```bash
docker-compose --env-file .env up -d
```

### 4. Access Kafka UI

Once containers are up, open your browser and go to:

```
http://localhost:8083
```

From here you can:
- View topics and partitions
- Produce and consume messages
- Monitor broker status and consumer groups

## 🔄 Data Notes

This setup does **not** persist data locally by default. Add volume mappings if persistence is needed.

## 🧠 Notes

- Kafka is exposed on `9092` for external connections and `29092` for internal Docker communication.
- Kafka UI connects using the internal `kafka:29092` address.

## 📚 Use Cases

- Developing Kafka-based apps
- Monitoring Kafka clusters visually
- Learning Kafka architecture with ease

---

Get started with Apache Kafka in minutes using this pre-configured environment.
