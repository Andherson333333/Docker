# SonarQube Installation and Deployment

## Project Description

This project aims to facilitate the installation and deployment of SonarQube using Docker. It provides necessary scripts and configurations to quickly set up a SonarQube environment, allowing development teams to easily implement this code quality analysis tool in their projects.

## Table of Contents
1. [What is SonarQube?](#what-is-sonarqube)
2. [Installation and Deployment Steps](#installation-and-deployment-steps)
   - [Directory Creation](#directory-creation)
   - [Creating the init.sh file](#creating-the-initsh-file)
   - [Deployment with Docker Compose](#deployment-with-docker-compose)
3. [Contributions](#contributions)
4. [License](#license)

## What is SonarQube?

SonarQube is an open-source platform designed to evaluate and analyze the quality of source code in software projects. It provides tools to perform static code analysis, identify quality issues, and offer recommendations to improve code readability, performance, and security.

## Installation and Deployment Steps

### Directory Creation

Before starting the deployment, it's necessary to create the directories that will store the required data and configurations. Run the following commands:

```bash
mkdir -p ./sonarqube/data
mkdir -p ./sonarqube/extensions
mkdir -p ./sonarqube/logs
mkdir -p ./postgresql/conf
mkdir -p ./postgresql/data
```

### Creating the init.sh file

The `init.sh` file is a script developed to address specific needs related to SonarQube. Its purpose is to perform kernel configurations before starting SonarQube using Docker Compose.

This script is essential because:
1. SonarQube uses an integrated Elasticsearch.
2. It's necessary to ensure that the Docker host configuration meets the requirements of Elasticsearch's production mode.
3. Specific file descriptor configurations are required.

### Deployment with Docker Compose

To start SonarQube, use the following command:

```bash
docker-compose up -d
```

This command will start the services defined in your `docker-compose.yml` file in detached mode.

## Contributions

Contributions to this project are welcome. Please feel free to open an issue or submit a pull request.

## License

[Include your license information here]
