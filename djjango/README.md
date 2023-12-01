# Que es djjango

Django es un framework web de alto nivel escrito en Python que fomenta el desarrollo rápido y limpio. Fue diseñado para ayudar a los desarrolladores a construir aplicaciones web de manera eficiente, proporcionando una estructura organizativa y un conjunto de patrones comunes

# Instalacion

En este caso en particular con el siguiente comando se puede usar de forma on-build para crear la estructura :

```
docker run -it --rm --user "$(id -u):$(id -g)" -v "$PWD":/usr/src/app -w /usr/src/app django django-admin.py
```

 Una ves instalado y verificado la imagen aplicar el dockerfile del repositorio

 # Djjango Project

## Descripción
Este proyecto utiliza el framework Django para construir una aplicación web. Incluye un ejemplo básico con una aplicación llamada ChatApp.

## Contenido
- [Estructura del Proyecto](#estructura-del-proyecto)
- [Requisitos](#requisitos)
- [Instrucciones de Uso](#instrucciones-de-uso)
- [Contribuir](#contribuir)
- [Licencia](#licencia)

## Estructura del Proyecto
- `ChatApp/`: Directorio que contiene la aplicación principal.
- `ChatProject/`: Directorio que contiene la configuración del proyecto Django.
- `Dockerfile`: Archivo de configuración para construir la imagen de Docker.
- `db.sqlite3`: Base de datos SQLite para el proyecto.
- `manage.py`: Archivo de gestión de Django para ejecutar comandos.
- `requirements.txt`: Lista de dependencias del proyecto.
- `templates/`: Directorio que puede contener plantillas HTML.

## Requisitos
- Docker instalado
- Otros requisitos específicos del proyecto...

## Instrucciones de Uso
1. Clona el repositorio: `git clone https://tu-repositorio.git`
2. Navega al directorio del proyecto: `cd djjango`
3. Construye la imagen de Docker: `docker build -t djjango .`
4. Ejecuta el contenedor: `docker run -p 8000:8000 djjango`

La aplicación estará disponible en [http://localhost:8000/](http://localhost:8000/).




