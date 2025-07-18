# ⚙️📟🖥️ Cliente FTP desde Línea de Comandos (Terminal) 
<br>

**📑 Indice** 
- [⚙️📟🖥️ Cliente FTP desde Línea de Comandos (Terminal)](#️️-cliente-ftp-desde-línea-de-comandos-terminal)
  - [📝 Definición](#-definición)
  - [💻 1. Terminal Windows](#-1-terminal-windows)
    - [❓ 1.1 Ayuda *``ftp``*](#-11-ayuda-ftp)
    - [🔑 1.2 Métodos de Acceso](#-12-métodos-de-acceso)
      - [1️⃣ 1.2.1 Primer Método de Accesoo](#1️⃣-121-primer-método-de-accesoo)
      - [2️⃣ 1.2.2 Segundo Método de Acceso](#2️⃣-122-segundo-método-de-acceso)
    - [📤 1.3 Subir Archivo](#-13-subir-archivo)
    - [📊 1.4 Estado de la Sesión *``ftp``*](#-14-estado-de-la-sesión-ftp)
    - [🔤 1.5 Tipo de Formato](#-15-tipo-de-formato)
    - [📥 1.6 Descargar Archivo](#-16-descargar-archivo)
    - [📚 2. Bibliografía](#-2-bibliografía)

<br>

## 📝 Definición
<br>

Para usar un terminal que usa *``ftp``* como cliente, primero debes asegurarte de que el cliente de *``ftp``* esté instalado en tu terminal . Luego , puedes abrir una sesión de terminal y utilizar los comandos de *``ftp``* para conectarte a un servidor remoto y transferir archivos.

Recuerda que para utilizar *``ftp``* es necesario tener los permisos adecuados para acceder al servidor remoto . Además, asegúrate de proteger tus credenciales de acceso y no compartir información confidencial a través de *``ftp``* , ya que es un protocolo poco seguro en términos de encriptación de datos
<br>


## 💻 1. Terminal Windows
<br>

### ❓ 1.1 Ayuda *``ftp``*

1 - En *``ftp``* hay un comando de ayuda para ver los comandos que podemos utilizar .

~~~
?
~~~

![Ayuda FTP](./img/comandos_terminal/1_ayuda_terminal.png)
<br>
<br>



### 🔑 1.2 Métodos de Acceso
<br>

#### 1️⃣ 1.2.1 Primer Método de Accesoo

Usando la forma interactiva , primero primero el comando y luego abrimos la *``ip``* del servidor .

![Primer Métodos de Acceso](./img/comandos_terminal/2_primer_metodo_inicio.png)
<br>
<br>


#### 2️⃣ 1.2.2 Segundo Método de Acceso

Usando el comando completo + la *``ip``* del servidor , como se muestra 

![Segundo Métodos de Acceso](./img/comandos_terminal/3_segundo_metodo_inicio.png)
<br>
<br>



### 📤 1.3 Subir Archivo

1 - Mostramos el fichero que queremos subir (servidor local) utilizando *``!``* . Luego subimos el fichero con *``put``* (servidor remoto) .

~~~
put fichero_local
~~~

![Subir Fichero](./img/comandos_terminal/4_subir_fichero.png)
<br>
<br>


2 - Comprobamos que se ha subido correctamente el fichero en el servidor remoto .
 
~~~
dir 
~~~

![Comprobar Subir Fichero](./img/comandos_terminal/5_comprobar_subir_fichero.png)
<br>
<br>


### 📊 1.4 Estado de la Sesión *``ftp``*

Mostrar el estado del servicio , usamos el siguiente comando

~~~
status
~~~

![Estado](./img/comandos_terminal/6_ver_estado_ftp.png)
<br>
<br>


### 🔤 1.5 Tipo de Formato

Hay dos tipos de formato en *``ftp``* , estos se utilizan para establecer el modo de transferencia de archivos .

~~~
# Archivos binarios (la mayoría de los casos)
binary

# Archivos de texto plano y para conversión de saltos de línea es necesaria.
ascii
~~~

![Tipo de Formato](./img/comandos_terminal/7_formato_ftp.png)
<br>
<br>


### 📥 1.6 Descargar Archivo

1 - Utilizamos el comando *``get``* para descargar un fichero  con *``ftp``* .

~~~
get fichero_remoto
~~~

![Descargar Fichero](./img/comandos_terminal/8_descarga_fichero.png)
<br>
<br>


2 - Comprobamos si el fichero remoto se descargo correctamente .

~~~
!dir
~~~

![Comprobar Descargar Fichero](./img/comandos_terminal/8_comprobar_descarga_fichero.png)
<br>
<br>


 
### 📚 2. Bibliografía

>   - **Página Oficial Microsof :** https://learn.microsoft.com/es-es/windows-server/administration/windows-commands/ftp
>   - **Página ***IONOS*** :** https://www.ionos.es/digitalguide/servidores/know-how/comandos-ftp/
>   - **dpgsmr.wordpress.com :** https://dpgsmr.wordpress.com/wp-content/uploads/2017/10/comandos-ftp.pdf