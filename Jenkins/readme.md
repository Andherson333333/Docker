# Jenkins Docker Configuration

This repository contains information and instructions for installing and configuring Jenkins using Docker.

## Table of Contents
* [Jenkins Installation](#jenkins-installation)
* [Advantages and Disadvantages](#advantages-and-disadvantages)
* [Dockerfile Configuration](#dockerfile-configuration)
* [Running Jenkins Container in Docker](#running-jenkins-container-in-docker)
* [Plugin Management](#plugin-management)

## Jenkins Installation

There are two ways to install Jenkins:

1. **Installation without Docker**: For Linux installation, refer to the official Jenkins documentation: [https://www.jenkins.io/doc/book/installing/linux/](https://www.jenkins.io/doc/book/installing/linux/)

2. **Installation with Docker**: We'll use a Dockerfile for this method as it allows for more customization based on your needs.

## Advantages and Disadvantages

### Advantages:
- **Easy Implementation**: Docker simplifies Jenkins installation and deployment.
- **Portability**: Docker containers can run in any environment that supports Docker.
- **Version Management**: Easily manage Jenkins and plugin versions using Docker images.
- **Scalability**: Docker allows efficient scaling of containers as needed.
- **Resource Management**: Efficiently manage resources allocated to Jenkins.

### Disadvantages:
- **Network Complexity**: Configuring the network correctly can be challenging.
- **Security**: Special attention is required to ensure the Jenkins instance is secure.
- **Performance**: There might be a slight performance overhead compared to a direct installation.

## Dockerfile Configuration

1. Choose a base image (e.g., Alpine or Debian).
2. Create a Dockerfile:
   ```
   touch Dockerfile
   ```
3. Build the image with a tag:
   ```
   sudo docker build -t jenkins:2.426.1-lts-jdk17 .
   ```
4. Verify the image:
   ```
   sudo docker images
   ```

![Docker Images](https://github.com/Andherson333333/Docker/blob/main/Jenkins/imagenes/Captura%20desde%202023-11-20%2001-29-49.png)

## Running Jenkins Container in Docker

Two methods to run the container:

1. Using Docker command:
   ```
   sudo docker run -p 8080:8080 -d  -v jenkins_home:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock jenkins:2.426.1-lts-jdk17
   ```

2. Using Docker Compose:
   Create a `docker-compose.yml` file and run:
   ```
   sudo docker-compose up -d
   ```

## Plugin Management

For more controlled plugin management:

1. View installed plugins:
   - Go to Manage Jenkins → Script Console
   - Run the following script:
     ```groovy
     Jenkins.instance.pluginManager.plugins.each { plugin ->
         println("${plugin.getShortName()}:${plugin.getVersion()}")
     }
     ```

2. Create a `plugins.txt` file with your desired plugins.

3. Rebuild your Docker image with the custom plugins.

4. In Jenkins, select "Install plugins manually" to see your listed plugins marked for installation.

![Jenkins Plugin Console](https://github.com/Andherson333333/Docker/blob/main/Jenkins/imagenes/jenkins-plugin1.png)

## Contributing

Contributions to this project are welcome. Please feel free to submit a pull request or open an issue.

## License

[Include your license information here]
