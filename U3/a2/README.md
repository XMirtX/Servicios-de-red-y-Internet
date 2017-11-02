# Servidor DNS Linux Bind9

## Preparacion:

  * Server:
    * S.O: Ubuntu 17.10
    * IP Fija :

    ![image](img/Seleccion_012.png)

    * DNS:

    ![image](img/Seleccion_013.png)

    > Colocamos el IP del servidor para que se autoapunte. IP_Servidor o 127.0.0.1

  * Cliente:

    * S.O: Ubuntu 17.10
    * IP Fija:

    ![image](img/Seleccion_013.png)

    * DNS

    ![image](img/Seleccion_016.png)

## Instalación Bind9

* DNS Cache:

  * Abrimos un terminal, instalamos Bind9 ```apt - get install Bind9```

  ![image](img/Seleccion_001.png)

  * Vamos al archivo "**named.conf.options**"" paea configurar los renviadores.

  ![image](img/Seleccion_002.png)

  * La descomentamos.

  ![image](img/Seleccion_003.png)

  * Vamos al Cliente y comprobamos que resuelve los nombres por nuestro Servidor.

  ![image](img/Seleccion_004.png)

  ![image](img/Seleccion_005.png)

* DNS Master:

  * Vamos al archivo "**named.conf.local**" aqui configuramos las "**Zona Busqueda Directa y Inversa**".

  ![image](img/Seleccion_007.png)

  * Ahora creamos el archivo de Zona de Busqueda Directa.

  ![image](img/Seleccion_008.png)

  * Creamos el archivo Zona de Busqueda Inversa.

  ![image](img/Seleccion_009.png)

## Comprobación

  * Server

    * Ejecutamos el comando "**Nslookup**" para comprobar que resuelve los nombres.

    ![image](img/Seleccion_010.png)

    ![image](img/Seleccion_011.png)

  * Cliente

    * Abrimos terminal y ejecutamos "**Nslookup**" desde el cliente para comprobar que resulve bien lo nombres.

    ![image](img/Seleccion_014,png)

    ![image](img/Seleccion_015.png)
