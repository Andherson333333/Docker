# Nginx Docker Configuration

This project contains the configuration to run Nginx in Docker, including a Dockerfile and a docker-compose.yml file.

## Table of Contents
* [What is Nginx?](#what-is-nginx)
* [Functions](#functions)
* [File Locations](#file-locations)
* [Structure for Docker Nginx](#structure-for-docker-nginx)
* [Building the Image](#building-the-image)

## What is Nginx?

Nginx (pronounced "engine-x") is an open-source web server and reverse proxy server. In addition to its primary function of serving static and dynamic web pages, Nginx is also commonly used as a reverse proxy and load balancer. It was created to address the issues of concurrency, performance, and efficient resource utilization.

## Functions

Common functions of Nginx:

1. Web server for static and dynamic content.
2. Reverse proxy for load balancing.
3. Handling HTTP/HTTPS requests.
4. SSL/TLS termination.
5. Caching of static and dynamic content.
6. Access control and authentication.
7. Content compression.
8. Redirections.
9. Detailed logging and monitoring.
10. Dynamic configuration with hot reloading.
11. Security with protection against DDoS attacks and other threats.

## File Locations

It's crucial to understand the role of different files within your Nginx container, as well as know the specific locations of these files.

### Important Locations

- `/usr/share/nginx/html`: static website
- `/etc/nginx/conf.d`: other configurations
- `/etc/nginx/nginx.conf`: main configuration

## Structure for Docker Nginx

![Nginx structure diagram](https://github.com/Andherson333333/Docker/blob/main/Ngnix/imagenes/nginix.JPG)

## Building the Image

Once the exchange files are configured, we proceed to place these files in the corresponding locations and generate the image using a Dockerfile. The key instruction in this process is COPY/ADD, which is used to copy files from the local machine to the Docker image's file system.

### Dockerfile

```dockerfile
FROM nginx:latest
COPY nginx.conf /etc/nginx/nginx.conf
COPY static-content /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

### Docker Compose

```yaml
version: '3'
services:
  nginx:
    image: nginx:alpine
    container_name: my-nginx
    ports:
      - "8080:80"
    volumes:
      - ./nginx/conf/nginx.conf:/etc/nginx/nginx.conf:ro
      - ./nginx/conf.d/default.conf:/etc/nginx/conf.d/default.conf:ro
      - ./static-content:/usr/share/nginx/html:ro
    restart: always
```

## Usage

To build and run the Nginx container:

1. Make sure you have Docker and Docker Compose installed.
2. Place your configuration files and static content in the corresponding directories.
3. Run `docker-compose up -d` to start the container in detached mode.

The Nginx server will be available at `http://localhost:8080`.
