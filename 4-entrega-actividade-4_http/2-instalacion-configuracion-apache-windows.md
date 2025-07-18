# 🪟🛠️⚙️ Instalación y Configuración de Apache en Windows con XAMPP 
<br>

**📑 Indice**
- [🪟🛠️⚙️ Instalación y Configuración de Apache en Windows con XAMPP](#️️-instalación-y-configuración-de-apache-en-windows-con-xampp)
  - [💡 Qué es y su utilidad ?](#-qué-es-y-su-utilidad-)
  - [🛠️ 1. Instalación y Congiguración](#️-1-instalación-y-congiguración)
    - [🔧 1.1 Instalación de *``Java``*](#-11-instalación-de-java)
    - [💽 1.2 Instalación de XAMPP](#-12-instalación-de-xampp)
    - [❗🧰 1.3 Corrección de Errores Comunes](#-13-corrección-de-errores-comunes)
    - [⚙️ 1.4 Configuración de Variables de Entorno](#️-14-configuración-de-variables-de-entorno)

<br>

## 💡 Qué es y su utilidad ?
<br>

>**XAMPP** es un software gratuito y de código abierto que permite crear un entorno de desarrollo web en sistemas Windows. Incluye varios componentes como *``apache``*, *``mysql``*, *``php``* y *``perl``*, que son necesarios para configurar un servidor web local en tu computadora. Esto facilita el desarrollo y prueba de aplicaciones web antes de subirlas a un servidor en línea..

<br>

## 🛠️ 1. Instalación y Congiguración
<br>

### 🔧 1.1 Instalación de *``Java``* 

Descargar el **`jdk`** para java , lo utilizaremos para iniciar nuestro xampp :

- **Enlace :** **https://www.oracle.com/es/java/technologies/downloads/#jdk22-windows**
<br>

![Descarga de Java](./img/install_xampp/1_xammp_windows.png)
<br>
<br>


### 💽 1.2 Instalación de XAMPP
<br>

Instalamos xampp utlizando formato *``zip``* , para configurarlo desde cero .

- **Enlace :** **https://sourceforge.net/projects/xampp/files/XAMPP%20Windows/8.2.12/**
<br>

![Descarga de XAMMP](./img/install_xampp/2_xammp_windows.png)
<br>
<br>


### ❗🧰 1.3 Corrección de Errores Comunes 
<br>

Una vez intalado y descomprimido , ejecutamos el xammp pero nos da un error . Ese error viene de las *``variables de entorno``* 

![Mostrando Error de inicio de XAMMP](./img/install_xampp/3_error_en_xampp.png)
<br>
<br>


### ⚙️ 1.4 Configuración de Variables de Entorno  

1 - Solucionamos el problema añadiendo el *``jdk (java)``* en las *``variables de entorno``* . Copiamos la ruta donde esta el *``ldk``* y al final añadimos el directorio *``bin``* para que funcione .


![Ruta del jdk](./img/install_xampp/4_variable_entono1.png)
<br>
<br>


2 - En las *``variables de netorno del sistema``* en la variable *``path``* añadimos la ruta del *``jdk``*

![Añadiendo varaiable en path](./img/install_xampp/4_variable_entono2.png)
<br>
<br>


3 - Iniciamos nuevamente el xampp , se ha iniciado correctamente sin errores

![Añadiendo varaiable en path](./img/install_xampp/5_xampp_corregido.png)
<br>
<br>


4 - En xampp iniciamos el *``apache``* y el *``mysql``* y nos damos cuenta que funciona correctamente

![Añadiendo varaiable en path](./img/install_xampp/6_iniciando_mysql_apache.png)
<br>
<br>


5 - Comprobamos el funcionamiento del *``apache``* desde el navegador

![Añadiendo varaiable en path](./img/install_xampp/6_localhost_apache.png)
<br>
<br>



**💡Consejo Final**

>Después de instalar *``XAMPP``* , asegúrate de ejecutar el panel como administrador 🧑‍💻 y verificar que los puertos necesarios *``(80 y 443)``* no estén en uso por otras aplicaciones como *``Skype``* o *``IIS``* 🛑.
>También es recomendable guardar una copia de seguridad de tus archivos de configuración antes de hacer cambios importantes 🗂️🛟.