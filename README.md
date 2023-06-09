# Confluent Cloud Connect
Quicky get access to Confluent Cloud with this script. This repo runs a standalone Kafka connect worker which is preconfigured to connect to a Confluent Cloud instance.
It includes two source connectors:

- Confluent syslog source connector: https://www.confluent.io/hub/confluentinc/kafka-connect-syslog. You can forward syslog to this instance and it will produce in Confluent Cloud.
- Kafka File Stream Connector: https://docs.confluent.io/home/connect/filestream_connector.html. See below details for adding files into Confluent Cloud

To get started:
```
1. git clone https://github.com/JohnnyMirza/CCloud_Connect.git
2. edit the .env file and fill in your credentials. To get the details Login to Confluent Cloud then to your Environment, and follow steps below:
-CLOUD_URL: cluster->Settings->Bootstrap server
-CLOUD_TOKEN: cluster->API keys
-CLOUD_SECRET: cluster->API keys
-SCHEMA_REGISTRY_URL: Environment->Schema Registry->API endpoint
-SCHEMA_REGISTRY_BASIC_AUTH: Environment->Schema Registry->API credentials (e.g. SCHEMA_REGISTRY_BASIC_AUTH='key':'secret')
3. Create your topic in Confluent Cloud e.g. KAFKA_TOPIC_NAME=? (see .env file)
4. echo (or source) .env
4. docker-compose up -d
```

This repo includes a neo4j source connector, and snowflake sink connector. Fill in connectivity details in:
```
-submit_neo4j.sh
-submit_snowflake.sh
```
