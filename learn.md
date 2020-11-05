# kafka 学习指南

## 基本命令

- 列出topic
> `./kafka-topics.sh --zookeeper 192.168.0.38:2181 --list`

- 查看kafka某个topic的信息

> `./kafka-topics.sh --describe --zookeeper 192.168.0.38:2181 --topic topic1`

- 创建新的topic

> `./kafka-topics.sh --create --zookeeper 192.168.0.38:2181 --replication-factor 3 --partitions 3 --topic topic1`

- 调整topic分区

> `./kafka-topics.sh --alter --zookeeper 192.168.0.38:2181 --topic topic1 --partitions 6`

> kafka的topic分区数 **只能调大** 而不能调小

- 调整topic副本数

> `./kafka-reassign-partitions.sh --zookeeper 192.168.0.38:2181 --reassignment-json-file increase-replication-factor.json --execute`

> 需要创建调整分区副本的json文件,根据文件配置设置副本数

- 查看consumer group列表

> `./kafka-consumer-groups.sh --zookeeper 192.168.0.38:2181 --list`
或 `./kafka-consumer-groups.sh --new-consumer --bootstrap-server 192.168.0.38:9092 --list`