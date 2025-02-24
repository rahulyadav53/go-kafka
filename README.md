
Apache Kafka with GO using Sarama by IBM.

HOW TO RUN

Install Docker and Docker Compose

Run docker-compose up -d in the root directory. This will start Apache Kafka and Zookeeper

Run go mod tidy in the root directory

Run go run producer/producer.go to start the producer which is a REST API listening on port 3000


HOW TO TEST IT!

Send a POST request to localhost:3000 using the below CURL Commands

curl --location --request POST '0.0.0.0:3000/api/v1/comments' \
--header 'Content-Type: application/json' \
--data-raw '{ "text":"message 1" }'

curl --location --request POST '0.0.0.0:3000/api/v1/comments' \
--header 'Content-Type: application/json' \
--data-raw '{ "text":"message 2" }'