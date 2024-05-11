# Servidor BIND Secundario (Respaldo)

## Indice 

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

![Cambios en Zonas 1](./img/bind9_secundario/3_primario_definicion_zona_directa.png)
![Cambios en Zonas 1](./img/bind9_secundario/4_primario_definicion_zona_invenso.png)