# Testing environments
This repo contains following images:
Kafka, Zookeeper, Kinetica

# Start the environment
```docker-compose up -d```

# Quick test of Kafka
## create a topic "test"
```docker exec -it kafka-lippo-broker /opt/kafka/bin/kafka-topics.sh --create --zookeeper 172.18.0.2:2181 --replication-factor 1 --partitions 1 --topic test```
## run producer
```docker exec -it kafka-lippo-broker /opt/kafka/bin/kafka-console-producer.sh --broker-list localhost:9092 --topic test```
## run consumer
```docker exec -it kafka-lippo-broker /opt/kafka/bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning```
