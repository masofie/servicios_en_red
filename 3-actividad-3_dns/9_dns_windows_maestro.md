# DNS Maestro en Windows Server

## Indice 
- [DNS Maestro en Windows Server](#dns-maestro-en-windows-server)
  - [Indice](#indice)
  - [1. Instalación de DNS](#1-instalación-de-dns)
    - [1.2 Agregar Rol DNS](#12-agregar-rol-dns)
  - [2. Configuración DNS](#2-configuración-dns)
    - [2.1 Reenviadores](#21-reenviadores)
    - [2.2 Creación de Zona Búsqueda Directa](#22-creación-de-zona-búsqueda-directa)
    - [2.2 Creación de Zona Búsqueda Inversa](#22-creación-de-zona-búsqueda-inversa)
    - [2.2 Añadir Registros Directa/Iversa](#22-añadir-registros-directaiversa)
  - [3. Compracioneas con ***nslookup***](#3-compracioneas-con-nslookup)
    - [3.1 Cliente Windows](#31-cliente-windows)


## 1. Instalación de DNS 

### 1.2 Agregar Rol DNS

Añadimos el rol para instalar el servidor dns en nuestro sistema operativo 

![Agregar Rol DNS](./img/ws_maestro/1_ws_maestro_roles.png)

## 2. Configuración DNS

### 2.1 Reenviadores 

Definimos los reenviadores que vamos ha utilizar para cuando el servidor no encuentre donde buscar le pidan la peticiones a ellos

![Reenviadores](./img/ws_maestro/1_ws_maestro_reenviadres.png)

### 2.2 Creación de Zona Búsqueda Directa

Una en la siguiente pestaña damos clic derecho en **zona directa** y creamos una nueva zona , de la siguiente manera 

![Nueva Busqueda Directa](./img/ws_maestro/3_ws_maestro_zona_directa1.png)

Seleccionamos el tipo de zona que deseamos y como es un servidor maestro seleccionamos **zona principal**

![Tipo Busqueda Directa](./img/ws_maestro/4_ws_maestro_zona_directa2.png)

Le damos un nombre alusivo a nuestra zona

![Nombre Busqueda Directa](./img/ws_maestro/5_ws_maestro_zona_directa3.png)

Y aqui esta la zona directa creada correctamente 

![Creada Busqueda Directa](./img/ws_maestro/6_ws_maestro_zona_directa4.png)

### 2.2 Creación de Zona Búsqueda Inversa

Damos cli derecho ay creamos zona de busqueda inversa 

![Nueva Busqueda Inversa](./img/ws_maestro/7_ws_maestro_zona_inversa1.png)

Le damos el nombre a nustra zona , como es una zona inversa y el nombre depende de la red que tengas al momento de crearla

![Nombre Busqueda Inversa](./img/ws_maestro/8_ws_maestro_zona_inversa2.png)

La zona inversa se ha creado correctamente 

![Creada Busqueda Inversa](./img/ws_maestro/9_ws_maestro_zona_inversa3.png)


### 2.2 Añadir Registros Directa/Iversa

Añadimos un par de registros a nustra zona para hacer luegos las comprobaciones en el cliente

![Añadir Registros Directa/Iversa](./img/ws_maestro/10_ws_maestro_registros.png)


## 3. Compracioneas con ***nslookup***

### 3.1 Cliente Windows 

Accedemos al cliente y hacemos las siguientes comprobaciones , esto para ver si funciona correctamente 

![Compracioneas en Cliente Windows](./img/ws_maestro/11_ws_maestro_comprobaciones.png)