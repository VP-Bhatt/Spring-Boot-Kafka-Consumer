# Spring Boot Kafka Consumer

This project demonstrates a **Kafka Consumer** application using **Spring Boot**. It enables consuming messages from Kafka topics, showcasing an easy integration with Apache Kafka for distributed messaging.

## Features

- **Spring Boot Integration**: Uses Spring Boot for streamlined configuration and management.
- **Kafka Consumer**: Reads messages from specified Kafka topics.
- **JSON Support**: Deserializes messages from JSON format for easy compatibility.
- **Configurable Topics**: Kafka topics are configurable via application properties.

## Prerequisites

- **Java 21** or higher
- **Apache Kafka**: A running Kafka instance
- **Maven**: For dependency management

## Configuration

The `application.yml` with Kafka details:

```yaml
spring:
  kafka:
    bootstrap-servers: localhost:29092
    consumer:
      key-deserializer: org.apache.kafka.common.serialization.StringDeserializer
      value-deserializer: org.apache.kafka.common.serialization.StringDeserializer
      group-id: my-consumer-group
```
## How It Works

- The consumer listens to a Kafka topic and processes messages in real-time.
- Messages are consumed based on the configured group ID and topic subscriptions.
- Future use cases can include processing messages for analytics, triggering events, or integrating with databases.

## Running the Application

1. **Start the Kafka broker and Zookeeper.**
2. **Build and run the application.**

### Starting Kafka Broker and Zookeeper

- Start Docker CLI or Docker Desktop to run the Docker daemon.
- Run the following command in the `docker` folder of the project to pull Kafka and Zookeeper images and run them using the `docker-compose.yml` configuration:

  ```bash
  docker-compose up -d

### Running Spring Boot Application

- Start the application by running it directly from the main `Application` class.

### Setup Offset Explorer

- Install **Offset Explorer** to visualize the data consumed from the producer.
- Download **Offset Explorer** from [here](https://www.kafkatool.com/download.html).
- Setup Offset Explorer by providing the host information.
- In our case, the host is `localhost:29092`.
- Now, you can visualize the messages consumed from Apache Kafka topics.