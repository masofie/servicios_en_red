# Instalación de ***Webmin*** en Servidor Primario

## Indice 

- [Instalación de ***Webmin*** en Servidor Primario](#instalación-de-webmin-en-servidor-primario)
  - [Indice](#indice)
  - [Definición](#definición)
  - [1.  Herramienta Webmin](#1--herramienta-webmin)
    - [1.1 Instalación de Paquetes](#11-instalación-de-paquetes)
    - [1.2 Descarga de ***GPG Keys***](#12-descarga-de-gpg-keys)
    - [1.3 Instalación de ***Webmin***](#13-instalación-de-webmin)
    - [1.4 Acceder a ***Webmin***](#14-acceder-a-webmin)


## Definición

***Webmin*** es una herramienta de administración basada en la web que se utiliza para gestionar servidores de forma remota, incluido el servidor ***DNS BIND9*** . Con ***Webmin***, los administradores pueden realizar tareas de configuración, monitoreo y mantenimiento en servidores de forma sencilla a través de una interfaz web intuitiva.

En el caso de **BIND9**, ***Webmin*** ofrece funcionalidades como la configuración de zonas **DNS**, la gestión de registros de recursos, la configuración de servidores de nombres secundarios, la monitorización del rendimiento del servidor **DNS**, entre otras tareas relacionadas con la gestión de un servidor **BIND9**.

En resumen, ***Webmin*** es una herramienta útil para facilitar la administración y el mantenimiento de servidores **DNS**, como **BIND9**, a través de una interfaz web fácil de usar.

## 1.  Herramienta Webmin

### 1.1 Instalación de Paquetes 

Primero tenemos que instalar algunos paquetes necesarios para la instalación y administración de ***webmin*** , ejecuta el siguiente comando 

~~~
apt -y install gnupg wget curl
~~~

![Instalación de Paquetes](./img/bind9_webmin/1_install_paquestes_necesarios.png)


### 1.2 Descarga de ***GPG Keys***

Descargamos el configurable de repositorio GPG keys

~~~
 curl -o setup-repos.sh https://raw.githubusercontent.com/webmin/webmin/master/setup-repos.sh
~~~

![Descarga de GPG Keys](./img/bind9_webmin/2_descarga_keys_curl.png)


Ejecutamos el configurable que acabamos de descargar

~~~
sh setup-repos.sh
~~~


![Ejecutar de GPG Keys](./img/bind9_webmin/3_ejecutar_keys_curl.png)


### 1.3 Instalación de ***Webmin***

Ahora instalamos el ***Webmin*** cuando este todo configurado antes

~~~
apt install webmin
~~~

![Instalación de Webmin](./img/bind9_webmin/4_descarga_webmin.png)


Después reiniciamos el servidor de Webmin y mostramos el puerto que utiliza , usamos los siguientes comandos

~~~
systemctl status webmin.service
~~~


![Reiniciamos el Webmin](./img/bind9_webmin/5_estado_webmin.png)

~~~
ss -ltn
~~~

![Puerto de Webmin](./img/bind9_webmin/6_puerto_webmin.png)


### 1.4 Acceder a ***Webmin***

Para acceder lo vamos hacer desde el navegador de w10 añadindo la ip y el puerto , de la siguiente manera 

~~~
192.168.18.107:10000
~~~

![Acceder a Webmin](./img/bind9_webmin/7_accediendo_webmin.png)


Como podemos ver hemos iniciado correctamente a nuesta herramienta desde el navegador


![Desde el Webmin](./img/bind9_webmin/8_adentro_webmin.png)