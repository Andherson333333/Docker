## Índice de contenidos
* [Descripcion](#item1)
* [Que es Nodejs](#item2)
* [Docker-compose](#item3)

<a name="item1"></a>
# Descripcion

Esta es una aplicación web básica para administrar notas simples en la web utilizando tecnologías Javascript como Nodejs, Mongodb y otras tecnologías relacionadas.


<a name="item2"></a>
# Que es Nodejs

Node.js es un entorno de ejecución de código abierto basado en el motor V8 de Google Chrome. Permite ejecutar código JavaScript en el lado del servidor, proporcionando a los desarrolladores la capacidad de construir aplicaciones escalables y eficientes. Node.js utiliza un modelo de entrada/salida no bloqueante y orientado a eventos, lo que significa que puede manejar múltiples operaciones simultáneamente sin esperar a que una operación se complete antes de pasar a la siguiente. Esta característica hace que Node.js sea especialmente adecuado para aplicaciones intensivas en E/S, como servidores web y aplicaciones de red..

<a name="item3"></a>
# Dockerfile

docker file es un controlador de imagenes de docker de forma personalizada

Este Dockerfile consta de dos etapas: una "etapa de construcción" y una "etapa de producción". Esta es una práctica común en Docker para reducir el tamaño final de la imagen y eliminar dependencias no necesarias en la etapa de producción. Con el siguiente comando creamos la imagen del container

```
docker build -t node:test .
```

![Diagrama](https://github.com/Andherson333333/Docker/blob/main/Node.js/Imagenes/docker-2.PNG)

<a name="item4"></a>
# Docker-compose

Para desplegarlo el aplicativo se realiza a traves de un docker-compose

```
docker-compose up
```

![Diagrama]()
