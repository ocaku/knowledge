### kafka
tar -xzf kafka_2.11-0.10.2.0.tgz

启动kafka
>bin/zookeeper-server-start.sh config/zookeeper.properties
>bin/kafka-server-start.sh config/server.properties

创建topic
>bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
>bin/kafka-topics.sh --list --zookeeper localhost:2181

topic 测试
producer
  >bin/kafka-console-producer.sh --broker-list localhost:9092 --topic test
consumer
> bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning
