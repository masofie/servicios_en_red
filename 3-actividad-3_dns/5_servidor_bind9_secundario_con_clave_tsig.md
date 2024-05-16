# Servidor ***BIND*** Secundario con **Clave TSIG**

## Indice 

## Definición

Una ***Clave TSIG (Transaction Signature)*** es una forma de autenticación utilizada en servidores **DNS** como **BIND9** para asegurarse de que las comunicaciones entre un servidor maestro y un servidor esclavo son seguras y auténticas. Esta clave se utiliza para firmar digitalmente las transferencias de zona entre servidores **DNS** y garantizar la integridad de los datos transmitidos. Las ***Claves TSIG*** se configuran con un algoritmo de hash y una clave compartida entre los servidores para asegurar la autenticidad de las comunicaciones.