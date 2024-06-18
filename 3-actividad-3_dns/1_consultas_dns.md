# Resulución de Nombres con Comandos ***nslookup*** , ***dig*** , ***hosts***

## Indice 


## 1. Comandos DNS 

### 1.2 Comandos ***nslookup***

Con el comando ***nslookup*** podemos podemos ver la ip y el nombre con el siguiente comando . Con la ip ya podmeos ver el nombre como en el siguiente ejemplo 

~~~
nslookup 8.8.8.8
~~~
~~~
nslookup dns.google
~~~


![Comando Nslokup - Nombre e ip](./img/consulta_nombre/1_nslookup_ip_nombre.png)

También podemos ver los registros de recursos . Se puede ver de con el los servidores ***NS*** de google de la sigueinte manera 

~~~
nslookup -type=NS dns.google
~~~

![Comando Nslokup - Registro NS](./img/consulta_nombre/2_nslookup_ns.png)


### 1.2 Comandos ***dig***

El comando dig podemos añadir la ip y el dominio al mismo tiempo , se peude hacer de la siguiente manera 

~~~
dig @8.8.8.8 dns.google
~~~

![Comando dig - Nombre e ip](./img/consulta_nombre/3_dig_nombre_ip.png)