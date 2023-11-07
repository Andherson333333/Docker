## Índice de contenidos
* [Docker compose](#item1)
* [Instalación de Docker Compose](#item2)
* [Verificacion de instalacion](#item3)


<a name="item1"></a>
##  Docker compose

Docker Compose es una herramienta que permite definir y ejecutar aplicaciones Docker multi-contenedor utilizando un único archivo de configuración llamado docker-compose.yml. Con Docker Compose, puedes especificar la configuración de tus contenedores y servicios de manera fácil y eficiente, lo que facilita la gestión y la orquestación de múltiples contenedores


<a name="item1"></a>
##  Instalación de Docker Compose

Actualmente biene instalado por defecto 
se puede instalar mediante esta documentacion https://docs.docker.com/compose/install/


<a name="item1"></a>
##  Verificacion de instalacion

Una ves instalado se puede verificar con este comando

```
docker --version
```
##  Estructura de un docker-compose

`version` Especifica la versión de la configuración de Docker Compose que se está utilizando. La versión '3' es comúnmente utilizada y admite muchas características avanzadas.

`services` Define los servicios y contenedores que componen la aplicación. Cada servicio se nombra y se le asigna una serie de configuraciones.

`image` Especifica la imagen Docker que se utilizará para el servicio. Puedes proporcionar el nombre de la imagen y la etiqueta.

`ports` Define el mapeo de puertos entre el sistema anfitrión y el contenedor. Esto permite que el tráfico llegue al contenedor a través de un puerto en el sistema anfitrión.

`volumes` Permite montar volúmenes en el contenedor para almacenar datos persistentes. Puedes especificar rutas de host y rutas de contenedor para montar volúmenes.

`environment` Define variables de entorno que se pasan al contenedor. Estas variables pueden ser utilizadas por la aplicación dentro del contenedor.

`depends_on` Indica las dependencias del servicio. Docker Compose esperará hasta que los servicios dependientes estén en funcionamiento antes de iniciar el servicio actual.

`networks` Define configuraciones de red, como la creación de redes personalizadas para aislar contenedores.

`volumes` Permite definir volúmenes personalizados que pueden ser compartidos entre contenedores.







