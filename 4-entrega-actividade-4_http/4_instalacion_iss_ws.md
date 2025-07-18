# 🪟🌐 Instalación y Configuración del Servidor IIS en Windows 
<br>

**📑 Indice**
- [🪟🌐 Instalación y Configuración del Servidor IIS en Windows](#-instalación-y-configuración-del-servidor-iis-en-windows)
- [💡 Servidor *``IIS``* en Windows](#-servidor-iis-en-windows)
  - [🏗️ 1. Instalación del Servidor *``IIS``*](#️-1-instalación-del-servidor-iis)
  - [2. ⚙️🌍 Configuración del Sitio Global](#2-️-configuración-del-sitio-global)
  - [🧱🌐 3. Creación de un Nuevo Sitio Web](#-3-creación-de-un-nuevo-sitio-web)
  - [🔁🔒 4. Redirección de HTTP a HTTPS](#-4-redirección-de-http-a-https)

<br>

# 💡 Servidor *``IIS``* en Windows 
<br>

> 📡 *``IIS (Internet Information Services)``* es el servidor web de Windows Server que permite hospedar páginas y aplicaciones web .
> 🔧 Soporta *``ASP.NET``* , bases de datos *``SQL``* , múltiples sitios y ofrece herramientas para gestión , diagnóstico y seguridad.
> ✅ Es ideal para crear y administrar sitios web en entornos Windows.

<br>

##  🏗️ 1. Instalación del Servidor *``IIS``* 
<br>

1 - Agregamos roles y características , son servicios necesarios 

![Agregando Roles 1](./img/iis_http/1_roles.png)
<br>
<br>


2 - Seleccionamos el rol *``servidor web (iss)``* este es el que nos interesa instalar . 

![Agregando Roles 2](./img/iis_http/2_roles.png)
<br>
<br>


3 - Agregamos componetes adicionales que necesitamos a la hora de usar *``iss``* 

![Agregando Roles 3](./img/iis_http/3_roles.png)
<br>
<br>


3 - Una vez instalado todo , vamos a la configuración del servidor  
 
![Acceso a ISS](./img/iis_http/1_iis.png)
<br>
<br>


## 2. ⚙️🌍 Configuración del Sitio Global 
<br>


1 - Habilitar el examen de directorio para todos los sitios 

![Examen de Directorios](./img/iis_http/2_iis.png)
<br>
<br>

2 - Los archivos por defecto solo mostrar los sitios *``index.html``* y *``default``* (no habrá más)

![Directorios Predeterminados](./img/iis_http/3_iis.png)
<br>
<br>


##  🧱🌐 3. Creación de un Nuevo Sitio Web 
<br>

1 - Crear un sitio virtual llamado *``masofieiis.gal``*

![Creando Sitio 1](./img/iis_http/4_iis.png)
<br>
<br>

2 - En el raíz hay que tener *``c:/masofieiis.gal``* y atender peticiones tanto por *``ip``* que por nombre (*``www.masofieiis.gal``*)

![Creando Sitio 2](./img/iis_http/5_iis.png)
<br>
<br>

3 - Agregamos un directorio virtual o sea un *``(alias)``*  
![Directorio Virtual](./img/iis_http/6_iis.png)
<br>
<br>

4 - El directorio virtual se denominará *``privado``* , este esta situado en *``c:/privado``* .

![Directorio Virtual 2](./img/iis_http/7_iis.png)
<br>
<br>

5 - Como podemos ver el directorio virtual se ha creado correctamente

![Directorio Virtual 2](./img/iis_http/8_iis.png)
<br>
<br>

6 - Cuando se produzca un error *``404``* deberás mostrar una página llamada *``error_404.html``* .

*``Esta página deberá contener el texto "Cometiste un ERROR 404"  , no se encontrado ningún resultado en la búsqueda``*.

<br>

Primero creamos el fichero de error en el directorio del sitio

![Creando Error 404 (1)](./img/iis_http/9_iis.png)
<br>
<br>

En las páginas de errores del sitio añadimos el error *``404``* que hemos creado .

![Creando Error 404 (2)](./img/iis_http/10_iis.png)
<br>
<br>

7 - Comprobamos el error , buscando una página que no es valida o sea que no existe  

![Comprobando Error 404](./img/iis_http/11_iis.png)
<br>
<br>

8 - Creamos un archivo llamado *``privado.html``* en el dictorio virtual *``privado``* . Dentro que tenga un mensaje de bienvenida (*``Bienvenido a esta carpeta PRIVADO del sitio web masofieiis.gal``*) .

![Creando Error 404 (2)](./img/iis_http/12_iis.png)
<br>
<br>

9 - El directorio tiene que tener *``autenticación basic``* o sea tiene que tener contraseña .

![Autenticación Basic 1](./img/iis_http/13_iis.png)
<br>
<br>

10 - Hay un usuario por defecto en *``iis``* llamado *``IUSR``* , le damos los permisos necesarios para este directorio . 

![Autenticación Basic 2](./img/iis_http/14_iis.png)
<br>
<br>

11 - Creamos un nuevo usuario para acceder al directorio virtual . 

![Autenticación Basic 3](./img/iis_http/15_iis.png)
<br>
<br>

12 - Cuando intentamos iniciar nos da error , esto pasa porque los directorios predeterminados eran *``index.html``* y *``default.asp``* . Este no aparece porque tiene otro nombre *``privado.html``* .

![Autenticación Basic 4](./img/iis_http/16_iis.png)
<br>
<br>

13 - Para solucionarlo solo hay que añadir la extensión del archivo o sea *``.html``* lo que estabamos haciendo era buscar el directorio completo y no el fichero en especifico .

![Autenticación Basic 5](./img/iis_http/17_iis.png)
<br>
<br>


## 🔁🔒 4. Redirección de HTTP a HTTPS 
<br>

1 - Creamos un certificado autofirmado y le damos un nombre .

![Re-dirección de http a https 1](./img/iis_http/18_iis.png)
<br>
<br>

2 - Modificamos en el enlace del certificado , para rediriguir al puerto *``443``* 

![Re-dirección de http a https 2](./img/iis_http/19_iis.png)
<br>
<br>

3 - Cuando lo tengamos así , solo hay que añadir el certificado creado anteriormente

![Re-dirección de http a https 3](./img/iis_http/20_iis.png)
<br>
<br>

4 - En el navegador añadimos la misma *``url``* pero en vez de añadir *``http``* añadimos *``https``* , luego nos muestra una ⚠️ advertencia , avandamos y aceptamos .

![Re-dirección de http a https 4](./img/iis_http/21_iis.png)
<br>
<br>

5 - Nos ha redirigido correctamente , también podemos ver el certificado que hemos creado antes .

![Re-dirección de http a https 5](./img/iis_http/22_iis.png)
<br>
<br>

**💡 Consejo Final**
>
>Antes de publicar tu sitio web en *``IIS``* 🪟🌐, asegúrate de que esté correctamente configurado con certificados válidos 🔒✅ para *``HTTPS``* y que la redirección esté activa 🔁🌍.
>Además , verifica los permisos y rutas físicas del sitio para evitar errores de acceso 🚫📁. 