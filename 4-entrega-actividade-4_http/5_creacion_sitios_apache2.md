# Creación de Sitio Virtual con ***HTTP/HTTPS*** en Apache2 en Debian
<br>

## INDICE 
- [Creación de Sitio Virtual con ***HTTP/HTTPS*** en Apache2 en Debian](#creación-de-sitio-virtual-con-httphttps-en-apache2-en-debian)
  - [INDICE](#indice)
  - [1. Definición de ***Apache2***](#1-definición-de-apache2)
  - [2. Configación de Sitios Globales :](#2-configación-de-sitios-globales-)
  - [3. Configuración del sitio por defecto :](#3-configuración-del-sitio-por-defecto-)
  - [4. Configuración de un nuevo sitio virtual :](#4-configuración-de-un-nuevo-sitio-virtual-)
  - [5. Comprobaciones del Sitio Virtual](#5-comprobaciones-del-sitio-virtual)
- [Biografia de ***Apache2***](#biografia-de-apache2)


## 1. Definición de ***Apache2***

***Apache2*** es un servidor web de código abierto que forma parte del sistema operativo Debian. Es uno de los servidores web más populares y ampliamente utilizado en el mundo. ***Apache2*** es conocido por su estabilidad, seguridad y flexibilidad, lo que lo convierte en una excelente opción para alojar sitios web de cualquier tamaño.

La utilización de ***Apache2*** en **Debian** permite a los usuarios hospedar sus sitios web, aplicaciones web y servicios en línea de una manera confiable y segura. Con su amplia gama de características y opciones de configuración, ***Apache2*** es capaz de manejar una gran cantidad de tráfico y responder eficientemente a las solicitudes de los usuarios. Además, su integración con el sistema operativo Debian facilita su instalación y mantenimiento, convirtiéndolo en una herramienta indispensable para desarrolladores y administradores de sistemas.

![Portada Apache](./img/sitios_virtuales_apache2/portada_apache2.png)


## 2. Configación de Sitios Globales :

1 – Instala el servidor web **Apache** y **PHP** . <br>

~~~
apt install apache2
apt install php
~~~

![Instalación de Apache2](./img/sitios_virtuales_apache2/1_exapache2.png)
![Instalación de PHP](./img/sitios_virtuales_apache2/2_exapache2.png)

2 – Modifica el archivo apropiado para que el archivo a mostrar por defecto de un directorio sea ***index.php*** , ***index.asp*** y luego ***index.html*** . <br>

~~~
nano /etc/apache2/mods-avaliables/dir.conf
~~~

![Directorio por Defecto](./img/sitios_virtuales_apache2/3_exapache2.png)

3 – Habilita los módulos usertrack y userdir <br>

~~~
a2enmod usertrack
a2enmod userdir
~~~

![Habilitar módulos](./img/sitios_virtuales_apache2/4_exapache2.png)

## 3. Configuración del sitio por defecto :

1 – Configura el sitio por defecto que muestre **‘Este es el fichero del sitio por defecto’** .<br>

![Mensaje de Sitio por Defecto](./img/sitios_virtuales_apache2/5_exapache2.png)

2 – Debe atender peticiones a mayores , en el puerto ***9999*** . <br>

![Añadir puertos](./img/sitios_virtuales_apache2/6_exapache2.png)

## 4. Configuración de un nuevo sitio virtual :

1 – Crea un sitio virtual por nombre ciudad.gal que atienda en los puertos ***80*** y ***9999*** .<br>

![Añadir puertos](./img/sitios_virtuales_apache2/7_exapache2.png)

2 – Modifica los archivos de logs para que sean específicos . <br>

![Archivos de logs](./img/sitios_virtuales_apache2/8_exapache2.png)

3 – Cuando se produzca un error ***404*** se mostrara el mensaje **“No se ha podido encontrar ningún resultado en la búsqueda”** , que este alojado en el directorio ***/var/www/ciudad.gal/error_404.html*** . <br>

![Error 404](./img/sitios_virtuales_apache2/9_exapache2.png)

4 – Cuando se produzca un error ***403*** se mostrará un mensaje de ***“PROHIBIDO”*** . <br>

![Error 403](./img/sitios_virtuales_apache2/10_exapache2.png)

5 – Los archivos de este sitio a mostrar por defecto serán ***index.html*** e ***index.php*** . <br>

![Archivos por defecto](./img/sitios_virtuales_apache2/11_exapache2.png)

6 – No se permitirá que se listen los contenidos de las carpetas , al no encontrar ninguno de los documentos por defecto .

![Listado de directorios](./img/sitios_virtuales_apache2/12_exapache2.png)

7 – Crea un **‘alias’** que se redirija la **‘url’** ***./docs  ./documentos*** , que se debe crear previamente . <br>

![Creación de alias](./img/sitios_virtuales_apache2/13_exapache2.png)

8 – Crea una carpeta denominada ***carpetacuidad** . El acceso a esta carpeta debe ser restringida para los usuarios ***‘user1’*** y ***‘user2’*** con contraseña ***‘abc123.’*** mediante ***Autenticación Basic*** . <br>

![Autenticación Basic](./img/sitios_virtuales_apache2/14_exapache2.png)

9 – Crea un archivo denominado ***index.html*** en la carpeta ciudad.gal que tenga en el contenido **‘’Bienvenido al Sitio Virtual ciudad.gal ’’** . <br>

![Creación de Index](./img/sitios_virtuales_apache2/15_exapache2.png)

10 – Habilita en el anterior sitio web un acceso por ***SSL*** con la creación de la ***claves RSA***. Debe redirigir las peticiones del puerto ***80*** al puerto ***443*** . <br>

![Redirección https](./img/sitios_virtuales_apache2/16_exapache2.png)

## 5. Comprobaciones del Sitio Virtual 

**Para comprobar que todo esta funcionando correctamente , lo comprobaremos un ***"cliente Windows"*** , desde el navegador web . Entones vamos hacer las siguintes pruebas desde el navegador :** <br><br>

1 - Desde ***w10*** mostramos el sitio por defecto utilizando la ip del equipo <br>

![Desde windows : sito por defecto](./img/sitios_virtuales_apache2/1_comprobaciones_exapache2.png)


# Biografia de ***Apache2***

- ***Página Oficial :*** ***https://httpd.apache.org/***
- ***Wikipedia :*** ***https://es.wikipedia.org/wiki/Servidor_HTTP_Apache***
- ***Ionos :*** ***https://www.ionos.es/digitalguide/servidores/configuracion/instalar-apache-en-ubuntu/***