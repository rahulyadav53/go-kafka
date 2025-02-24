
Apache Kafka with GO using Sarama by IBM.
This program implements a Kafka-based message queue system for handling user comments. It consists of a producer and a consumer. 
The producer, using Fiber, exposes an API endpoint (/api/v1/comments) to receive comments, serializes them into JSON, and sends them to a Kafka topic (comments). 
The consumer listens for messages from the Kafka broker, processes them, and prints the received messages.
Error handling and graceful shutdown mechanisms are included to ensure reliability. 

## HOW TO RUN

- Install Docker and Docker Compose

- Run docker-compose up -d in the root directory. This will start Apache Kafka and Zookeeper

- Run go mod tidy in the root directory

- Run go run producer/producer.go to start the producer which is a REST API listening on port 3000

- Run go run worker/worker.go to start the consumer


## HOW TO TEST IT!

Send a POST request to localhost:3000 using the below CURL Commands

```sh
curl --location --request POST '0.0.0.0:3000/api/v1/comments' \
--header 'Content-Type: application/json' \
--data-raw '{ "text":"message 1" }'

curl --location --request POST '0.0.0.0:3000/api/v1/comments' \
--header 'Content-Type: application/json' \
--data-raw '{ "text":"message 2" }'

```
