# Montar Apache, PHP y MariaDB

## Indice

- [Montar Apache, PHP y MariaDB](#montar-apache-php-y-mariadb)
  - [Indice](#indice)
  - [Definición](#definición)
  - [1. Sitio Web con Phpmyadmin](#1-sitio-web-con-phpmyadmin)
    - [1.1 Instalación de MariaDB y Comprobación](#11-instalación-de-mariadb-y-comprobación)
    - [1.2 Instalación de PHP y Comprobación](#12-instalación-de-php-y-comprobación)
    - [1.3 Instalación de PHPmyadmin y Comprobación](#13-instalación-de-phpmyadmin-y-comprobación)


## Definición

***Apache*** : Es un servidor web de código abierto que permite publicar páginas web en Internet. Es muy popular y es ampliamente utilizado en la mayoría de los sistemas operativo

***PHP*** : Es un lenguaje de programación de código abierto especialmente diseñado para el desarrollo web. Se utiliza para crear sitios web dinámicos e interactivos, ya que puede integrarse fácilmente con bases de datos y otros servicios web

***MariaDB*** : Es un sistema de gestión de bases de datos relacional de código abierto que se ha convertido en una alternativa popular a **MySQL**. Ofrece un rendimiento rápido, alta disponibilidad y robustez, haciendo que sea muy utilizado en entornos web y de aplicaciones empresariales


![Logo de Servicios](./img/montar_servicios/logo.png)

## 1. Sitio Web con Phpmyadmin

### 1.1 Instalación de MariaDB y Comprobación

Primero instalamos mariadb-server , en nuestra máquina www

~~~
apt install mariadb-server
~~~

![Instalar MariaDB Server](./img/montar_servicios/1_install_mariadb_server.png)


Para comprobar que se instalo correctamente visualizamos los puertos y si esta el 3306 es porque esta instalado e iniciamos sesión en mysql

~~~
ss -ltn
~~~

![Ver Puertos](./img/montar_servicios/2_ver_puertos.png)

<br>

![Iniciar MYSQL](./img/montar_servicios/3_iniciar_mysql.png)


### 1.2 Instalación de PHP y Comprobación

Instalamos los servicios php que vamos a necesitar

~~~
apt install php libapache2-mod-php php-mysql php-gd php-intl php-xml
~~~

![Instalar PHP](./img/montar_servicios/4_install_php.png)

En el cliente comprobamos que esta el php instalado

![Especificaciones PHP](./img/montar_servicios/5_especificaciones_php.png)


### 1.3 Instalación de PHPmyadmin y Comprobación

Instalamos el phpmyadmin en el equipo utilizando el siguiente comando en el terminal 

~~~
apt install phpmyadmin
~~~

![Instalar phpmyadmin](./img/montar_servicios/6_install_phpmyadmin.png)

Vamos al cliente para probar si funciona bien el phpmyadmin

![Comprobar w10](./img/montar_servicios/7_comprobar_w10.png)