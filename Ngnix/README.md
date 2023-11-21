## Índice de contenidos
* [Ques es ngnix](#item1)
* [Funciones](#item2)
* [Ubicacion de archivos](#item3)
* [Estructura para docker nginx  general](#item4)
* [Construir imagen](#item5)

<a name="item1"></a>
# Ques es ngnix

Nginx (pronunciado "engine-x") es un servidor web de código abierto y un servidor proxy inverso. Además de su función principal de servir páginas web estáticas y dinámicas, Nginx también se utiliza comúnmente como proxy inverso y equilibrador de carga. Fue creado para abordar el problema de la concurrencia, el rendimiento y el uso eficiente de los recursos.

<a name="item2"></a>
# Funciones

Funciones mas comunes :

1)Servidor web para contenido estático y dinámico.

2)Proxy inverso para balanceo de carga.

3)Manejo de solicitudes HTTP/HTTPS.

4)Terminación SSL/TLS.

5)Cache de contenido estático y dinámico.

6)Control de acceso y autenticación.

7)Compresión de contenido.

8)Redirecciones.

9)Logging detallado y monitoreo

10)Configuración dinámica con recarga en caliente.

11)Seguridad con protección contra ataques DDoS y otras amenazas.

<a name="item3"></a>
# Ubicacion de archivos

Es crucial comprender qué función desempeñan los distintos archivos dentro de su contenedor Nginx, así como conocer las ubicaciones específicas de estos archivos. Al entender estas funciones y localizaciones, podrá personalizar la configuración según sus necesidades, simplemente reemplazando los archivos correspondientes

## Ubicacion importantes

`/usr/share/nginx/html` sitio web estatico

`/etc/nginx/conf.d` otras configraciones

`/etc/nginx/nginx.conf` configuracion principal

<a name="item4"></a>
# Estructura para docker nginx  general

![Diagrama](https://github.com/Andherson333333/Docker/blob/main/Ngnix/imagenes/nginix.JPG)

# Construir imagen

Una vez configurados los archivos de intercambio, procedemos a colocar estos archivos en las ubicaciones correspondientes y generar la imagen utilizando un archivo Dockerfile. La instrucción clave en este proceso es COPY/ADD, la cual se utiliza para copiar archivos desde la máquina local al sistema de archivos de la imagen Docker.












