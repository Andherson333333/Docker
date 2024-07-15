# Dockerfile Usage Guide

## Table of Contents
* [What is a Dockerfile?](#what-is-a-dockerfile)
* [Creating a Dockerfile](#creating-a-dockerfile)
* [Content inside the Dockerfile](#content-inside-the-dockerfile)
* [Building the image](#building-the-image)
* [Verifying the image](#verifying-the-image)

## What is a Dockerfile?
A Dockerfile is a controller for customizing Docker images.

### Dockerfile Parameters
Here are some of the key Dockerfile parameters:

- `FROM`: Specifies the base image to work with. You can add tags, and by default, it uses 'latest'. Syntax: `FROM image:Tag`
- `RUN`: Executes commands inside the container. Note that it's not interactive, so for commands that require confirmation, use `-y` (e.g., for Debian). As each RUN creates a new layer, it's recommended to combine multiple commands in a single RUN instruction.
- `CMD`: `["executable","param1","param2"]` (executive form, preferred). Only one CMD instruction can be effective in a Dockerfile. This execution is not persistent and can be overridden.
- `ENTRYPOINT`: Similar to CMD but persistent and cannot be changed. Often used to run background applications or set up environment variables.
- `COPY/ADD`: Used to copy files to the container. Requires source:destination. ADD is more powerful as it can copy from URLs and extract compressed files.
- `ENV`: Sets environment variables.
- `EXPOSE`: Informational, indicates which ports the container will listen on. Only takes effect with `docker run -p`.
- `LABEL`: Adds metadata to Docker objects.
- `USER`: Sets the UID (or username) that should run the container.
- `VOLUME`: Mechanism for persisting and sharing data between containers.
- `WORKDIR`: Creates a directory inside the container and sets it as the working directory.

Note: These are not all the options but the most commonly used ones.

## Creating a Dockerfile
Create a file named Dockerfile. You can also use variations like Dockerfile.test1 or Dockerfile.test2.

```bash
touch Dockerfile
```
![Diagram](https://github.com/Andherson333333/Docker/blob/main/Dockerfile/imagenes/dockerfile-ls.JPG)

## Content inside the Dockerfile
Once you know the basic parameters and their uses, you can create the Dockerfile according to your needs.

![Diagram](https://github.com/Andherson333333/Docker/blob/main/Dockerfile/imagenes/dockerfile-cat.JPG)

## Building the image
Once the file is created with the different parameters, run the following command:

```bash
docker build -t image_name:tag -f path/to/Dockerfile context_directory
```

Example:
```bash
docker build -t alpine-mysql:1.0 -f Dockerfile . .
```
![Diagram](https://github.com/Andherson333333/Docker/blob/main/Dockerfile/imagenes/Dockerfile-build.JPG)

## Verifying the image
To verify the creation of the image, use the following command:

```bash
docker images
```
![Diagram](https://github.com/Andherson333333/Docker/blob/main/Dockerfile/imagenes/dockerfile-images.JPG)
