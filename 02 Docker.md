# Docker container

`docker pull nginx`

`docker cp docker-nginx:/etc/nginx/conf.d/default.conf default.conf`

Edit `default.conf`.

Create Dockerfile.

`docker build -t nginx-html:v1 .`

## Docker Hub

`docker login`

`docker images`

`docker tag CONTAINER_ID alko89/nginx-html`

`docker push alko89/nginx-html`

### Pull container from Docker Hub

`docker pull alko89/nginx-html`

`docker run --name docker-nginx -p 80:80 -d alko89/nginx-html`
