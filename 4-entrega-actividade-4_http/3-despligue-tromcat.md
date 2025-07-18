# 🪟🐱🚀 Despliegue de Tomcat en Windows 
<br>

**📑 Indice**
- [🪟🐱🚀 Despliegue de Tomcat en Windows](#-despliegue-de-tomcat-en-windows)
  - [🌐⚙️ ¿Qué es Apache Tomcat?](#️-qué-es-apache-tomcat)
  - [❌ 1. Error al Iniciar Tomcat](#-1-error-al-iniciar-tomcat)
  - [🛠️ 2. Solucionar Errores Comunes](#️-2-solucionar-errores-comunes)
  - [👤 1.3 Crear Usuario *``manager``* en Tomcat](#-13-crear-usuario-manager-en-tomcat)
  - [📎 2. Información Adicional sobre el Despliegue](#-2-información-adicional-sobre-el-despliegue)

<br>

##  🌐⚙️ ¿Qué es Apache Tomcat?
<br> 

> Tomcat es un módulo web que permite la integración de **Tomcat en XAMPP**, un paquete de software que incluye *``apache``* , **``mysql``** , **``php``** y **``perl``**. 
>
> Es un servidor web de código abierto que se utiliza principalmente para ejecutar aplicaciones *``java``* en un entorno web. Al integrar *``tomcat``* en xampp , los usuarios pueden acceder a funcionalidades avanzadas para ejecutar aplicaciones *``java``* y servicios en su servidor web local. Esto es útil para desarrolladores que trabajan con aplicaciones *``java``* y desean probarlas en un entorno seguro y controlado antes de implementarlas en un entorno de producción.

![Logo Tromcat](./img/despligue_tromcat/logo_tromcat.png)
<br>
<br>


## ❌ 1. Error al Iniciar Tomcat
<br>

Cuando intentamos iniciar *``tomcat``* no deja hacerlo , da error . Porque le falta una variable . 

![Error al Iniciar Tromcat](./img/despligue_tromcat/1_crear_usuarios_tromcat.png)
<br>
<br>


## 🛠️ 2. Solucionar Errores Comunes 
<br>

1 - Para solucionar el problema , debemos añadir la variable *``java_home``* en el fichero *``conf``* (fichero de configuración) .

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
HKEY_LOCAL_MACHINE
FOFTWARE
JavaSoft
Java Development Kit >> JavaHome >> ruta del jdk
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

![Creción de Directorios](./img/despligue_tromcat/1_crear_usuarios_tromcat.png)
<br>
<br>

2 - Comprobamos iniciando *``tromcat``* nuevamente , se ha inciciado correctamente .

![Tromcat iniciado correctamente](./img/despligue_tromcat/2_variable_java_home.png)
<br>
<br>


## 👤 1.3 Crear Usuario *``manager``* en Tomcat
<br>

1 - Si queremos iniciar sesión como *``administrador``* , creamos un usuario moficando el fichero de configuración . 


![Tromcat crear usuario 1](./img/despligue_tromcat/1_crear_usuarios_tromcat.png)
<br>
<br>


2 - En el editor de registro , y añadimos una cadena  con *``jdk``* .

~~~~
# Ruta 
HKEY_LOCAL_MACHINE\SOFTWARE\JavaSoft\Java Development Kit

# Añadir Cadena
Nombre + jdk
~~~~

![Tromcat crear usuario 2](./img/despligue_tromcat/1_variable_java_home.png)
<br>
<br>


3 - Iniciamos con el usuario *``admin``* , como podemos ver se ha iniciado correctamente .

![Tromcat crear usuario 3](./img/despligue_tromcat/3_crear_usuarios_tromcat.png)
<br>
<br>


## 📎 2. Información Adicional sobre el Despliegue 
<br>

> **Página oficial :**
>   - *``https://tomcat.apache.org/``*
> 
> **Wikipedia :**  
>   - *``https://es.wikipedia.org/wiki/Tomcat``*

<br>
<br>

**💡 Consejo Final**

> Antes de iniciar *``tomcat``* 🐱, asegúrate de que *``java_home``* esté correctamente configurada ⚙️☕ y que el puerto *``8080``* no esté siendo utilizado por otra aplicación 🚫🔌.
> Además, usa credenciales seguras para el usuario *``manager``* 👤🔐 y restringe el acceso si el servidor está en red pública 🌐🔒