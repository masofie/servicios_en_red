# 📘 Guía Básica de VSFTPD

**📑 Indice**

- [📘 Guía Básica de VSFTPD](#-guía-básica-de-vsftpd)
  - [📝 Explicación del Fichero](#-explicación-del-fichero)
- [📄 1. Fichero Básico: vsftpd.conf](#-1-fichero-básico-vsftpdconf)
  - [📁 1.1 Configuración del Servidor](#-11-configuración-del-servidor)
  - [👤 2. Configuración del Usuario **`anonymous`**](#-2-configuración-del-usuario-anonymous)
  - [👨‍💻 3. Configuración de Usuarios Locales](#-3-configuración-de-usuarios-locales)

<br>

## 📝 Explicación del Fichero

En esta guía veremos algunas de las opciones esenciales del archivo de configuración vsftpd.conf, que nos permiten dejar listo un servidor FTP de forma básica y funcional, sin complicaciones.

🗂️ Estas configuraciones son ideales para comenzar y comprender cómo opera el servicio **VSFTPD** paso a paso.

> ⚠️ Advertencia: ¡Recuerda reiniciar el servicio después de cada cambio! Si no lo haces, los ajustes no tendrán efecto.
> 
> 📌 Comando útil: sudo systemctl restart vsftpd

<br>

# 📄 1. Fichero Básico: vsftpd.conf
<br>

## 📁 1.1 Configuración del Servidor

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
# 💬 Añadir mensaje de bienvenida
ftpd_banner=Bienvenido

# 👥 Número máximo de conexiones simultáneas
max_clients=5

# 🌐 Máximo de conexiones desde la misma IP
max_per_ip=10

# ⏳ Tiempo de espera para conexiones de datos
data_connection_timeout=600

# 💤 Tiempo de sesión inactiva
idle_session_timeout=600

# 🔁 Activar modo pasivo
pasv_enable=YES

# 🕒 Usar hora local del servidor
use_localtime=YES

# 🔐 Crear certificado SSL
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/vsftpd.pem -out /etc/ssl/certs/vsftpd.pem

# 📎 Añadir y aceptar certificado SSL
rsa_cert_file=/etc/ssl/certs/vsftpd.pem
rsa_private_key_file=/etc/ssl/private/vsftpd.key
ssl_enable=YES

# 🔒 Forzar cifrado SSL para datos y login
force_local_data_ssl=YES
force_local_logins_ssl=YES

# 📄 Ver logs desde fichero
xferlog_enable=YES
xferlog_std_format=YES
xferlog_file=/var/log/vsftpd.log
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

## 👤 2. Configuración del Usuario **`anonymous`**

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
# 🚫 Acceso anónimo desactivado (por seguridad)
anonymous_enable=NO

# 🐢 Límite de velocidad para usuarios anónimos
anon_max_rate=1000

# 📤 Permitir subida de archivos (anónimo)
anon_upload_enable=YES

# 📝 Permitir escritura en directorios
anon_mkdir_write_enable=YES

# 🔐 Uso de SSL para anónimos (desactivado)
allow_anon_ssl=NO

# 🔑 Pedir o no contraseña al usuario anónimo
no_anon_password=NO
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

## 👨‍💻 3. Configuración de Usuarios Locales

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
# ✅ Permitir conexiones de usuarios locales
local_enable=YES

# 📝 Permitir escritura para usuarios locales
write_enable=YES

# 🚀 Velocidad máxima de descarga para locales
local_max_rate=1000

# 📥 Permitir subir archivos
download_enable=YES

# 📐 Permisos predeterminados para archivos
local_umask=022

# 🏠 Enjaular usuarios en su directorio personal
chroot_local_user=YES
allow_writeable_chroot=YES
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


<br>

**💡 Consejo Final**

>🔧 Recuerda siempre reiniciar el servicio después de cada cambio en el fichero de configuración:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo systemctl restart vsftpd
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
>
>🛡️ Evita permitir acceso anónimo salvo que sea estrictamente necesario y controlado.
>
>📈 Verifica los logs regularmente para detectar posibles accesos no autorizados.