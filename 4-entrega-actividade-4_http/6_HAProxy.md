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