FROM jenkins/jenkins:2.426.1-lts-jdk17
USER root
RUN apt-get update -y && \
    apt-get install -y docker.io
RUN usermod -aG docker jenkins

# Agrega las siguientes líneas para copiar los archivos de configuración y los plugins
COPY plugin /usr/share/jenkins/ref/plugin

# Resto del Dockerfile
USER jenkins

