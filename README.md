# REAME or not



### Dependncies

- spark-streaming-kafka-0-8_2.11-2.0.1.jar
	- kafka_2.11-0.8.2.2.jar
		- metrics-core-2.2.0.jar

### Train offline model

```
# save model to file
$SPARK_HOME/bin/spark-submit spark_training.py
```

### Demo

-  Start zookeeper & Kafka

```
sudo /usr/local/zookeeper/bin/zkServer.sh start
sudo /usr/local/kafka/bin/kafka-server-start.sh /usr/local/kafka/config/server.properties &
```

- Start Redis

```
redis-server
```

- Start Spark Streaming

```
$SPARK_HOME/bin/spark-submit stream_predict.py
```

- Start Kafka Producer

```
python auto_producer.py
```

- Start flask app

```
cd flask
python run.py

# in the browser
localhost:5000
```

-  Stop zookeeper & Kafka

```
sudo /usr/local/zookeeper/bin/zkServer.sh stop
sudo /usr/local/kafka/bin/kafka-server-stop.sh
```