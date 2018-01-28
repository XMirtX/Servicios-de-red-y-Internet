# hMailServer

### 1. Desinstalar Servicio SMTP

* En primer lugar, hay que desinstalar el servicio SMTP de Windows 2012 Server.

  * Pulsamos quitar caracteristica

    ![img](img/img1.png)

  * Y pulsamos quitar para que se desinstale el servicio.

    ![img](img/img4.png)

  * Una vez hecho esto tenemos que reiniciar el equipo.

    ![img](img/img6.png)

### 2. Instalación de hMailServer

* Debes descargar e instalar en el servidor Windows 2012 server el servidor de correo hMailServer.

  ![img](img/img5.png)

* Ejecutamos el archivo descargado para comenzar la instalación.

  ![img](img/img7.png)

* Lo dejamos por defecto.

  ![img](img/img8.png)

* Elegimos la primera opcion.

  ![img](img/img9.png)

* Ingresamos una contraseña.

  ![img](img/img10.png)

* Finalizamos la instalación.

  ![img](img/img11.png)


### 3. Configuración de hMailServer.

* 3.1 Accedemos al panel de hMailServer

  ![img](img/img14.png)

* 3.1 Crea dos dominios denominados srd.edu y asir.edu.

  ![img](img/img16.png)

  > Vamos al apartado de dominios y ahi los creamos.

  ![img](img/img15.png)

  ![img](img/img17.png)

* Ejecuta los diagnósticos para ambos dominios y soluciona el error de backup asignando una carpeta para tal fin. Establece copia de seguridad de los mensajes.

  * Dominio asir.

    ![img](img/img18.png)

  * Dominio srd.

    ![img](img/img19.png)

* Para solucionar el error de backup , vamos al panel de hMailServer, backup y elegimos una ruta para la copias de seguridad, elegimos todas las opciones del backup y guardamos.

  ![img](img/img20.png)

* Solucionar el error de MX , vamos a nuestro DNS, creamos los dominio asir.edu , srd.edu y creamos un alias llamado **mail."dominio.edu"** apuntando al servidor.


  * Dominio asir.edu

    * MX

      ![img](img/img44.png)

  * Dominio srd.edu

    * MX

      ![img](img/img43.png)

> A la hora de ejecutar el diagnósticos de nuevo puede tardar en funcionar.


### Creaciñon de usuarios.

* Crea dos cuentas para dos usuarios ficticios en cada uno de los dos dominios.

  * Abraham:

    ![img](img/img27.png)

  * Suso

    ![img](img/img26.png)


  * Visto desde el panel de hMailServer

    ![img](img/img28.png)

* Investiga y configura las cuentas con diferentes opciones (cuota de disco, auto-reply, forwarding, signature, etc.)

  * Autoreply.

    ![img](img/img53.png)

  * Le mandamos a ususrio Abraham un correo a ver si funciona el Autoreply.

    ![img](img/img56.png)

  * Comprobamos que nos llega el mensaje de abraham automaticamente.

    ![img](img/img54.png)

  * Forwarding

    ![img](img/img57.png)

  * Le mandamos un mesaje abraham para ver si lo recibe robert.

    ![img](img/img58.png)

### Configuración SMTP, POP3, IMAP.

* Realiza todas las opciones de configuración que consideres necesarias y/o convenientes. Consulta para ello los tutoriales cuyos enlaces se proporcionan (opciones de protocolos SMTP, POP e IMAP, rangos de IP, bloqueo de correo entrante, nombre de host, reenvío dominios remotos, blacklists, opciones de logging, etc.)

  * SMTP.

    ![img](img/img29.png)

  * Mensaje de salida y Maxima Conexiones.

    ![img](img/img30.png)

  * POP3

    ![img](img/img31.png)

  * IMAP

    ![img](img/img33.png)

* Instalamos el Cliente Telnet para comprobar cada servidcio.

  ![img](img/img34.png)

* Los puerto de cada servicio.

  ![img](img/img36.png)

* Comprobamos SMTP con el puero 25.

  ![img](img/img35.png)

* Comprobamos POP3 con el puerto 110

  ![img](img/img37.png)

* Comprobamos IMAP con el puerto 143

  ![img](img/img38.png)

### Configuracion de Correo.

* Comprobamos desde el cliente que tenemos acceso a nuestro servidor.

  ![img](img/img45.png)

* Configura en el cliente W7 un cliente de correo como thunderbird o Live Mail (en los ordenadores clientes) para acceder al servidor de correo instalado en Windows 2012.

  * Abraham:

    ![img](img/img39.png)

    ![img](img/img40.png)

  * Suso

    ![img](img/img41.png)

    ![img](img/img42.png)


* Realiza prueba de envío y recepción de correos entre los diferentes usuarios, comprobando, además de envío y recepción correctas, el efecto de las opciones configuradas en las cuentas.

  * Enviamos un correo con Abraham a Suso.

    ![img](img/img46.png)

  * Ahora desde Suso a Abraham

    ![img](img/img47.png)

* Crea una lista de distribución empleados asociada al dominio y añade a los dos usuarios de miempresa.com a ella.

  ![img](img/img48.png)

  ![img](img/img49.png)

> Para esta parte creamos mas usuarios ficticios.

* Realiza prueba de envío y recepción de correos por medio de la lista de distribución.

  * Enviamos un correo a miempresa.

  ![img](img/img50.png)

  * Vemos con le llega a robert que esta dentro de la distrubucion.

  ![img](img/img51.png)
