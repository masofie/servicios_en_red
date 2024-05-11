# Alta Disponibilidad con ***HAProxy***

## Indice

## Definición 

***HAProxy*** es un software de código abierto que proporciona balanceo de carga y proxy inverso para servidores web. Es utilizado comúnmente en entornos de alta disponibilidad para distribuir la carga entre varios servidores y garantizar la disponibilidad y rendimiento de los servicios web. En **Debian**, ***HAProxy*** se puede instalar a través del gestor de paquetes ***apt-get***.

![Logo HAProxy](./img/HAProxy/logo_aproxy.png)

## 1. HAProxy SSL Terminador

### 1.1 Instalación y Comprobación

Creamos una máquina nueva e instalamos el paquete haproxy 

~~~
apt install haproxy
~~~
![Comando de Instalación](./img/HAProxy/1_aproxy_instalacion.png)


Mostramos la versión que hemos instalamos

~~~
haproxy -v
~~~
![Comando de Versión](./img/HAProxy/2_aproxy_version.png)


Copiamos el fichero original de haproxy para tener una copia de seguridad

~~~
cp /etc/haproxy/haproxy.cfg /etc/haproxy/haproxy.cfg.original
~~~

![Copia de Fichero](./img/HAProxy/3_copia_fichero.png)


### 1.2 Instalación de Apache2

Ahora instalamos apache en la máquina del sitio web (www1)

~~~
apt install apache2
~~~

![Instalación de Apache2](./img/HAProxy/4_instalacion_apache2.png)


### 1.3 Instalación de Módulos PHP

E instalamos el modulo de php

~~~
sudo apt-get install apache2 php libapache2-mod-php
~~~

![Instalación de Apache2](./img/HAProxy/5_instalacion_php.png)


Reiniciamos el servicio de apache2 para guardar cambios

~~~
systemclt restart apache2
~~~
~~~
systemclt status apache2
~~~

![Reiniciar y Estado de Apache2](./img/HAProxy/6_reinciar_status_apache2.png)


Copiamos el sitio por defecto y cambiamos el nombre

~~~
cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/www.seriprobas.eu.conf
~~~

![Copia de Fichero de Sitios](./img/HAProxy/7_copia_sites_avaliables.png)


Creamos un fichero index.php alusivo al sitio web de seriprobas.eu

~~~
nano var/www/www.seriprobas.eu/index.php
~~~

![Copia de Fichero de Sitios](./img/HAProxy/8_crear_fichero_index.png)


Vamos al navegador del cliente y comprobamos que podemos acceder al sitio web


![Copia de Fichero de Sitios](./img/HAProxy/9_comprobar_index_w10.png)