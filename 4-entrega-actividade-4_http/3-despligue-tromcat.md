# 🪟🐱🚀 Despliegue de Tomcat en Windows 

**📑 Indice**
- [🪟🐱🚀 Despliegue de Tomcat en Windows](#-despliegue-de-tomcat-en-windows)
  - [🌐⚙️ ¿Qué es Apache Tomcat?](#️-qué-es-apache-tomcat)
  - [❌ 1. Error al iniciar Tomcat](#-1-error-al-iniciar-tomcat)
  - [🛠️ 2. Solucionar errores comunes](#️-2-solucionar-errores-comunes)
  - [👤 1.3 Crear usuario "manager" en Tomcat](#-13-crear-usuario-manager-en-tomcat)
  - [📎 2. Información adicional sobre el despliegue](#-2-información-adicional-sobre-el-despliegue)

<br>

##  🌐⚙️ ¿Qué es Apache Tomcat?
<br> 

**Tomcat** es un módulo web que permite la integración de **Tomcat en XAMPP**, un paquete de software que incluye **``Apache``** , **``MySQL``** , **``PHP``** y **``Perl``**. 

**Tomcat** es un servidor web de código abierto que se utiliza principalmente para ejecutar aplicaciones Java en un entorno web. Al integrar Tomcat en `**XAMPP** , los usuarios pueden acceder a funcionalidades avanzadas para ejecutar aplicaciones **Java** y servlets en su servidor web local. Esto es útil para desarrolladores que trabajan con aplicaciones **Java** y desean probarlas en un entorno seguro y controlado antes de implementarlas en un entorno de producción.

![Logo Tromcat](./img/despligue_tromcat/logo_tromcat.png)
<br>

## ❌ 1. Error al iniciar Tomcat
<br>

Este es el error que nos da al iniciar el **``TROMCAT``** porque le hace falta una variable 
<br><br>


![Error al Iniciar Tromcat](./img/despligue_tromcat/1_crear_usuarios_tromcat.png)
<br><br>

## 🛠️ 2. Solucionar errores comunes 
<br>

Para solucionar el problema del inicio de **``tromcat``** debemos añadir la variable **``java_home``** de la siguiente manera : 
<br><br>

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
HKEY_LOCAL_MACHINE
FOFTWARE
JavaSoft
Java Development Kit >> JavaHome >> ruta del jdk
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



![Creción de Directorios](./img/despligue_tromcat/1_crear_usuarios_tromcat.png)
<br><br>

Volvemos comprobar que **tromcat** se ha iniciado correctamente
<br>

![Tromcat iniciado correctamente](./img/despligue_tromcat/2_variable_java_home.png)



## 👤 1.3 Crear usuario "manager" en Tomcat
<br>


Para poder manejaer como administrador podemos crear un usaurio para iniciar sesión, modificando el siguiente fichero :
<br><br>

![Tromcat crear usuario 1](./img/despligue_tromcat/1_crear_usuarios_tromcat.png)
<br><br>

Volvemos ha la página principal y damos clic a **Manager App** . 
<br><br>

![Tromcat crear usuario 2](./img/despligue_tromcat/1_variable_java_home.png)
<br><br>

Iniciamos con el usuario que hemos agreagado antes y como podemos ver inicia correctamente 
<br><br>

![Tromcat crear usuario 3](./img/despligue_tromcat/3_crear_usuarios_tromcat.png)
<br><br><br>


## 📎 2. Información adicional sobre el despliegue 

> ***Página oficial :*** 
>
> - ***https://tomcat.apache.org/***
>
>
> ***Wikipedia :***  
>
> - ***https://es.wikipedia.org/wiki/Tomcat*** 
