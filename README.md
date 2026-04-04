# Kafka-Event-Driven-Order-Processing-Platform
A production-style, event-driven microservices system built using Node.js, Kafka and PostgreSQL demonstrating distributed systems concepts such as event sourcing, idempotency, outbox pattern and fault-tolerant processing

# Overview 
This project simulates a real-world order processing pipeline where services communicate asynchronously using Kafka.

# Architecture 
High-level flow 
1. Client creates an order via API 
2. Order is stored in PostgreSQL
3. Event is written to Outbox table (same transaction)
4. Outbox publisher sends event to Kafka 
5. Downstream services process events independently 

# Services 
- Order API -> Creates orders
- Outbox Publisher -> Publishes events to Kafka 
- Payment Service -> Processes payments 
- Inventory Service -> Reserves Inventory 
- Notification Service -> Generates Notifications 

# Tech stack 
- Backend: Node.js (Fastify + Typescript)
- Messaging: Apache Kafka (KafkaJS)
- Database: PostgreSQL 
- Infra: Docker + Docker Compose 
- Logging: Pino 
