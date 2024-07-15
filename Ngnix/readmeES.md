# Nginx Docker Configuration

Este proyecto contiene la configuración para ejecutar Nginx en Docker, incluyendo un Dockerfile y un archivo docker-compose.yml.

## Índice de contenidos
* [¿Qué es Nginx?](#qué-es-nginx)
* [Funciones](#funciones)
* [Ubicación de archivos](#ubicación-de-archivos)
* [Estructura para Docker Nginx](#estructura-para-docker-nginx)
* [Construir imagen](#construir-imagen)

## ¿Qué es Nginx?

Nginx (pronunciado "engine-x") es un servidor web de código abierto y un servidor proxy inverso. Además de su función principal de servir páginas web estáticas y dinámicas, Nginx también se utiliza comúnmente como proxy inverso y equilibrador de carga. Fue creado para abordar el problema de la concurrencia, el rendimiento y el uso eficiente de los recursos.

## Funciones

Funciones más comunes de Nginx:

1. Servidor web para contenido estático y dinámico.
2. Proxy inverso para balanceo de carga.
3. Manejo de solicitudes HTTP/HTTPS.
4. Terminación SSL/TLS.
5. Cache de contenido estático y dinámico.
6. Control de acceso y autenticación.
7. Compresión de contenido.
8. Redirecciones.
9. Logging detallado y monitoreo.
10. Configuración dinámica con recarga en caliente.
11. Seguridad con protección contra ataques DDoS y otras amenazas.

## Ubicación de archivos

Es crucial comprender qué función desempeñan los distintos archivos dentro de su contenedor Nginx, así como conocer las ubicaciones específicas de estos archivos.

### Ubicaciones importantes

- `/usr/share/nginx/html`: sitio web estático
- `/etc/nginx/conf.d`: otras configuraciones
- `/etc/nginx/nginx.conf`: configuración principal

## Estructura para Docker Nginx

![Diagrama de estructura Nginx](https://github.com/Andherson333333/Docker/blob/main/Ngnix/imagenes/nginix.JPG)

## Construir imagen

Una vez configurados los archivos de intercambio, procedemos a colocar estos archivos en las ubicaciones correspondientes y generar la imagen utilizando un archivo Dockerfile. La instrucción clave en este proceso es COPY/ADD, la cual se utiliza para copiar archivos desde la máquina local al sistema de archivos de la imagen Docker.

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

## Uso

Para construir y ejecutar el contenedor Nginx:

1. Asegúrate de tener Docker y Docker Compose instalados.
2. Coloca tus archivos de configuración y contenido estático en los directorios correspondientes.
3. Ejecuta `docker-compose up -d` para iniciar el contenedor en modo detached.

El servidor Nginx estará disponible en `http://localhost:8080`.









