# crypto_data_streaming
streaming data from coinmarket to a database via Kafka

update /opt/kafka_2.13-3.8.0/config/server.properties and update listeners=PLAINTEXT://ec2-13-38-70-25.eu-west-3.compute.amazonaws.com:9092 - check the DNS for the ec2 instance (as the dns may change between restarts of the VM) 

update app_crypto_data_stream.py and update producer = KafkaProducer(bootstrap_servers=['ec2-15-237-176-35.eu-west-3.compute.amazonaws.com:9092']) - check the DNS for the ec2 instance (as the dns may change between restarts of the VM) 

./service_zookeeper-server-stop.sh 
./service_zookeeper-server-start.sh 
 
./service_kafka-server-stop.sh 
./service_kafka-server-start.sh  

python app_source_variables.sh 
python app_crypto_data_stream.py 

