# storm-docker
This will be used to setup the images that will be used to run Storm, Kafka, Zookeeper, MongoDB, and Redis.

## Setup Storm
 * Clone this git project
 * Run "./rebuild.sh"
 * Run "fig up -d"
 
## Configuration
 * Edit fig.xml and make sure the following KAFKA_ADVERTISED_HOST_NAME is set to your docker_host ip

## Validating running instances
 * fig ps
 * fig logs
 
## Stopping running instances
 * fig stop
 * fig kill
