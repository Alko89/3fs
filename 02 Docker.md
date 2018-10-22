# Docker container

Install docker `apt install docker.io`

Pull the offical nginx container `docker pull nginx`

Coppy the default configuration file from nginx container into your project directory:

`docker cp docker-nginx:/etc/nginx/conf.d/default.conf nginx.conf`

Edit and save `nginx.conf` configuration file.

Create Dockerfile that will copy `nginx.conf` and `index.html` foles in the container.

Build container image `docker build -t nginx-html:v1 .`

## Docker Hub

Login to Docker Hub `docker login`

List docker images `docker images` and tag the repository on Docker Hub with CONTAINER_ID of the newly created container `docker tag CONTAINER_ID alko89/nginx-html`

Push the container to repository `docker push alko89/nginx-html`

### Pull and run container from Docker Hub

`docker run --name nginx-html -p 80:80 -d alko89/nginx-html`
