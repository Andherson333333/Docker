# Que es djjango

Django es un framework web de alto nivel escrito en Python que fomenta el desarrollo rápido y limpio. Fue diseñado para ayudar a los desarrolladores a construir aplicaciones web de manera eficiente, proporcionando una estructura organizativa y un conjunto de patrones comunes

# Instalacion

En este caso en particular con el siguiente comando se puede usar de forma on-build para crear la estructura :

```
docker run -it --rm --user "$(id -u):$(id -g)" -v "$PWD":/usr/src/app -w /usr/src/app django django-admin.py
```

 Una ves instalado y verificado la imagen aplicar el dockerfile del repositorio
