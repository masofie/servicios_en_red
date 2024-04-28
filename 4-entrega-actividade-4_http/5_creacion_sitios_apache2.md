# Creación de Sitios Virtuales en Apache2 en Debian
<br><br>

## INDICE 
- [Creación de Sitios Virtuales en Apache2 en Debian](#creación-de-sitios-virtuales-en-apache2-en-debian)
  - [INDICE](#indice)
  - [Configación de Sitios Globales :](#configación-de-sitios-globales-)
  - [Configuración del sitio por defecto :](#configuración-del-sitio-por-defecto-)
  - [Configuración de un nuevo sitio virtual :](#configuración-de-un-nuevo-sitio-virtual-)



## Configación de Sitios Globales :

1 – Instala el servidor web Apache y PHP . <br>
2 – Modifica el archivo apropiado para que el archivo a mostrar por defecto de un directorio sea ***index.php*** , ***index.asp*** y luego ***index.html*** . <br>
3 – Habilita los módulos usertrack y userdir <br>

## Configuración del sitio por defecto :

1 – Configura el sitio por defecto que muestre **‘Este es el fichero del sitio por defecto’** .<br>
2 – Debe atender peticiones a mayores , en el puerto ***9999*** . <br>


## Configuración de un nuevo sitio virtual :

1 – Crea un sitio virtual por nombre ciudad.gal que atienda en los puertos ***80*** y ***9999*** .<br>
2 – Modifica los archivos de logs para que sean específicos . <br>
3 – Cuando se produzca un error 404 se mostrara el mensaje **“No se ha podido encontrar ningún resultado en la búsqueda”** , que este alojado en el directorio ***/var/www/ciudad.gal/error_404.html*** . <br>
4 – Cuando se produzca un error 403 se mostrará un mensaje de ***“PROHIBIDO”*** . <br>
5 – Los archivos de este sitio a mostrar por defecto serán ***index.html*** e ***index.php*** . <br>
6 – No se permitirá que se listen los contenidos de las carpetas , al no encontrar ninguno de los documentos por defecto .
7 – Crea un ‘alias’ que se redirija la **‘url’** ***./docs  ./documentos*** , que se debe crear previamente . <br>
8 – Crea una carpeta denominada carpetacuidad . El acceso a esta carpeta debe ser restringida para los usuarios ***‘user1’*** y ***‘user2’*** con contraseña ***‘abc123.’*** mediante Autenticación Basic . <br>
9 – Crea un archivo denominado index.html en la carpeta ciudad.gal que tenga en el contenido **‘’Bienvenido al Sitio Virtual ciudad.gal ’’** . <br>
10 – Habilita en el anterior sitio web un acceso por SSL con la creación de la ***claves RSA***. Debe redirigir las peticiones del puerto 80 al puerto ***443*** . <br>