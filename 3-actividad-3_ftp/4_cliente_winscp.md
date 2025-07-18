# 🔐🖥️ Cliente WinSCP 
<br>

**📑 Indice**
- [🔐🖥️ Cliente WinSCP](#️-cliente-winscp)
  - [📝 Definición](#-definición)
  - [🔍 1. Comprobaciones](#-1-comprobaciones)
    - [▶️ 1.1 Iniciar Sesión](#️-11-iniciar-sesión)
    - [🔄 1.2 Sincronizar Directorios](#-12-sincronizar-directorios)

<br>

## 📝 Definición

*``WinSCP``* es un cliente de transferencia de archivos gratuito y de código abierto para los protocolos de transferencia de archivos *``SCP (Secure Copy Protocol)``* y *``SFTP (SSH File Transfer Protocol)``*. Permite a los usuarios conectarse de forma segura a servidores remotos para transferir archivos de forma rápida y segura. *``WinSCP``* ofrece una interfaz de usuario intuitiva y funciones avanzadas como la sincronización de directorios, la edición remota de archivos y la gestión de sitios favoritos.

![Logo](./img/winscp/logo_winscp.png)
<br>
<br>

## 🔍 1. Comprobaciones
<br>

### ▶️ 1.1 Iniciar Sesión

Para inciar sesión a un servidor *``ftp``* desde *``winscp``* . Para eso creamos un sitio .

![Iniciar Seseión con Usuarios](./img/winscp/1_inciar_sesion.png)
<br>
<br>


### 🔄 1.2 Sincronizar Directorios

1 - Sincronizamos los directorios locales y remotos . Seleccionamos antes los directorios que queremos sincronizar y seleccionamos *``ambos``* para sincronizar los al mismo tiempo .


![Sincronizar Directorios 1](./img/winscp/2_sincronizar_directorios_1.png)
<br>
<br>



2 - Confirmamos los directorios que queremos sincronizar y *``aceptamos``* 


![Sincronizar Directorios 2](./img/winscp/3_sincronizar_directorios_2.png)
<br>
<br>


3 - Los directorios se han sincronizado correctamente 


![Sincronizar Directorios 3](./img/winscp/4_sincronizar_directorios_3.png)
<br>
<br>

**💡 Consejo Final**

> Para mantener una transferencia segura y eficiente, asegúrate de usar siempre conexiones cifradas *``(SFTP o SCP)``* en *``WinSCP``* .
> Además, aprovecha la función de sincronización para evitar pérdidas de archivos y mantener tus carpetas siempre actualizadas. 🔐📂✅