# Creación de Subdominios

## Indice 

## Definición 

Un ***subdominio virtual*** es un término utilizado en el ámbito de las tecnologías de internet para referirse a un dominio dentro de un dominio principal. Por ejemplo, si tenemos el dominio principal **"ejemplo.com"**, un subdominio virtual podría ser **"subdominio.ejemplo.com"**. Los subdominios virtuales se utilizan comúnmente para organizar y estructurar un sitio web.

Por otro lado, un ***delegado** es una persona o entidad designada para actuar en nombre de otra persona o entidad. En el contexto de los servidores de nombres de dominio **(DNS)**, un delegado es una entidad autorizada para administrar ciertos aspectos de un dominio. Por ejemplo, un delegado puede ser responsable de la gestión de los registros **DNS** de un subdominio virtual.

En resumen, la diferencia entre un ***subdominio virtual*** y un ***delegado*** radica en que un subdominio virtual es un dominio dentro de un dominio principal, mientras que un delegado es una entidad designada para administrar ciertos aspectos de un dominio, como los registros **DNS**.


## 1. Creación Dominio Virtual 

### 1.1 Definir Registro 

Para crear un dominio virtual se usa la clausula **'$ORIGIN'** para definir el dominio , se hace de la siguiente manera , sin tener en cuenta el registo ***NS*** **(NO)**

![Añadiendo Registro A](./img/sub_dominios/1_subdominios_registros.png)