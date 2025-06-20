# 🧰 Comandos Básicos **`(scp, pscp y wget)`** en FTP

**📑 Indice**

- [🧰 Comandos Básicos **`(scp, pscp y wget)`** en FTP](#-comandos-básicos-scp-pscp-y-wget-en-ftp)
  - [1. 🔐 scp – Copia segura entre máquinas Linux](#1--scp--copia-segura-entre-máquinas-linux)
  - [2. 💻 pscp – Copia segura desde Windows](#2--pscp--copia-segura-desde-windows)
  - [3. 🌐 wget – Descarga de archivos desde FTP o HTTP](#3--wget--descarga-de-archivos-desde-ftp-o-http)

<br>

## 1. 🔐 scp – Copia segura entre máquinas Linux
<br>

El comando **`scp`** se usa para transferir archivos de forma segura entre dos equipos mediante SSH.
Sirve para enviar archivos a un servidor o copiarlos desde él.

**📌 Ejemplo básico :**

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
scp archivo.txt usuario@ip:/ruta/de/destino
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


## 2. 💻 pscp – Copia segura desde Windows
<br>

**`pscp`** es la versión de **`scp`** para sistemas Windows, y forma parte de las herramientas de **PuTTY** .
Permite enviar y recibir archivos con seguridad desde la línea de comandos de Windows.

**📌 Ejemplo básico :**

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
pscp archivo.txt usuario@ip:/ruta/remot
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

## 3. 🌐 wget – Descarga de archivos desde FTP o HTTP
<br>

**`wget`** es una herramienta que permite descargar archivos desde servidores **FTP** o web.
Se utiliza comúnmente en Linux, aunque también está disponible en Windows.

**📌 Ejemplo básico para FTP :**

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
wget ftp://usuario:contraseña@ip/archivo.txt
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

**También se puede usar sin autenticación si el servidor FTP lo permite.**


**💡 Consejo Final**

> - 🔄 Usa scp o pscp cuando necesites seguridad (SSH).
> - 📥 Usa wget si solo vas a descargar archivos desde un servidor sin editar nada.
> - ✅ Antes de usar los comandos, asegúrate de tener acceso, permisos y conocer la dirección IP o nombre del servidor.