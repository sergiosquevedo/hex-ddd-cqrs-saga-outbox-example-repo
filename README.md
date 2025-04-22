# Food Ordering System

This project was developed as part of the course [Microservices Clean Architecture, DDD, SAGA, Outbox, Kafka & Kubernetes on Udemy.](https://sngular.udemy.com/course/microservices-clean-architecture-ddd-saga-outbox-kafka-kubernetes/learn/lecture/31152934#overview)

It contains the development of a food ordering system based on microservices, following principles of **Clean Architecture** and **Hexagonal Architecture**. The project implements advanced patterns such as **SAGA**, **Outbox**, and **CQRS**, and integrates technologies like **Apache Kafka** and **Spring Boot**.

## Project Content

### Main Technologies and Tools
- **Java**: Primary language of the project.
- **Spring Boot**: Framework for microservices development.
- **Maven**: Dependency management and project build tool.
- **Apache Kafka**: Distributed messaging system for microservices communication.
- **PostgreSQL**: Relational database used in the system.
- **Docker Compose**: Container orchestration for local deployment.
- **Kafka UI**: Tool for visualization and management of Kafka clusters.

### Implemented Patterns and Principles
- **Clean Architecture**: Separation of concerns into layers to facilitate maintainability and scalability.
- **Hexagonal Architecture**: Isolation of the business core through ports and adapters.
- **SAGA**: Management of distributed transactions in microservices.
- **Outbox**: Ensures consistency between the database and events published to Kafka.
- **CQRS**: Separation of read and write operations to optimize performance.

## Project Structure

The project is divided into multiple microservices, each with specific responsibilities. Some of the main microservices include:

- **Order Service**: Order management.
- **Payment Service**: Payment processing.
- **Restaurant Service**: Restaurant approval management.
- **Customer Service**: Customer management.

Each microservice follows clean and hexagonal architecture principles, ensuring high cohesion and low coupling.

## Setup and Deployment

### Prerequisites
- **Docker** and **Docker Compose** installed.
- **Java 17** or higher.
- **Maven** installed.

### Steps to Test the Services
#### Build the microservices:
`mvn clean install`  
The `install` phase is necessary because it is the phase where `AVRO` objects are generated.

#### Start the services with Docker Compose:
**Kafka Cluster (KRaft):**  
`docker-compose -f common.yml -f kafka_cluster.yml up`  

`kafka_cluster.yml` contains everything related to the Kafka cluster. It will spin up 3 Brokers (controller, bootstrap), create the necessary topics for the service, and launch a graphical tool to navigate the cluster.

**PostgreSQL & PgAdmin**  
`docker-compose -f common.yml -f postgres.yml up`

#### Access the tools:
Kafka UI: http://localhost:9000  
PgAdmin: http://localhost:5050

