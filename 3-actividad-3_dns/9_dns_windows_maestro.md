# 🪟🧭 DNS Maestro en Windows Server 
<br>

**📑 Indice** 
- [🪟🧭 DNS Maestro en Windows Server](#-dns-maestro-en-windows-server)
  - [🛠️ 1. Instalación de *``DNS``*](#️-1-instalación-de-dns)
    - [➕ 1.1 Agregar Rol *``DNS``*](#-11-agregar-rol-dns)
  - [⚙️ 2. Configuración de *``DNS``*](#️-2-configuración-de-dns)
    - [🔁 2.1 Reenviadores](#-21-reenviadores)
    - [📂 2.2 Zona de Búsqueda Directa](#-22-zona-de-búsqueda-directa)
    - [2.3 Zona de Búsqueda Inversa](#23-zona-de-búsqueda-inversa)
    - [🧩 2.4 Añadir Registros Directa/Inversa](#-24-añadir-registros-directainversa)
  - [🔎 3. Comprobaciones con *``nslookup``*](#-3-comprobaciones-con-nslookup)
    - [💻 3.1 Cliente Windows](#-31-cliente-windows)

<br>

## 🛠️ 1. Instalación de *``DNS``*
<br>

### ➕ 1.1 Agregar Rol *``DNS``*

Añadimos el rol para instalar el servidor dns en nuestro sistema operativo 

![Agregar Rol DNS](./img/ws_maestro/1_ws_maestro_roles.png)
<br>
<br>



## ⚙️ 2. Configuración de *``DNS``*
<br>

### 🔁 2.1 Reenviadores

Definimos los reenviadores que vamos ha utilizar para cuando el servidor no encuentre donde buscar le pidan la peticiones a ellos

![Reenviadores](./img/ws_maestro/1_ws_maestro_reenviadres.png)
<br>
<br>



###  📂 2.2 Zona de Búsqueda Directa

1 - Una en la siguiente pestaña damos clic derecho en *``zona directa``* y creamos una nueva zona , de la siguiente manera 

![Nueva Busqueda Directa](./img/ws_maestro/3_ws_maestro_zona_directa1.png)
<br>
<br>



2 - Seleccionamos el tipo de zona que deseamos y como es un servidor maestro seleccionamos *``zona principal``*

![Tipo Busqueda Directa](./img/ws_maestro/4_ws_maestro_zona_directa2.png)
<br>
<br>



3 - Le damos un nombre alusivo a nuestra zona

![Nombre Busqueda Directa](./img/ws_maestro/5_ws_maestro_zona_directa3.png)
<br>
<br>



4 - Aquí esta la zona directa creada correctamente 

![Creada Busqueda Directa](./img/ws_maestro/6_ws_maestro_zona_directa4.png)
<br>
<br>



###  2.3 Zona de Búsqueda Inversa

1 - Hacemos clic derecho ay creamos zona de busqueda inversa 

![Nueva Busqueda Inversa](./img/ws_maestro/7_ws_maestro_zona_inversa1.png)
<br>
<br>



2 - Le damos el nombre a nustra zona , como es una zona inversa y el nombre depende de la red que tengas al momento de crearla

![Nombre Busqueda Inversa](./img/ws_maestro/8_ws_maestro_zona_inversa2.png)
<br>
<br>



3 - La zona inversa se ha creado correctamente 

![Creada Busqueda Inversa](./img/ws_maestro/9_ws_maestro_zona_inversa3.png)
<br>
<br>



### 🧩 2.4 Añadir Registros Directa/Inversa

Añadimos un par de registros a nustra zona para hacer luegos las comprobaciones en el cliente

![Añadir Registros Directa/Iversa](./img/ws_maestro/10_ws_maestro_registros.png)
<br>
<br>




## 🔎 3. Comprobaciones con *``nslookup``*
<br>

### 💻 3.1 Cliente Windows
Accedemos al cliente y hacemos las siguientes comprobaciones , esto para ver si funciona correctamente 

![Compracioneas en Cliente Windows](./img/ws_maestro/11_ws_maestro_comprobaciones.png)
<br>
<br>

**💡 Consejo Final**

>La correcta configuración del *``DNS``* Maestro en Windows Server es esencial para garantizar la resolución rápida y precisa de nombres en una red interna 🧠⚡.
>
> - 📌 Verifica que las zonas estén correctamente creadas *``(directa e inversa)``* y que los registros correspondan al *``nombre``* y *``IP``* esperados.
> - 🔁 Los reenviadores permiten una navegación externa más eficiente.
> - 🧪 Utiliza nslookup para comprobar la resolución y detectar errores tempranos.
> - 🔐 ¡Y no olvides los permisos y el cortafuegos si usas máquinas virtuales o múltiples redes!