# 🔄 Alta Disponibilidad con HAProxy

**📑 Indice**
- [🔄 Alta Disponibilidad con HAProxy](#-alta-disponibilidad-con-haproxy)
  - [📝 Definición](#-definición)
  - [⚙️ 1. HAProxy como Terminador SSL](#️-1-haproxy-como-terminador-ssl)
    - [🛠️ 1.1 Instalación y Comprobación de HAProxy](#️-11-instalación-y-comprobación-de-haproxy)
    - [1.2 Instalación del servidor Apache2](#12-instalación-del-servidor-apache2)
    - [📦 1.3 Instalación de Módulos PHP Necesarios](#-13-instalación-de-módulos-php-necesarios)
  - [🔧 2. Configuración de HAProxy](#-2-configuración-de-haproxy)
    - [🖥️ 2.1 Crear Servidores de Respaldo (Backends)](#️-21-crear-servidores-de-respaldo-backends)
    - [✅ 2.2 Comprobaciones de Funcionamiento](#-22-comprobaciones-de-funcionamiento)

<br>

## 📝 Definición 

**HAProxy** es un software de código abierto que proporciona balanceo de carga y proxy inverso para servidores web. Es utilizado comúnmente en entornos de alta disponibilidad para distribuir la carga entre varios servidores y garantizar la disponibilidad y rendimiento de los servicios web. En **Debian**, **HAProxy** se puede instalar a través del gestor de paquetes **``apt-get``**.

<br>

## ⚙️ 1. HAProxy como Terminador SSL

### 🛠️ 1.1 Instalación y Comprobación de HAProxy

Creamos una máquina nueva e instalamos el paquete **``haproxy``** : 

~~~~~~~~~~~~~~~~~~~~
apt install haproxy
~~~~~~~~~~~~~~~~~~~~

![Comando de Instalación](./img/HAProxy/1_aproxy_instalacion.png)


Mostramos la versión que hemos instalamos

~~~~~~~~~~~~
haproxy -v
~~~~~~~~~~~~

![Comando de Versión](./img/HAProxy/2_aproxy_version.png)


Copiamos el fichero original de haproxy para tener una copia de seguridad

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
cp /etc/haproxy/haproxy.cfg /etc/haproxy/haproxy.cfg.original
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

![Copia de Fichero](./img/HAProxy/3_copia_fichero.png)


### 1.2 Instalación del servidor Apache2

Ahora instalamos apache en la máquina del sitio web (www1)

~~~~~~~~~~~~~~~~~~~~
apt install apache2
~~~~~~~~~~~~~~~~~~~~

![Instalación de Apache2](./img/HAProxy/4_instalacion_apache2.png)


### 📦 1.3 Instalación de Módulos PHP Necesarios

E instalamos el modulo de **``php``**

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo apt-get install apache2 php libapache2-mod-php
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

![Instalación de Apache2](./img/HAProxy/5_instalacion_php.png)


Reiniciamos el servicio de **``apache2``** para guardar cambios

~~~~~~~~~~~~~~~~~~~~~~~~~~
systemclt restart apache2
~~~~~~~~~~~~~~~~~~~~~~~~~~
~~~~~~~~~~~~~~~~~~~~~~~~~~
systemclt status apache2
~~~~~~~~~~~~~~~~~~~~~~~~~~

![Reiniciar y Estado de Apache2](./img/HAProxy/6_reinciar_status_apache2.png)


Copiamos el sitio por defecto y cambiamos el nombre

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/www.seriprobas.eu.conf
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

![Copia de Fichero de Sitios](./img/HAProxy/7_copia_sites_avaliables.png)


Creamos un fichero **``index.php``** alusivo al sitio web de **``seriprobas.eu``**

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
nano var/www/www.seriprobas.eu/index.php
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

![Copia de Fichero de Sitios](./img/HAProxy/8_crear_fichero_index.png)


Vamos al navegador del cliente y comprobamos que podemos acceder al sitio web


![Visitar navegador](./img/HAProxy/9_comprobar_index_w10.png)

## 🔧 2. Configuración de HAProxy
<br>

### 🖥️ 2.1 Crear Servidores de Respaldo (Backends)

Lo primero que hay que hacer es ir al **``haproxy``** , visualizamos la ip . Eliminamos la ip que teníamos antes en el fichero hosts y añadimos la de la máquina haproxy .


![Mostrar ip](./img/HAProxy/10_ver_ip.png)
![Fichero host en windows](./img/HAProxy/11_fichero_hostss_w10.png)


Abrimos el siguiente fichero y añadimos las siguientes lineas al final del fichero

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
frontend apache_front
	bind *:80
	acl host_www_seriprobas.eu hdr(host) -i www.seriprobas.eu
	use_bckend apache_backend_servers if hos_www_seriprobas.eu
	option forwardfor

frontend apache_backend_serves
	balance roundrobin
	server backend01 172.16.10.96:80 check
	server backend01 172.16.10.91:80 check
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

![Crear Fcihero Haproxy](./img/HAProxy/12_fichero_haproxy.png)


Reiniciamos el servicio de haproxy y miramos el estado para ver si esta todo correcto 

![Reiniciamos servicio](./img/HAProxy/13_reinicio.png)


### ✅ 2.2 Comprobaciones de Funcionamiento

Tenemos las tres máquinas encendidas **``haproxy``** , **``www1``** y **``www2``** y vamos al cliente y accedemos al a sitio el servidor que nos responde es el **``www1``**

<br>

![Comprobaciones desde Windows 1](./img/HAProxy/14_comprobacion_w10.png)

Luego apagamos el servidor **``www1``** y hacemos la misma comprobación y nos responde el **``www2``**
<br>

![Comprobaciones desde Windows 2](./img/HAProxy/15_comprobacion_w10.png)

Ahora apagamos el servidor **``www2``** y solo tenemos encendió haproxy , y como podemos ver no funciona

<br>

![Comprobaciones desde Windows 3](./img/HAProxy/16_comprobacion_w10.png)

<br>

**💡 Consejo Final**

>Asegúrate de que todos los servidores backend estén activos 🟢 y correctamente configurados antes de levantar **``HAProxy``** 🛠️.
>Utiliza el modo balanceo de carga **``round-robin``** 🔁 para distribuir tráfico de forma equitativa y mejorar el rendimiento.
>Puedes verificar el estado en tiempo real con herramientas como **``haproxy -c -f /ruta/al/config.cfg``** o accediendo a la interfaz de estadísticas si está habilitada 📊.
>¡No olvides reiniciar el servicio tras cada cambio con **``sudo systemctl restart haproxy``** ! 🔄