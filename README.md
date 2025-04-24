# 🌍 The Band Communication and Change Data Capture Infrastructure

This project sets up an infrastructure to capture real-time changes in a PostgreSQL database (e.g., **insert**, **update**, **delete**) and publish them to **Apache Kafka** topics using **Debezium**.

![Debezium Architecture](debezium-architecture.png "Debezium")

---

## 🚀 Goal

Enable **Change Data Capture (CDC)** for PostgreSQL, allowing systems to react to data changes instantly via a messaging queue. This supports integration, synchronization, analytics, and auditing use cases.

---

## ⚙️ Requirements

- [Docker Compose](https://docs.docker.com/compose/)

---

## 🔧 Installation

1. Create a `.env` file in the project root with the following content:

```env
DEBEZIUM_VERSION=2.0
COMPOSE_PROJECT_NAME=immigrant-cdc-infrastructure
```

> ⚠️ Note: Remove any spaces around the `=` signs in your `.env` file.

2. Start the infrastructure with:

```bash
docker-compose up -d
```

Once started, you can access the Kafdrop UI at:

📍 [http://localhost:19000](http://localhost:19000)

---

## 🛠️ Stack Overview

| Component     | Description                                         |
|---------------|-----------------------------------------------------|
| **PostgreSQL** | The source database being monitored for changes     |
| **Apache Kafka** | The message broker used to propagate the changes |
| **Debezium**   | The CDC engine that reads changes from PostgreSQL  |
| **Kafdrop**    | A Kafka web UI for inspecting topics and messages  |

---

## 📚 References & Learning Materials

1. 📘 [Debezium GitHub Examples](https://github.com/debezium/debezium-examples/tree/main/tutorial)  
2. 📖 [Introduction to Debezium – Baeldung](https://www.baeldung.com/debezium-intro)  
3. 🛠️ [Setting Up Kafdrop with Kafka Using Docker Compose](https://medium.com/azure-na-pratica/apache-kafka-kafdrop-docker-compose-montando-rapidamente-um-ambiente-para-testes-606cc76aa66)
