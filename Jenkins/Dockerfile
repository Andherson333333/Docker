FROM jenkins/jenkins:2.426.1-lts-jdk17
USER root
RUN curl -sSL https://get.docker.com/ | sh
RUN usermod -aG docker jenkins
USER jenkins
