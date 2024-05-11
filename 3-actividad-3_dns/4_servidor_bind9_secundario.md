# Servidor BIND Secundario (Respaldo)

## Indice 

## Definición 

Un ***servidor secundario*** es un servidor que contiene una copia de la información almacenada en un servidor principal. Su función principal es actuar como respaldo en caso de que el servidor principal falle o se vuelva inaccesible. 

Además de servir como ***respaldo***, los servidores secundarios también pueden ser utilizados para distribuir la carga de trabajo, mejorar la disponibilidad de los servicios y garantizar la redundancia en caso de falla en el servidor principal. También pueden utilizarse para mejorar la velocidad de acceso a los datos al estar distribuidos geográficamente.

## 1. Cambios en el Servidor Primario

### 1.2 Clausula ***allow-transfer*** 

Utilizamos la siguiente clausula en el fichero de definción de zonas y de definición de los reenviadores , tiene que estar de la siguiente forma 

![Fichero de Definiir Zonas](./img/bind9_secundario/1_primario_allow_transfer.png)
![Fichero de Reenviadores](./img/bind9_secundario/2_primario_reenviaores.png)