# Docker

`docker pull nginx`

`docker cp docker-nginx:/etc/nginx/conf.d/default.conf default.conf`

`docker run --name docker-nginx -p 8080:8080 -v ~/Development/SandBox/3fs/docker:/usr/share/nginx/html -v ~/Development/SandBox/3fs/docker/default.conf:/etc/nginx/conf.d/default.conf -d nginx`

## Docker Hub

`docker images`

`docker tag dbfc48660aeb alko89/nginx-html`

`docker push alko89/nginx-html`

### Pull container from Docker Hub

`docker pull alko89/nginx-html`

`docker run --name docker-nginx -p 8080:8080 -d alko89/nginx-html`
