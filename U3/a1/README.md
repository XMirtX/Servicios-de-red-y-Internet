# Instalación y Configuración DNS Windows 2012 Server

### Preparación:

  * Servidor

    * Windows 2012 Server
    * IP Fija:

    ![image](img/img0001.png)


  * Cliente

    * Windows 10 Cliente
    * IP Fija:
    
    ![image](img/img00002.png)

### Instalación de DNS:

  * Vamos al panel de agregar roles y carateristicas y buscamos el Servicio DNS.

    ![image](img/img0.png)

    > En mi caso ya lo tengo instalado, por que el sevidor esta como controlador de dominio y automaticamente se instala.

### Configuración de DNS

  * Creación de Zona de busqueda Directa

    * Vamos al panel de Administador de Servicio, Herramientas DNS y elegimos crear una nueva zona.

      ![image](img/img02.png)

    * Le damos a siguiente.

      ![image](img/img03.png)

    * Elegimos zona principal.

      ![image](img/img04.png)

    * Elegimos la segunda opción.

      ![image](img/img05.png)

    * Le damos un nombre.

      ![image](img/img06.png)

    * Dejamos esta opción por defecto y finalizamos.

      ![image](img/img07.png)

      ![image](img/img08.png)

  * Creacion de Zona de busqueda Inversa

    * En el panel de configuración del DNS, vamos a "**Zonas de Busqueda Inversa y agregamos una nueva zona**".
    ![image](img/img001.png)

    *  Le damos a siguiente.

      ![image](img/img002.png)

    * Seleccionamos zona principal.

      ![image](img/img03.png)

    * Elegimos la segunda opción.

      ![image](img/img004..png)

    * Zona Inversa IPv4 .

      ![image](img/img005.png)

    * Colocamos nuestra IP de Red.

      ![image](img/img007.png)

    * Dejamos esta opción por defecto y finalizamos.

      ![image](img/img008.png)

      ![image](img/img009.png)

### Configurar Reenviadores

  * Abrimos el panel DNS y vamos al servidor y editamos el archivo reenviadores.

    ![image](img/img09.png)

  * Modificamos el archivo y dejamos el DNS de google.

    ![image](img/img010.png)

  * Tenemos ahora el servidor DNS en modo cache, vamos a un cliente y hacemos un nslookup para ver si resuelve los nombres de dominio, por nuestro servidor.

    ![image](img/img00003.png)

  > Resuelve el nombre de dominio y sale por nuestro servidor.

### Configuración de DNS Maestro

  * Creamos un "**CNAME**"(alias) llamado "Server" que apunta a la ip del servidor.

    ![image](img/img000002.png)

    ![image](img/img00001.png)

  * Un "**Host A**" nuevo llamado "**Printer**"(Impresora).

    ![image](img/img1.png)

  * Un nuevo "**Host A**" llamado correo.

    ![image](img/img6.png)

  * Y ahora creamos un "**MX**"(Intercambiador de correo), apuntando las "**Host A**"" denominado "**correo**"

    ![image](img/img3.png)

  * Vamos a crear una subzona (dominio nuevo).

    ![image](img/img7.png)

  * Le damos un nombre al nuevo dominio.

    ![image](img/img8.png)

  *  Ahora creamos "**CNAME**" (Alias) apuntando al servidor llamado "**FTP**".

    ![image](img/img11.png)

    ![image](img/img10.png)

  * Un nuevo "**Host A**" (Impresora).

    ![image](img/img12.png)

### Comprobación

  * Servidor:

    * Abrimos un terminal y ejecutamos comandos con nslookup.

      ![image](img/img13.png)

      ![image](img/img14.png)

  * Cliente

    * Abrimos el terminal y ejecutamos nslookup.

      ![image](img/img15.png)

      ![image](img/img16.png)
