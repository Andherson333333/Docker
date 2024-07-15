# Instalación y Despliegue de SonarQube

## Descripción del Proyecto

Este proyecto tiene como objetivo facilitar la instalación y despliegue de SonarQube utilizando Docker. Proporciona scripts y configuraciones necesarias para configurar rápidamente un entorno de SonarQube, permitiendo a los equipos de desarrollo implementar fácilmente esta herramienta de análisis de calidad de código en sus proyectos.

## Índice de Contenidos
1. [¿Qué es SonarQube?](#qué-es-sonarqube)
2. [Pasos de Instalación y Despliegue](#pasos-de-instalación-y-despliegue)
   - [Creación de Directorios](#creación-de-directorios)
   - [Creación del archivo init.sh](#creación-del-archivo-initsh)
   - [Despliegue con Docker Compose](#despliegue-con-docker-compose)
3. [Contribuciones](#contribuciones)
4. [Licencia](#licencia)

## ¿Qué es SonarQube?

SonarQube es una plataforma de código abierto diseñada para evaluar y analizar la calidad del código fuente en proyectos de software. Proporciona herramientas para realizar análisis estático del código, identificar problemas de calidad, y ofrecer recomendaciones para mejorar la legibilidad, el rendimiento y la seguridad del código.

## Pasos de Instalación y Despliegue

### Creación de Directorios

Antes de iniciar el despliegue, es necesario crear los directorios que almacenarán los datos y configuraciones necesarios. Ejecuta los siguientes comandos:

```bash
mkdir -p ./sonarqube/data
mkdir -p ./sonarqube/extensions
mkdir -p ./sonarqube/logs
mkdir -p ./postgresql/conf
mkdir -p ./postgresql/data
```

### Creación del archivo init.sh

El archivo `init.sh` es un script desarrollado para abordar necesidades específicas relacionadas con SonarQube. Su propósito es realizar configuraciones del kernel antes de iniciar SonarQube mediante Docker Compose.

Este script es esencial porque:
1. SonarQube utiliza un Elasticsearch integrado.
2. Es necesario garantizar que la configuración del host Docker cumpla con los requisitos del modo de producción de Elasticsearch.
3. Se requieren configuraciones específicas de los descriptores de archivos.

### Despliegue con Docker Compose

Para iniciar SonarQube, utiliza el siguiente comando:

```bash
docker-compose up -d
```

Este comando iniciará los servicios definidos en tu archivo `docker-compose.yml` en modo detached.

## Contribuciones

Las contribuciones a este proyecto son bienvenidas. Por favor, siéntete libre de abrir un issue o enviar un pull request.

## Licencia

[Incluye aquí la información de tu licencia]
