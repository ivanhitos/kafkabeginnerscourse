# kafkabeginnerscourse

Notes from the course.

1. Install kafka following ``https://kafka.apache.org/quickstart``
```
apt update
apt install openjdk-8-jdk

export PATH=/home/ubuntu/kafka_2.12-2.3.0-bin:$PATH
wget https://www-eu.apache.org/dist/kafka/2.3.0/kafka_2.12-2.3.0.tgz

tar -zxvf kafka_2.12-2.3.0.tgz
```
2. Test
```
cd /home/ubuntu/kafka_2.12-2.3.0/
./bin/kafka-topics.sh
```

3. Configuration
```
cd /home/ubuntu/kafka_2.12-2.3.0/
mkdir data/kafka data/zookeepeer
vi config/server.properties       # add data dir
vi config/zookeeper.properties    # add data dir
```

4. Start. We need one command per shell
```
cd /home/ubuntu/kafka_2.12-2.3.0/
kafka-server-start.sh config/server.properties
zookeeper-server-start.sh config/zookeeper.properties
```

5. Test consumer. We need one command per shell.
```
kafka-console-consumer.sh --bootstrap-server 127.0.0.1:9092 --topic first_topic
kafka-console-producer.sh --broker-list 127.0.0.1:9092 --topic first_topic
```

5. Test java producer
```
java -jar kafkabeginnerscourse.jar
```
