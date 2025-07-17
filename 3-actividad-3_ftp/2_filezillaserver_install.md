# 🖥️📂 Servidor FTP en FileZilla Server
<br>

**📑 Indice**
- [🖥️📂 Servidor FTP en FileZilla Server](#️-servidor-ftp-en-filezilla-server)
  - [🧾 Definición](#-definición)
  - [⚙️ 1. Configuración](#️-1-configuración)
    - [🛠️ 1.1 Administrar Servidor](#️-11-administrar-servidor)
    - [👤 Creación de Usuarios](#-creación-de-usuarios)
    - [👥 Creación de Grupos](#-creación-de-grupos)

<br>

## 🧾 Definición
<br>

Claro, un servidor *``FTP Filezilla Server``* es un software de servidor *``FTP (Protocolo de Transferencia de Archivos)``* que permite a los usuarios conectarse y transferir archivos a través de Internet de forma segura. 

*``Filezilla Server``* es una aplicación de servidor *``ftp``* de código abierto que es ampliamente utilizado debido a su facilidad de uso y fiabilidad. Permite la configuración de usuarios con distintos niveles de acceso, la encriptación de las conexiones para mayor seguridad, y la supervisión de las transferencias de archivos en tiempo real.

En resumen, un servidor *``ftp``* Filezilla Server es una herramienta que permite a los usuarios compartir y transferir archivos de forma segura a través de Internet utilizando el protocolo *``ftp``*.

![Logo de Filezilla Server](./img/filezillaserver/logo_filezilla.png)
<br>
<br>

##  ⚙️ 1. Configuración 
<br>

### 🛠️ 1.1 Administrar Servidor

1 - Cambiar contraseña y puerto del servidor 

![Password and port](./img/filezillaserver/cambio_puerto.png)
<br>
<br>



2 - Tiempo global o general para login y actividad en el servidor 

![Tiempo login-actividad](./img/filezillaserver/timpo_global.png)
<br>
<br>


3 - Mensaje de Bienvenida al servidor 

![Mensaje del Baner](./img/filezillaserver/mensaje_bienvenida.png)
<br>
<br>


4 - Para crear un certicado podemos hacerlo de la siguiente manea , es un certicado personal 

![Certicado cn](./img/filezillaserver/crear_certificado_cm.png)
<br>
<br>



5 - Para ver los *``logs``* modemos verlo desde la siguiente ruta 

![Ver Logs](./img/filezillaserver/ver_logs.png)
<br>
<br>



### 👤 Creación de Usuarios

1 - Crear usuarios en el servidor con sus directorios

![Crear Usuarios](./img/filezillaserver/crear_user.png)
<br>
<br>


2 - Para admitir solo usuarios desde una *``ip``* podemos hacerlo de la siguiente , en este caso la vanos ha admitir 


![Admitir una ip](./img/filezillaserver/admitir_ip.png)
<br>
<br>


### 👥 Creación de Grupos

Hay que crear los grupos con sus despectivas *``pahs``*


![Crear Grupos](./img/filezillaserver/crear_grupos.png)

<br>

**🧠💡 Consejo Final**

> Recuerda siempre configurar correctamente los permisos de usuario y grupo para evitar accesos no autorizados.
> Además, si tu servidor *``ftp``* va a estar expuesto a internet, considera usar *``ftp``* sobre *``TLS (FTPS)``* para mantener la transferencia de archivos segura. 🔐🌐
>
> Un servidor bien configurado es clave para evitar errores y garantizar una experiencia fluida. ✅📁