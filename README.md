# Instrucciones de uso de Apache kafka


Para levantar el servicio de zookeeper:
````
bin/zookeeper-server-start.sh config/zookeeper.properties
````

Para levantar el servicio de kafka:
````
bin/kafka-server-start.sh config/server.properties
````

Para crear una lista en el servicio de kafka:
````
bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic test
````

Para ver las listas creadas en ese servicio de kafka:
````
bin/kafka-topics.sh --list --bootstrap-server localhost:9092 
````

Para activar la lista creada en ese servicio de kafka:
````
bin/kafka-console-producer.sh --broker-list localhost:9092 --topic test 
````

Para poner a la escucha un consumidor del servicio de kafka:
````
bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning
````

Para activar un source y un sink
````
bin/connect-standalone.sh config/connect-standalone-properties ./source.properties ./sink.properties
````
