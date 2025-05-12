# Kafka + Kafdrop + Zookeeper Docker Stack

This project provides a complete, ready-to-run Docker Compose setup for running Apache Kafka, Zookeeper, and Kafdrop — a web-based UI for viewing Kafka clusters. It is designed for developers and testers who need an easy way to spin up a Kafka environment locally for exploration or integration.

## 📦 What's Included

- **Zookeeper:** Manages coordination for Kafka brokers.
- **Kafka:** Distributed event streaming platform for building real-time data pipelines.
- **Kafdrop:** A lightweight web UI for inspecting Kafka topics, partitions, consumer groups, and more.

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/enavid/docker-service-kit.git
cd docker-service-kit/kafka-kafdrop-zookeeper
```

### 2. Configure Environment (optional)

Edit the `.env` file if you want to change ports, Kafka broker ID, or other configurations.

### 3. Start the services

```bash
docker-compose --env-file .env up -d
```

### 4. Access the Kafdrop UI

Once all containers are running, open your browser and navigate to:

```
http://localhost:9000
```

This UI allows you to:
- View Kafka topics
- Inspect partitions and their leaders
- Monitor consumer groups
- Check configurations and metadata

## 🔄 Data Persistence

Kafka data will be stored locally in `./kafka_data`. This volume can be reused or deleted based on your needs.

## 🧠 Notes

- Kafka listens internally on `29092` for Docker network communication and externally on `9092` for host access.
- Kafdrop connects directly to the Kafka broker at `kafka:29092`.

## 📚 Use Cases

- Ideal for testing Kafka-based microservices
- Learning Kafka with a simple local setup
- Visual debugging of Kafka message flow and cluster behavior

---

This setup eliminates the complexity of manual Kafka configuration and gives you a fully functioning Kafka environment in minutes.