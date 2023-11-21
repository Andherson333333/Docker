# Ques es ngnix

Nginx (pronunciado "engine-x") es un servidor web de código abierto y un servidor proxy inverso. Además de su función principal de servir páginas web estáticas y dinámicas, Nginx también se utiliza comúnmente como proxy inverso y equilibrador de carga. Fue creado para abordar el problema de la concurrencia, el rendimiento y el uso eficiente de los recursos.

# Funciones

-Servidor web para contenido estático y dinámico.

-Proxy inverso para balanceo de carga.

-Manejo de solicitudes HTTP/HTTPS.

-Terminación SSL/TLS.

-Cache de contenido estático y dinámico.

-Control de acceso y autenticación.

-Compresión de contenido.

-Redirecciones.

-Logging detallado y monitoreo
.
-Configuración dinámica con recarga en caliente.

-Seguridad con protección contra ataques DDoS y otras amenazas.


#Ubicacion de archivos


Claro, aquí están algunas ubicaciones típicas de configuración y contenido en un contenedor Nginx:

Proxy inverso para balanceo de carga:

Configuración: /etc/nginx/nginx.conf
Archivos de configuración adicionales: /etc/nginx/conf.d/
Manejo de solicitudes HTTP/HTTPS:

Configuración SSL/TLS: /etc/nginx/conf.d/ssl.conf
Terminación SSL/TLS:

Certificados SSL/TLS: /etc/nginx/ssl/
Cache de contenido estático y dinámico:

Cache estática: /var/cache/nginx/
Cache dinámica: /var/run/nginx-cache/
Control de acceso y autenticación:

Configuración de autenticación básica: /etc/nginx/conf.d/auth.conf
Compresión de contenido:

Configuración de compresión: /etc/nginx/nginx.conf
Redirecciones:

Configuración de redirección: /etc/nginx/conf.d/redirect.conf
Logging detallado y monitoreo:

Archivos de logs: /var/log/nginx/
Configuración dinámica con recarga en caliente:

Recarga de configuración: nginx -s reload (comando ejecutado dentro del contenedor)
Seguridad con protección contra ataques DDoS y otras amenazas:

Configuración de seguridad: /etc/nginx/conf.d/security.conf





