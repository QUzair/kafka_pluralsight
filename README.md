
## 4. Running Kafka brokers and Zookeeper

```
 bin/zookeeper-server-start.sh config/zookeeper.properties
bin/kafka-server-start.sh config/s1.properties
bin/kafka-server-start.sh config/s2.properties
```

## 5. Schema Registry 

Start Schema Registry - Run w/o Zookeeper
```
➜   bin/schema-registry-start config/schema-registry.properties
```

## 6. KSQL CLI

Create KSQL Server that connects to brokers, bootstrap servers 
```
bin/ksql-server-start config/ksql-server.properties
```

Run cli 
```
bin/ksql
```

## 7. Running SQL Connector, 

Initiate Connector Consumer that consumes orders and persists to Mysql db

```
➜  kafka_2.13-3.2.0 bin/connect-standalone.sh config/connect-standalone.properties config/mysql-connector.properties
```

Produce Order events 
```
bin/kafka-console-producer.sh --broker-list localhost:9092 --topic orders
```
