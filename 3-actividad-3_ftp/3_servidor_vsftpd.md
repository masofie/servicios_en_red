# Servidor vsftpd

## Indice 

## 1. Configuración en el Servidor 

Ver los logs de ftp , están en el directorio /var/log/vsftpd.log . 

![Logs del Servidor](./img/vsftpd/logs_servidor.png)

Añadir el mensaje de bienvenida al conectarse en el servidor  

![Mensaje del Baner](./img/vsftpd/mensaje_baner.png)

Máximo número de conexiones  

![Maximo clientes](./img/vsftpd/maximo_clientes.png)

Tiempo de conexión

![Tiempo de conexion](./img/vsftpd/tiempo_conexion.png)

## 2. Usuarios anónimos (anonymous)

Permitir conexión con el usuario anonymous y escritura 

![Permitir usuarios anonymous](./img/vsftpd/conexiones_anonimas.png)

## 3. Usuarios Locales 

Permitir que los conexiones de los usuarios locales y poder escribir en el servidor 

![Conexiones a usuarios locales](./img/vsftpd/conexiones_locales.png)

Permitir que usuarios específicos se puedan conectar si o no (hay que crear el fichero antes) . El usuario dadmin no se va ha poder conectar al servidor , porque la denegación la tenemos en YES 

![Especificar lista de usuarios 1](./img/vsftpd/permitir_conexiones_1.png)
![Espercificar lista de usuarios 2](./img/vsftpd/permitir_conexiones_2.png)

Permitir o no ver los home de los demás usuarios . Aquí estamos diciendo que solo puede ver su misma home porque esta a YES 

![Home de Usuarios](./img/vsftpd/home_usuario.png)

Creamos un certificado y añadimos las rutas de la clave privada y la publica y forzar a que pida el certificado (o sea obligarlo)


![Añadir Certificado](./img/vsftpd/certificado.png)