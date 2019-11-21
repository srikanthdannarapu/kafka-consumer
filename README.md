# kafka-consumer

#start zookeper

navigate to C:\Program Files\kafka_2.12-2.3.1\bin\windows new cmd

run the below command to start zookeeper instance

zookeeper-server-start.bat C:\Users\sreekanth\Desktop\kafka_2.12-2.3.1\config\zookeeper.properties


#start kafka server
navigate to C:\Program Files\kafka_2.12-2.3.1\bin\windows on new cmd

run the below command to start kafka server
kafka-server-start.bat C:\Users\sreekanth\Desktop\kafka_2.12-2.3.1\config\server.properties


#publish message on to topic SRI_TOPIC



navigate to C:\Users\sreekanth\Desktop\kafka_2.12-2.3.1\bin\windows on new cmd

kafka-console-producer.bat --broker-list localhost:9092 --topic SRI_TOPIC

publish a message on to topic (SRI_TOPIC) say ex: hello world, this message is seen in app logs

#create new 2nd topic JSONTOPIC and publish josn on this 2nd topic

open new cmd and create new topic with below command

kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic JSONTOPIC

then run the producer on the topic JSONTOPIC
kafka-console-producer.bat --broker-list localhost:9092 --topic JSONTOPIC

publish a json message on to topic (JSONTOPIC) say ex: {"name": "Srikanth", "dept": "Java"}, this message is seen in app logs
