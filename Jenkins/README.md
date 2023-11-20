## Índice de contenidos
* [Instalacion de jenkins](#item1)
* [Ventajas y desventajase](#item2)
* [Configuracion Dockerfile](#item3)
* [Ejecucion del contenedor en docker](#item4)
* [Manejos de plugin](#item5)
*

<a name="item1"></a>
# Instalacion de jenkins

Hay 2 formas de instalar jenkins:

   1)Instalacion sin docker , si desea hacer la instalacion(linux) verificar la siguiente pagina       
   https://www.jenkins.io/doc/book/installing/linux/ 

   2)Instalacion con docker , para realizar esta instalacion vamos hacerlo a traves de un dockerfile ya que puedes personalizar un poco     mas la instalacion en funcion a los que necesites 
   
<a name="item2"></a>
# Ventajas y desventajas 

### Ventajas:

`Facilidad de Implementación` Docker simplifica el proceso de instalación y despliegue de Jenkins. Puedes configurar Jenkins con Docker en minutos.

`Portabilidad `Los contenedores Docker son portátiles y se pueden ejecutar en cualquier entorno que admita Docker. Esto facilita la migración y la replicación del entorno Jenkins.

`Gestión de Versiones `Puedes administrar las versiones de Jenkins y sus plugins utilizando imágenes de Docker. Esto facilita la reproducción de entornos específicos y la administración de versiones.

`Escalabilidad `Docker permite escalar contenedores según sea necesario. Puedes ejecutar múltiples instancias de Jenkins de manera eficiente y equilibrar la carga.

`Gestión de Recursos `Docker permite gestionar eficientemente los recursos asignados a Jenkins, como CPU y memoria.


### Desventajas:

`Complejidad de Red `Configurar correctamente la red puede ser un desafío, especialmente si Jenkins necesita interactuar con otros contenedores o servicios en la red.

`Seguridad` Configurar la seguridad de Jenkins dentro de un contenedor Docker requiere una atención especial para garantizar que la instancia de Jenkins sea segura y no se vea comprometida.

`Rendimiento`Aunque Docker introduce una sobrecarga mínima, puede haber una pequeña pérdida de rendimiento en comparación con una instalación directa en el sistema operativo anfitrión.

<a name="item3"></a>
# Configuracion Dockerfile 

Antes de contruir tiene que buscar la imagen base , puedes instalar diferentes S.O como:

`Alpine` La instalacion de paquetes se hace comando apk add

`Debian` La instalacion de paquetes se hace comando apt-get

1)Una ves elegida crearemos el dockerfile

```
touch dockerfile
```

2)Una ves creado vamos a construir la imagen ,vamos agregarle un tag para que sea facil ver la version de nuestro jenkins

```
sudo docker build -t jenkins:2.426.1-lts-jdk17 .
```
![Diagrama](https://github.com/Andherson333333/Docker/blob/main/Jenkins/imagenes/Captura%20desde%202023-11-20%2001-27-13.png)

3)Verificacion de la imagen

```
sudo docker images
```
![Diagrama](https://github.com/Andherson333333/Docker/blob/main/Jenkins/imagenes/Captura%20desde%202023-11-20%2001-29-49.png)

<a name="item4"></a>
# Ejecucion del contenedor en docker

Se puede hacer de 2 formas :

   1)A traves de comandos 

 ```
sudo docker run -p 8080:8080 -d  -v jenkins_home:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock jenkins:2.426.1-lts-jdk17
```
![Diagrama](https://github.com/Andherson333333/Docker/blob/main/Jenkins/imagenes/Captura%20desde%202023-11-20%2001-31-08.png)

   2)A traves de docker-compose

 ```
sudo docker images
```
![Diagrama](https://github.com/Andherson333333/Docker/blob/main/Jenkins/imagenes/Captura%20desde%202023-11-20%2001-39-10.png)

3)Una ves desplegado el contenedor lanze este comando para ver la clave de jenkins

 ```
docker logs -f <ID>
```

![Diagrama]()
   
Si tienes la instalacion del complemento compose de docker antes de aplicar

<a name="item5"></a>
# Manejos de plugin

Si desea un manejor de plugin mas controlado e informativo lo puedes hacer agregando un archivo a su dockerfile

1)Como ver mis plugin

Estando en su GUI de jenkins , valla a la siguiente zona :
Manage Jenkins-->Script Console

Copie y pegue la siguiente orden en su consola:

 ```
Jenkins.instance.pluginManager.plugins.each { plugin ->
    println("${plugin.getShortName()}:${plugin.getVersion()}")
}

```
![Diagrama](https://github.com/Andherson333333/Docker/blob/main/Jenkins/imagenes/jenkins-plugin1.png)



2)Archivo plugin

Usaremos una arquitectura de archivos como esta 

![Diagrama]()

Creamos el archivo plugin.txt y anesamos la lista de nuestros plugin , una ves realizado reconstruimos nuestra imagen de nuevo con los plugin personalizados
















