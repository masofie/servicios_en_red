# 🗂️ Registros Básicos en BIND

**📑 Indice** 
- [🗂️ Registros Básicos en BIND](#️-registros-básicos-en-bind)
  - [📌 1. Tipos de Registros DNS](#-1-tipos-de-registros-dns)
    - [🏠 1.1 Registro de recursos ***A (Address)***](#-11-registro-de-recursos-a-address)
    - [🌐 1.2 Registro de recursos ***AAAA***](#-12-registro-de-recursos-aaaa)
    - [🔗 1.3 Registro de recursos ***CNAME (Canonical Name)***](#-13-registro-de-recursos-cname-canonical-name)
    - [📬 1.4 Registro de recursos ***MX (Mail Exchange)***](#-14-registro-de-recursos-mx-mail-exchange)
    - [🔙 1.5 Registro de recursos ***PTR (Pointer)***](#-15-registro-de-recursos-ptr-pointer)
    - [🖥️ 1.6 Registro de recursos ***NS (Name Server)***](#️-16-registro-de-recursos-ns-name-server)
    - [📝 1.7 Registro de recursos ***TXT (Texto)***](#-17-registro-de-recursos-txt-texto)
    - [⚙️ 1.8. Registro de recursos ***SRV (Service)***](#️-18-registro-de-recursos-srv-service)

<br>

## 📌 1. Tipos de Registros DNS

### 🏠 1.1 Registro de recursos ***A (Address)***

Se utiliza para asociar un nombre de dominio con una dirección IP IPv4.

~~~
equipo1 IN A 192.168.18.50
~~~

### 🌐 1.2 Registro de recursos ***AAAA***

Similar al registro A, pero utilizado para asociar un nombre de dominio con una dirección IP IPv6.

~~~
equipo1 IN A  00:00:00:00:00:00
~~~

### 🔗 1.3 Registro de recursos ***CNAME (Canonical Name)***

Se utiliza para crear alias o apuntadores de un nombre de dominio a otro nombre de dominio.

~~~
equ1 IN CNAME equipo1
~~~

###  📬 1.4 Registro de recursos ***MX (Mail Exchange)***

Se usa para especificar los servidores de correo responsables de recibir los correos electrónicos de un dominio.

~~~
equipo1 IN  MX  1   equipo1.nombre_dominio.
~~~

### 🔙 1.5 Registro de recursos ***PTR (Pointer)***

Se utiliza para asociar una dirección IP con un nombre de dominio.

~~~
50  IN  PTR equipo1.nombre_dominio. 
~~~

### 🖥️ 1.6 Registro de recursos ***NS (Name Server)***

Se utiliza para especificar los servidores de nombres autoritativos para un dominio.

~~~
equipo1 IN  NS  equipo1.nombre_dominio. 
~~~

### 📝 1.7 Registro de recursos ***TXT (Texto)***

Se utiliza para almacenar texto de cualquier tipo en un registro de recursos DNS.

~~~
equipo1 IN  TXT "Esto es un equipo de prueba"
~~~

### ⚙️ 1.8. Registro de recursos ***SRV (Service)***

Se utiliza para especificar la ubicación de servicios dentro de un dominio.

~~~
equipo1 IN  SRV 1 1 5060  equipo1.nombre_dominio. 
~~~

<br>

**🔍 Estos son algunos de los tipos de registros más comunes que encontrarás en un servidor DNS.**
<br>
**⚠️ Existen otros tipos menos frecuentes, que se usan según las necesidades específicas de cada dominio.**


**💡 Consejo Final**

>Para una configuración DNS efectiva, es importante conocer bien cada tipo de registro y cómo se adapta a las necesidades de tu dominio. ¡Explora, practica y mantén tu servidor siempre optimizado! 🚀🌐
