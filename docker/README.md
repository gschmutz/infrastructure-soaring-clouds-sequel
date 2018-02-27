# Infrastructure for local development


In order for the Elasticsearch docker container to start successfully, the following setting has to be applied on the Linux docker host:

```bash
sudo sysctl -w vm.max_map_count=262144
```

Set the environment variable DOCKER_HOST_IP to the IP address of your docker host:
```bash
EXPORT DOCKER_HOST_IP=<IP address of your Docker Host>
```

Start the complete environment in the background (-d switch)
```bash
docker-compose up -d
```

check if the services are running
```bash
docker-compose ps
```

if you want to see the logs of the services
```bash
docker-compose logs
```

of for a specific service
```bash
docker-compose logs connect
```

The following web application are available, asuming that docker is running on localhost....

* Confluent Control Center: [http://localhost:9021](http://localhost:9021)
* Schema Registry UI: [http://localhost:8002](http://localhost:8002)
* Kafka Connect UI: [http://localhost:8001](http://localhost:8001)
* Kibana: [http://localhost:5601](http://localhost:5601)

The following APIs are available

* Kafka Broker REST API: [http://localhost:8084](http://localhost:8084) ([doc](https://docs.confluent.io/current/kafka-rest/docs/api.html#api-v2))
* Schema Registry REST API: [http://localhost:8081](http://localhost:8081) ([doc](https://docs.confluent.io/current/schema-registry/docs/api.html#overview))
