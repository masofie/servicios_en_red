# Instalación y Configuración de Apache en Windows 

- [Instalación y Configuración de Apache en Windows](#instalación-y-configuración-de-apache-en-windows)
  - [1 Qué es XAMPP y para que se uiliza](#1-qué-es-xampp-y-para-que-se-uiliza)
  - [1.1 Instalación de Java](#11-instalación-de-java)
  - [1.2 Instalación de XAMPP](#12-instalación-de-xampp)
  - [2.0 Correción de Error](#20-correción-de-error)
    - [2.1 Variables de Entorno](#21-variables-de-entorno)

## 1 Qué es XAMPP y para que se uiliza 
<br>

XAMPP es un software gratuito y de código abierto que permite crear un entorno de desarrollo web en sistemas Windows. XAMPP incluye varios componentes como **Apache**, **MySQL**, **PHP** y **Perl**, que son necesarios para configurar un servidor web local en tu computadora. Esto facilita el desarrollo y prueba de aplicaciones web antes de subirlas a 
un servidor en línea..

![Imagen logo xampp](./img/install_xampp/portada_xammp.png)

## 1.1 Instalación de Java
<br>

Primero vamos a descargar el **jdk** para java que lo vamos a utilizar para iniciar nuestro xampp , lo puedes consultar en la siguiente url :

**ENLACE :** **https://www.oracle.com/es/java/technologies/downloads/#jdk22-windows**



![Descarga de Java](./img/install_xampp/1_xammp_windows.png)

## 1.2 Instalación de XAMPP
<br>

En este caso apara instalar xammp utilizaremos un formato zip , para configuralo desde cero . Lo podemos encontrar
en el siguiente enlace 

**ENLACE :** **https://sourceforge.net/projects/xampp/files/XAMPP%20Windows/8.2.12/**

![Descarga de XAMMP](./img/install_xampp/2_xammp_windows.png)


## 2.0 Correción de Error 
<br>

Cuando tenemos el xammp instalado y descomprimido lo ejecutamos pero nos da un error , ese error viene de las 
variables de entorno . El error ese el siguiente que se ve en la imagen :


![Mostrando Error de inicio de XAMMP](./img/install_xampp/3_error_en_xampp.png)
<br><br>



### 2.1 Variables de Entorno  

Para solucionar el problema añadimos el **jdk (java)** en las variables de entorno de la siguiente manera : 

Primero , copiamos la ruta de nustro **jdk** terminado en el directorio **bin** , asi como esta en la imagen 


![Ruta del jdk](./img/install_xampp/4_variable_entono1.png)
<br><br>

Luego vamos a nuestra variables de entorno del sistema y en el **path** añadimos la ruta del **jdk** lo hacemos de 
la siguiente manera : 
<br><br>

![Añadiendo varaiable en path](./img/install_xampp/4_variable_entono2.png)
<br><br>


Volvemos ha iniciar nuestro xampp y como podemos ver se ha iniciado correctamente
<br><br>

![Añadiendo varaiable en path](./img/install_xampp/5_xampp_corregido.png)
<br><br>

Iniciamos el **apache** y el **mysql** para ver si esta funcionando todo correctamente 

<br><br>
![Añadiendo varaiable en path](./img/install_xampp/6_iniciando_mysql_apache.png)
<br><br>

Comprobamos el funcionamiento del **APACHE** desde el navegador usando :
<br><br>


![Añadiendo varaiable en path](./img/install_xampp/6_localhost_apache.png)