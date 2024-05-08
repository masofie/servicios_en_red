# Guia Básica de ***VSFTPD***

## Explicación del Fichero


Estas son algunas especificaciones que podemos utilizar para la configuración del servidor ***vsftpd*** , con esto podemos configurar el servidor de una manera básica y bastante facil .

- **Advertencia :** ***no funcionara si no se reincia nuestor servicio***
##
## Fichero Básico de ***vsftpd.conf***


~~~
# Configuración del servidor vsftpd

# 1. Configuración del servidor

        # Añadir mensaje de bienvenida
        ftpd_banner=Bienvenido
        # Maximo número de conexiones simultaneas
        max_clients=5
        # Limite de usuarios maximos de conexiones que se puedan realizar desde una misma IP
        max_per_ip=10
        # Permitir el tiempo de espera de conexiones establecidas
        data_connection_timeout=600
        # Tiempo de conexion de inactividad
        idle_session_timeout=600
        # Activar o no el modo pasivo
        pasv_enable=YES
        # Activar la hora local del servidor
        use_localtime=YES
        # Crear certificado
        openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/vsftpd.pem -out /etc/ssl/certs/vsftpd.pem
        # Añadir y aceptar certicado openssl
        rsa_cert_file=/etc/ssl/certs/vsftpd.pem
        rsa_private_key_file=/etc/ssl/private/vsftpd.key
        ssl_enable=YES
        # Forzar certicado si/no
        force_local_data_ssl=YES
        force_local_logins_ssl=YES
        #Ver los logs desde un fichero
        xferlog_enable=YES
        xferlog_std_format=YES
        xferlog_file=/var/log/vsftpd.log

# 2. Configuracion de usuario anonymous

        # Permitir o no el acceso anonimo (por defecto esta desactivado)
        anonymous_enable=NO
        # Permitir o no los usuarios locales puedan escribir
        anon_max_rate=1000
        # Permir o no que anonimo suba ficheros
        anon_upload_enable=YES
        # Permitir o no que anonimo pueda escribir
        anon_mkdir_write_enable=YES
        # Permitir o no usar certificado ssl
        allow_anon-ssl=NO
        # Pedir contraseña o no al usuario anonimo
        no_anon_password=NO

# 3. Configuracion de usuarios locales

        # Permiti o no la conexion de usuarios locales
        local_enable=YES
        # Permitir o no los usuarios locales puedan escribir
        write_enable=YES
        # Ancho de banda de descarga pata usuarios locales
        local_max_rate=1000
        # Permitir que los usuarios locales puedan subir ficheros
        download_enable=YES
        # Establecer permisos a usuarios locales
        local_umask=022
        # Enjaular usuarios en su /home (solo ver su propia home)
        chroot_local_user=YES
        allow_writeable_chroot=YES
~~~
