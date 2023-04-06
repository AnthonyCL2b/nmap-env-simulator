# nmap-env-simulator
Test environment for experimenting with the functionality of nmap using Docker containers

## Requirements
To use this environnment, you need to have installed on your machine:
- Docker
- Docker-compose


## How to use it ?
To build the Docker image, save the above Dockerfile to a directory and run the following command in the same directory as the Dockerfile:

```
docker build -t nmap-test .
```

To build the container that hosts all the service images that will allow us to test nmap, use the following command:

```
docker-compose up -d
```

This command is also used to create a network linking all images.

Now we need to run a terminal in the container hosting nmap and add it to the network of service images so that nmap can reach them:

```
docker run -it --name nmap-test --network my-network nmap-test
```