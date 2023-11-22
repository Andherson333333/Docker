# Que es sonarqube

SonarQube es una plataforma de código abierto diseñada para evaluar y analizar la calidad del código fuente en proyectos de software. Proporciona herramientas para realizar análisis estático del código, identificar problemas de calidad, y ofrecer recomendaciones para mejorar la legibilidad, el rendimiento y la seguridad del código

# Paso de instalacion y despligue

## Creacion Directorios

`Nota` Cabe destacar que tiene un  `.` asi que modifique la ruta 

```
mkdir -p ./sonarqube/data

mkdir -p ./sonarqube/extensions

mkdir -p ./sonarqube/logs

mkdir -p ./postgresql/conf

mkdir -p ./postgresql/data
```

## Creacion init.sh

Este script, denominado init.sh, se desarrolla para abordar una necesidad específica relacionada con SonarQube. Dado que SonarQube utiliza un Elasticsearch integrado, es esencial garantizar que la configuración del host Docker cumpla con los requisitos del modo de producción de Elasticsearch y las configuraciones de los descriptores de archivos.

El propósito del script init.sh es realizar configuraciones específicas del kernel antes de iniciar SonarQube mediante Docker Compose. Estas configuraciones son fundamentales para satisfacer los requisitos de ciertas aplicaciones, como SonarQube, que pueden tener demandas particulares en cuanto al sistema operativo y el kernel.

## docker-compose

```
docker-compose up -d 
```
