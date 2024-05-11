# Alta Disponibilidad con ***HAProxy***

## Indice

## Definición 

***HAProxy*** es un software de código abierto que proporciona balanceo de carga y proxy inverso para servidores web. Es utilizado comúnmente en entornos de alta disponibilidad para distribuir la carga entre varios servidores y garantizar la disponibilidad y rendimiento de los servicios web. En **Debian**, ***HAProxy*** se puede instalar a través del gestor de paquetes ***apt-get***.

## 1. HAProxy SSL Terminador

## 1.2 Instalación y Comprobación

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