# Adminer Docker Project

This project contains a Dockerfile for running [Adminer](https://www.adminer.org/), a full-featured database management tool written in PHP.

## Building the Docker Image

To build the Docker image, run the following command in the directory containing the Dockerfile:

```bash
docker build -t adminer -f Dockerfile.adminer .
```

This will create a Docker image named adminer.

## Running the Docker Image
To run the Docker image, use the following command:

```bash
docker run -p 8080:8080 adminer
```

This will start a container from the adminer image and map port 8080 in the container to port 8080 on your host machine.

## Accessing Adminer
Once the container is running, you can access Adminer at http://localhost:8080. You can log in with your database credentials to manage your database.

## Pushing the Docker Image to Github Container Registry (GHCR)
If you want to push the Docker image to GCR, you can do so with the following commands:

```bash
# Tag the Docker image with the GCR registry name
docker tag adminer:latest ghcr.io/seaosinc/adminer:latest

# Push the Docker image to GCR
docker push ghcr.io/seaosinc/adminer:latest
```