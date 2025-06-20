# 🖥️📂 Servidor FTP en FileZilla Server

**📑 Indice**

- [🖥️📂 Servidor FTP en FileZilla Server](#️-servidor-ftp-en-filezilla-server)
  - [🧾 Definición](#-definición)
  - [⚙️ 1. Configuración](#️-1-configuración)
    - [🛠️ 1.1 Administrar Servidor](#️-11-administrar-servidor)
    - [👤 Creación de Usuarios](#-creación-de-usuarios)
    - [👥 Creación de Grupos](#-creación-de-grupos)

<br>

## 🧾 Definición

Claro, un servidor **FTP Filezilla Server** es un software de servidor ***FTP (Protocolo de Transferencia de Archivos)*** que permite a los usuarios conectarse y transferir archivos a través de Internet de forma segura. 

**Filezilla Server** es una aplicación de servidor **FTP** de código abierto que es ampliamente utilizado debido a su facilidad de uso y fiabilidad. Permite la configuración de usuarios con distintos niveles de acceso, la encriptación de las conexiones para mayor seguridad, y la supervisión de las transferencias de archivos en tiempo real.

En resumen, un servidor **FTP** Filezilla Server es una herramienta que permite a los usuarios compartir y transferir archivos de forma segura a través de Internet utilizando el protocolo **FTP**.

![Logo de Filezilla Server](./img/filezillaserver/logo_filezilla.png)

<br>

##  ⚙️ 1. Configuración 
<br>

### 🛠️ 1.1 Administrar Servidor

Cambiar contraseña y puerto del servidor 

![Password and port](./img/filezillaserver/cambio_puerto.png)


Tiempo global o general para login y actividad en el servidor 

![Tiempo login-actividad](./img/filezillaserver/timpo_global.png)

Mensaje de Bienvenida al servidor 

![Mensaje del Baner](./img/filezillaserver/mensaje_bienvenida.png)

Para crear un certicado podemos hacerlo de la siguiente manea , es un certicado personal 

![Certicado cn](./img/filezillaserver/crear_certificado_cm.png)


Para ver los ***logs*** modemos verlo desde la siguiente ruta 

![Ver Logs](./img/filezillaserver/ver_logs.png)

### 👤 Creación de Usuarios

Crear usuarios en el servidor con sus directorios

![Crear Usuarios](./img/filezillaserver/crear_user.png)

Para admitir solo usuarios desde una **IP** podemos hacerlo de la siguiente , en este caso la vanos ha admitir 


![Admitir una ip](./img/filezillaserver/admitir_ip.png)

### 👥 Creación de Grupos
Hay quw crear los grupos con sus despectivas ***pahs***


![Crear Grupos](./img/filezillaserver/crear_grupos.png)

<br>

**🧠💡 Consejo Final**

> Recuerda siempre configurar correctamente los permisos de usuario y grupo para evitar accesos no autorizados.
> Además, si tu servidor **FTP** va a estar expuesto a internet, considera usar **FTP** sobre **TLS (FTPS)** para mantener la transferencia de archivos segura. 🔐🌐
>
> Un servidor bien configurado es clave para evitar errores y garantizar una experiencia fluida. ✅📁