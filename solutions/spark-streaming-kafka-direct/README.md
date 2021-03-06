# Spark Streaming Kafka 0.10 Direct

The example complements my [Mastering Apache Spark 2.0 Notes](https://jaceklaskowski.gitbooks.io/mastering-apache-spark/content/spark-streaming/spark-streaming-kafka-KafkaUtils.html) about Kafka 0.10 Direct API support in Spark Streaming 2.0.

## Running Example

```
// Terminal 1
// Start Zookeeper.
./bin/zookeeper-server-start.sh config/zookeeper.properties
```

```
// Terminal 2
// Start a Kafka server
./bin/kafka-server-start.sh config/server.properties
```

```
// Terminal 3
$ sbt package

// Use whatever Spark directory you chose at installation
$ ~/dev/oss/spark/bin/spark-submit --packages org.apache.spark:spark-streaming-kafka-0-10_2.11:2.0.2 target/scala-2.11/spark-streaming-kafka-direct_2.11-1.0.jar
```

```
// Terminal 4
// Start publishing records (strings) to topic1

$ ./bin/kafka-console-producer.sh --topic topic1 --broker-list localhost:9092
```

Monitor the streaming application in the Spark UI at [http://localhost:4040/streaming/](http://localhost:4040/streaming).

