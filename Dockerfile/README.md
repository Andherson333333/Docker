## Índice de contenidos
* [¿Que es un dockerfile?](#item1)
* [Creacion de un Dockerfile](#item2)
* [Contenido dentro del archivo Dockerfile](#item3)
* [Construcion de la imagen](#item4)
* [Construcion de la imagen](#item5)

<a name="item1"></a>
## ¿Que es un dockerfile?

docker file es un controlador de imagenes de docker de forma personalizada 

## Parametros de dokerfile hasta el momento esta estos:

`FROM`la imagen base con los que se quiere trabajar se le pueden agregar tag y por default biene lates FROM imagen:Tag

`RUN`Ejecutas comandos dentro del contenedor cabe destacar que no es asistido por ende al colocar un comando se tendra que utilizar -y(debia) tambien como esto se genera en capas y run es una capa se recomienda utilizar la mayor cantidad de comandos en una sola linea RUN apt-get update && apt-get install tree.

`CMD`["executable","param1","param2"] (ejecutivo forma, esta es la forma preferida )Solo puede haber uno CMD instrucción en un Dockerfile. Si enumera más de uno CMD entonces solo el último CMD entrará en vigencia.Esta ejecucion se caracteriza por no ser persistente y se puede cambiar(uso servidores para mantenerlo abierto pero se puede cambiar)

`ENTRYPOINT`Tambien es un comando pero es persistente no se puede cambiar este comando se realiza al ejecutar el contenedor y la mayoria de las beses se usa ejecutar algun aplicativo tercer plano,o poner algo persistente como las variables de entorno en un scrip(usar alguna ejecutivo desde contenedo u otros uso)

`COPY/ADD`Se utiliza para copiar archivos al contenedor cabe destarcar que se necesita una fuente:destino ADD es mas potente que copi ya que permite copiar desde una URL, incluso si src es un archivo comprimod lo descomprime en el destino

`ENV`variables de entorno como usuario bases de datos , entre otras depende del programa

`EXPOSE`Solo se toma como referencia al contenedor de forma Informativa y se ejecuta solo con docker run -p

`LABEL`son etiquetas para el contenedor se puede usar para personalizar no son necesarias funcionan con Las etiquetas son un mecanismo para aplicar metadatos a los objetos de Docker

`USER`establece el UID (o nombre de usuario) que debe ejecutar el contenedor

`VOLUME`es un mecanismo que permite persistir datos y compartirlos entre contenedores. Los volúmenes son una forma de almacenamiento duradero que no está vinculada directamente al ciclo de vida de un contenedor

`WORKDIR`se crea una carpte dentro del contenedor como home tu le indicas ,ahora desde se correra run ,cmd entrypoint / raiz (linuz)

Cabe destacar que esta no son todas las opciones pero son las mas utilizadas por el momento

<a name="item2"></a>
## Creacion de un Dockerfile
Se crea un archivo con el nombre Dockerfile tambien puede usar esta sintansis al crear dockerfile , Dockerfile.test1 o Dockerfile.test1 .

```
touch Dockerfile
```

![Diagrama](https://github.com/Andherson333333/Docker/blob/main/Dockerfile/imagenes/dockerfile-ls.JPG)

<a name="item3"></a>
## Contenido dentro del archivo Dockerfile

Como ya sabemos los parametros bases y sus usos solo tenemos que realizarlo segun lo que necesitemos 

![Diagrama](https://github.com/Andherson333333/Docker/blob/main/Dockerfile/imagenes/dockerfile-cat.JPG)

<a name="item4"></a>
## Construcion de la imagen
Una ves creado el archivo con los diferentes parametros corremos el siguiente comando 

docker build -t nombre_de_la_imagen:etiqueta -f ruta/al/Dockerfile directorio_de_contexto

```
 docker build -t alpine-mysql:1.0 -f Dockerfile . .
```
![Diagrama](https://github.com/Andherson333333/Docker/blob/main/Dockerfile/imagenes/Dockerfile-build.JPG)

## Verificacion de la imagen
Ahora una ves creada la imagen para verificar la creacion se usa el siguiente comando

```
docker images
```

![Diagrama](https://github.com/Andherson333333/Docker/blob/main/Dockerfile/imagenes/dockerfile-ls.JPG)
















