# 🧱 Servidor *``BIND``* Secundario (Respaldo)
<br>

**📑 Indice** 
- [🧱 Servidor *``BIND``* Secundario (Respaldo)](#-servidor-bind-secundario-respaldo)
  - [ℹ️ Definición](#ℹ️-definición)
  - [🛠️ 1. Cambios en el Servidor Primario](#️-1-cambios-en-el-servidor-primario)
    - [🔐 1.2 Cláusula *``allow-transfer``*](#-12-cláusula-allow-transfer)
    - [🗂️ 1.2 Modificaciones en las Zonas](#️-12-modificaciones-en-las-zonas)
  - [🧩 2. Configuración en Servidor Secundario](#-2-configuración-en-servidor-secundario)
    - [📍 2.1 Definición de Zonas](#-21-definición-de-zonas)
    - [🔄 2.2 Visualizar Transferencia de Zonas](#-22-visualizar-transferencia-de-zonas)
    - [📝 2.3  Ajustes de Formato de Texto](#-23--ajustes-de-formato-de-texto)
  - [🧪 3. Comprobaciones en Cliente Windows](#-3-comprobaciones-en-cliente-windows)
    - [📛 3.1 Verificación del Registro **`ns`**](#-31-verificación-del-registro-ns)
    - [🌐 3.1 Prueba de Resolución de Dominio](#-31-prueba-de-resolución-de-dominio)
    - [🚨 3.2 Simulación de Caída del Servidor Primario](#-32-simulación-de-caída-del-servidor-primario)

<br>

## ℹ️ Definición 
<br>

Un servidor *``BIND``* secundario es un servidor que mantiene una copia exacta de la información almacenada en un servidor primario. Su función principal es actuar como respaldo en caso de que el servidor principal falle o se vuelva inaccesible. ⚠️

Además de servir como respaldo, los servidores secundarios :

- 📶 Distribuyen la carga de trabajo.

- 🌍 Mejoran la disponibilidad del servicio.

- 🛡️ Aseguran redundancia en caso de fallos.

- ⚡ Mejoran la velocidad de acceso si están geográficamente distribuidos.

<br>

## 🛠️ 1. Cambios en el Servidor Primario
<br>

### 🔐 1.2 Cláusula *``allow-transfer``* 

1 - Se añade la cláusula allow-transfer en los archivos de definición de zonas y reenviadores. Debe quedar así:

~~~
allow-transfer { 192.168.18.109; };
forwardes{};
~~~


![Fichero de Definiir Zonas](./img/bind9_secundario/1_primario_allow_transfer.png)
<br>
<br>



2 - En el fichero de named.conf.options añadimos esa misma clausula 

~~~
allow-transfer { 192.168.18.109; };
~~~

![Fichero de Reenviadores](./img/bind9_secundario/2_primario_reenviaores.png)
<br>
<br>



###  🗂️ 1.2 Modificaciones en las Zonas

Se modifica el archivo de la zona directa e inversa, añadiendo el registro NS para definir el servidor secundario . ✅ Con esto, el servidor primario reconoce al servidor secundario como autorizado para recibir transferencias de zona .

~~~
;Zona Directa
ns2 IN  NS  ns2.masofie.eus.
ns2 IN  A   192.168.18.109
~~~

![Cambios en Zonas 1](./img/bind9_secundario/3_primario_definicion_zona_directa.png)
<br>
<br>


~~~
; Zona Inversa
109 IN  PTR ns2.masofie.eus.
~~~

![Cambios en Zonas 1](./img/bind9_secundario/4_primario_definicion_zona_invenso.png)
<br>
<br>



## 🧩 2. Configuración en Servidor Secundario
<br>

### 📍 2.1 Definición de Zonas 

Aquí definimos las zonas directa e inversa, especificando que el servidor actuará como esclavo *``(slave)``* del servidor primario *``(master)``* : 

![Definición de zonas](./img/bind9_secundario/5_secundario_definicion_zonas.png)
<br>
<br>



### 🔄 2.2 Visualizar Transferencia de Zonas

Reiniciamos BIND en el servidor secundario . Luego accedemos a la ruta de las zonas (por defecto en *``/var/cache/bind``*) y comprobamos que los archivos se hayan transferido correctamente ✅.

~~~
systemctl restart bind9
~~~

![Mostrar Transferencia de Zonas](./img/bind9_secundario/6_secundario_transferencia_zonas1.png)
<br>
<br>


### 📝 2.3  Ajustes de Formato de Texto

1 - 🔧 **Problema :** Al transferirse, las zonas se guardan en formato *``RAW``* , que no es legible fácilmente . Esto genera una copia en formato legible del archivo de zona. 


![Cambio de Formato de Texto](./img/bind9_secundario/7_secundario_texto_ilegible.png)
<br>
<br>



2 - 🛠️ **Solución :** Convertir al formato texto plano con el siguiente comando :

~~~
named-compilezone -f raw -F text -o db.masofie.eus masofie.eus db.masofie.eus
~~~


![Corregido Formato de Texto](./img/bind9_secundario/8_secundario_texto_ilegible_arreglado.png)
<br>
<br>



3 - Comprobamos el fichero de zona para ver si acambiado el formato y este mas legible para nosotros 

![Fichero Legible](./img/bind9_secundario/9_secundario_texto_ilegible_bien.png)
<br>
<br>



## 🧪 3. Comprobaciones en Cliente Windows
<br>

### 📛 3.1 Verificación del Registro **`ns`**

Comprobamos el registro *``NS``* desde el cliente, preguntando al servidor primario . Esto ✅ verifica que aparezca el servidor *``ns2.masofie.eus.``* .

~~~
nslookup -type=NS masofie.eus 192.168.18.107
~~~


![Registro NS](./img/bind9_secundario/10_w10_registro_ns.png)
<br>
<br>




### 🌐 3.1 Prueba de Resolución de Dominio

Consultamos el dominio a ambos servidores para comprobar que responden correctamente , ✅ Si ambos responden, ¡la sincronización funciona!

~~~
nslookup masofie.eus 192.168.18.107

nslookup masofie.eus 192.168.18.109
~~~


![Comprobar Dominio](./img/bind9_secundario/11_w10_mostrar_dominio.png)
<br>
<br>



### 🚨 3.2 Simulación de Caída del Servidor Primario

1 - 🔌 Apagamos el servidor primario y realizamos una consulta *``DNS``* desde el cliente . ✅ Si el secundario responde correctamente, ¡la configuración está bien hecha!


![Caida de Dominio Principal](./img/bind9_secundario/12_w10_priemario_apagado.png)
<br>
<br>



2 - Luego le preguntamos al servidor secundario , en este caso esta funcionando correctamente 

![Caida de Dominio Principal 2](./img/bind9_secundario/13_w10_priemario_apagado2.png)
<br>
<br>


**💡 Consejo Final**

>Tener un servidor *``BIND``* secundario no es solo una copia del primario...
>¡es tu red de seguridad! 🛡️
>
> 📌 Recomendaciones :
>
> - 🔁 Verifica regularmente las transferencias de zona.
>
> - 🔐 Usa *``allow-transfer``* solo con IPs confiables.
>
> - 🧪 Haz simulaciones de caída para confirmar que todo sigue funcionando.
>
> - 📝 Lleva un registro de cambios y monitorea el sistema.
>
> - ⚙️ Un sistema DNS robusto no es el que nunca falla , sino el que sigue funcionando cuando algo falla.