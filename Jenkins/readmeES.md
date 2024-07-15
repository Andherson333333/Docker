# Configuración de Jenkins con Docker

Este repositorio contiene información e instrucciones para instalar y configurar Jenkins utilizando Docker.

## Índice de contenidos
* [Instalación de Jenkins](#instalación-de-jenkins)
* [Ventajas y desventajas](#ventajas-y-desventajas)
* [Configuración del Dockerfile](#configuración-del-dockerfile)
* [Ejecución del contenedor Jenkins en Docker](#ejecución-del-contenedor-jenkins-en-docker)
* [Manejo de plugins](#manejo-de-plugins)

## Instalación de Jenkins

Hay dos formas de instalar Jenkins:

1. **Instalación sin Docker**: Para la instalación en Linux, consulta la documentación oficial de Jenkins: [https://www.jenkins.io/doc/book/installing/linux/](https://www.jenkins.io/doc/book/installing/linux/)

2. **Instalación con Docker**: Utilizaremos un Dockerfile para este método, ya que permite una mayor personalización según tus necesidades.

## Ventajas y desventajas

### Ventajas:
- **Facilidad de implementación**: Docker simplifica la instalación y el despliegue de Jenkins.
- **Portabilidad**: Los contenedores Docker pueden ejecutarse en cualquier entorno que soporte Docker.
- **Gestión de versiones**: Fácil gestión de versiones de Jenkins y sus plugins utilizando imágenes Docker.
- **Escalabilidad**: Docker permite escalar eficientemente los contenedores según sea necesario.
- **Gestión de recursos**: Administración eficiente de los recursos asignados a Jenkins.

### Desventajas:
- **Complejidad de red**: Configurar correctamente la red puede ser un desafío.
- **Seguridad**: Se requiere una atención especial para garantizar que la instancia de Jenkins sea segura.
- **Rendimiento**: Puede haber una ligera sobrecarga de rendimiento en comparación con una instalación directa.

## Configuración del Dockerfile

1. Elige una imagen base (por ejemplo, Alpine o Debian).
2. Crea un Dockerfile:
   ```
   touch Dockerfile
   ```
3. Construye la imagen con una etiqueta:
   ```
   sudo docker build -t jenkins:2.426.1-lts-jdk17 .
   ```
4. Verifica la imagen:
   ```
   sudo docker images
   ```

![Imágenes Docker](https://github.com/Andherson333333/Docker/blob/main/Jenkins/imagenes/Captura%20desde%202023-11-20%2001-29-49.png)

## Ejecución del contenedor Jenkins en Docker

Dos métodos para ejecutar el contenedor:

1. Usando el comando Docker:
   ```
   sudo docker run -p 8080:8080 -d  -v jenkins_home:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock jenkins:2.426.1-lts-jdk17
   ```

2. Usando Docker Compose:
   Crea un archivo `docker-compose.yml` y ejecuta:
   ```
   sudo docker-compose up -d
   ```

## Manejo de plugins

Para un manejo más controlado de plugins:

1. Ver plugins instalados:
   - Ve a Administrar Jenkins → Consola de Scripts
   - Ejecuta el siguiente script:
     ```groovy
     Jenkins.instance.pluginManager.plugins.each { plugin ->
         println("${plugin.getShortName()}:${plugin.getVersion()}")
     }
     ```

2. Crea un archivo `plugins.txt` con tus plugins deseados.

3. Reconstruye tu imagen Docker con los plugins personalizados.

4. En Jenkins, selecciona "Instalar plugins manualmente" para ver tus plugins listados marcados para instalación.

![Consola de Plugins de Jenkins](https://github.com/Andherson333333/Docker/blob/main/Jenkins/imagenes/jenkins-plugin1.png)

## Contribuciones

Las contribuciones a este proyecto son bienvenidas. Por favor, siéntete libre de enviar un pull request o abrir un issue.

## Licencia

[Incluye aquí la información de tu licencia]













