# Servidor ***BIND*** Secundario (Respaldo)

## Indice 

- [Servidor ***BIND*** Secundario (Respaldo)](#servidor-bind-secundario-respaldo)
  - [Indice](#indice)
  - [Definición](#definición)
  - [1. Cambios en el Servidor Primario](#1-cambios-en-el-servidor-primario)
    - [1.2 Clausula ***allow-transfer***](#12-clausula-allow-transfer)
    - [1.2 Cambios en Zonas](#12-cambios-en-zonas)
  - [2. Configuración en Servidor Secundario](#2-configuración-en-servidor-secundario)
    - [2.1 Definición de zonas](#21-definición-de-zonas)
    - [2.3 Mostrar Transferencia de Zonas](#23-mostrar-transferencia-de-zonas)


## Definición 

Un ***servidor secundario*** es un servidor que contiene una copia de la información almacenada en un servidor principal. Su función principal es actuar como respaldo en caso de que el servidor principal falle o se vuelva inaccesible. 

Además de servir como ***respaldo***, los servidores secundarios también pueden ser utilizados para distribuir la carga de trabajo, mejorar la disponibilidad de los servicios y garantizar la redundancia en caso de falla en el servidor principal. También pueden utilizarse para mejorar la velocidad de acceso a los datos al estar distribuidos geográficamente.

## 1. Cambios en el Servidor Primario

### 1.2 Clausula ***allow-transfer*** 

Utilizamos la siguiente clausula en el fichero de definción de zonas y de definición de los reenviadores , tiene que estar de la siguiente forma 

~~~
allow-transfer { 192.168.18.109; };
forwardes{};
~~~

![Fichero de Definiir Zonas](./img/bind9_secundario/1_primario_allow_transfer.png)

~~~
allow-transfer { 192.168.18.109; };
~~~

![Fichero de Reenviadores](./img/bind9_secundario/2_primario_reenviaores.png)


### 1.2 Cambios en Zonas 

Modificamos el fichero de zonas directa y zona inversa y añadimos el registro ***NS*** para definir el servidor secundario que vamos ha asignar para el dominio 

~~~
ns2 IN  NS  ns2.masofie.eus.
ns2 IN  A   192.168.18.109
~~~

![Cambios en Zonas 1](./img/bind9_secundario/3_primario_definicion_zona_directa.png)

~~~
109 IN  PTR ns2.masofie.eus.
~~~

![Cambios en Zonas 1](./img/bind9_secundario/4_primario_definicion_zona_invenso.png)


## 2. Configuración en Servidor Secundario

### 2.1 Definición de zonas 

Aqui vamos ha defir las zonas directas e inversas y que van a tener una directiva ***slave*** o sea esclavo o secundario de otro directorio y otra directiva llamada ***masters*** para ahí añadir los servidores maestros 

![Definición de zonas](./img/bind9_secundario/5_secundario_definicion_zonas.png)


### 2.3 Mostrar Transferencia de Zonas

Para transferir las zonas reiniciamos nuestro servicio de **bind9** , de la siguiente manera y accedemos a la ruta donde estan las zonas por defecto y como podes ver se ha trasferido correctamente 

~~~
systemctl restart bind9
~~~

![Mostrar Transferencia de Zonas](./img/bind9_secundario/6_secundario_transferencia_zonas1.png)