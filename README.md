**Use corda 3.3**

**Docker 17.09 and up is required for this Dockerfile.**

Docker configuration files to create and spin up Docker images for a few Corda Nodes (banka/bankb/bankc), Notary and one CordApp.

The docker image is based on Alpine/OpenJDK (https://hub.docker.com/_/openjdk/)

## Usage (automatic way - using docker compose)

* Check Dockerfile and docker-compose.yml (e.g. to adjust version or exposed ports)
* use the network bootstrap for generate your nodes
* Bootstrapping a test network The Corda Network Bootstrapper can be downloaded from here 
* Create a directory containing a node config file, ending in “_node.conf”, for each node you want to create. Then run the following command: `java -jar network-bootstrapper-VERSION.jar <nodes-root-dir>`
* `docker-compose build` - to build base Corda images for Corda Node/Networkmap/Notary
* `docker-compose up` - to spin up all Corda containers (Nodes + Networkmap + Notary)
* `docker exec -it banka /bin/sh` - to log in to one of the running Node containers

## Corda configuration
At the moment java options are put into **corda_docker.env**. All the others are in Dockerfile/docker_compose.yml
