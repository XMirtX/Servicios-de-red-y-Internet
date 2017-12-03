# Instalación y Configuración de un Servidor Web Avanzado Parte II

* 1.Instalación de PHP, MySQL y PHPMyAdmin

* 1.1 Instalación de PHP

*    Lo primero que debemos hacer es acceder a la web http://windows.php.net/downloads/releases/archives, donde figuran las diferentes versiones de PHP. Nosotros elegimos la versión 5.3.9 con formato msi.

![image](img/Selección_031.png)

  *  Una vez descargado el instalador, comenzamos la instalación guiada.

![image](img/Selección_032.png)

![image](img/Selección_033.png)

  *  Seleccionamos la carpeta en la que se instalará los ficheros del programa.

![image](img/Selección_034.png)

  *  Aquí seleccionamos que sea gestionado por IIS FastCGI, el cual tenemos que instalar desde el administrador del servidor

![image](img/Selección_035.png)

![image](img/Selección_036.png)

![image](img/Selección_037.png)

![image](img/Selección_038.png)

  *  Una vez realizado esto, lo que hacemos es seguir con la instalación

![image](img/Selección_039.png)

![image](img/Selección_040.png)

  *  Una vez instalado PHP, vamos al administrador del servidor IIS para activar el uso de ficheros con extensión .php

![image](img/Selección_041.png)

  *  Aquí vemos que está puesta por defecto, por lo que no debemos preocuparnos por este paso.

![image](img/Selección_042.png)

  *  El último paso para comprobar que la instalación de PHP ha sido realizada satisfactoriamente es colocar un fichero index.php dentro del directorio miempresa con el siguiente contenido en su interior:

> <?php phpinfo(); ?>

![image](img/Selección_043.png)

  *  Por último accedemos a www.miempresa.edu y comprobamos que el fichero de información PHP se ve correctamente.

![image](img/Selección_044.png)

 * Instala el servidor de bases de datos
relacionales MySQL para tus sitios Web gestionados por IIS.

* Descargamos el paquete msi.

![image](img/Selección_045.png)

* Lo ejecutamos y empezamos la instalación de MySql.

![image](img/Selección_046.png)

* Elegimos la opción Developer.

![image](img/Selección_047.png)

* Le damos a ejecutar y esperamos a que termine de descargar e instalar.

![image](img/Selección_048.png)

![image](img/Selección_049.png)

* Una vez finalizado pasamos a la configuración.

![image](img/Selección_050.png)

* Dejamos el puerto y el firewall por defecto.

![image](img/Selección_051.png)

* Le damos una contraseña a el usuario root de MySql.

![image](img/Selección_052.png)

* Le damos un nombre al servicio.

![image](img/Selección_053.png)

* Dejamos estos valores por defecto.

![image](img/Selección_054.png)

* Finalizar.

![image](img/Selección_055.png)

* Comprobamos la conexion con el servidor usando el usuario root.

![image](img/Selección_056.png)

* Aplicamos la configuración dando finalizar.

![image](img/Selección_057.png)

* Instala PHPMyAdmin para tus sitios Web
gestionados   por   IIS.

* Descargamos el phpMyAdmin.

![image](img/Selección_058.png)

* Descomprime el contenido en la carpeta de miempresa.

![image](img/Selección_059.png)

![image](img/Selección_060.png)

* Para   esto   debes   crear   un   nuevo   sitio   web   asociado a phpmyadmin.miEmpresa.com, y actualizar DNS.

* Vamos a nuestro DNS y creamos un nuevo registro llamado "**phpmyadmin.miEmpresa.com**" en el dominio miempresa.edu.

![image](img/Selección_061.png)

* Ahora vamos a crear nuestro sitio web de "**phpmyadmin.miEmpresa.com**", para ello vamos a nuestro servidor ISS y añadimos nuevo sitio web.

![image](img/Selección_061.png)

# Parte II: Instalación de Servidor FTP y CMS Drupal

* Servidor y cliente FTP

  * Instalamos el servidor FTP Filezilla dentro de la máquina con W2012 Server.

![image](img/000063.png)

![image](img/000064.png)

![image](img/000065.png)

  *  Una vez finalizada la instalación, creamos al usuario ftpuser y le damos privilegios totales para controlar la carpeta miempresa.

![image](img/000066.png)

![image](img/000067.png)

  *  Hecho esto, ahora instalamos el cliente FTP de Filezilla en la máquina cliente.

![image](img/000068.png)

  *  Antes de hacer la conexión FTP debemos asegurarnos de que el Firewall no bloqueará la petición, de lo contrario, no se producirá la conexión.

  ![image](img/000069.png)

  ![image](img/000070.png)

  *  Ahora es cuando nos logueamos desde el cliente con el usuario ftpuser.

![image](img/000071.png)

![image](img/000072.png)

  *  Buscamos el instalador de Drupal en la web oficial, en nuestro caso usamos la versión 7.56.

![image](img/000073.png)

  *  Una vez descargado, desde el cliente pasamos por FTP el contenido de Drupal a la carpeta Principal dentro del directorio Miempresa

![image](img/000074.png)

![image](img/000075.png)

## Drupal

  *  Creamos una base de datos en phpmyadmin llamada cms

![image](img/000076.png)

  *  Por algún motivo, la pestaña usuarios de phpmyadmin no funciona, por lo que una opción sería crear al usuario que controlará la base de datos recién creada, cmsuser, desde workbench.

![image](img/000077.png)

![image](img/000078.png)

  *  Una vez hecho esto, le damos permisos totales a cmsuser desde phpmyadmin

![image](img/000079.png)

  *  Al ejecutar ahora el contenido de /principal no nos muestra el contenido de manera deseada. Todo es culpa de un fichero denominado web.config, al que le cambiaremos su extensión por .old.

![image](img/000080.png)

![image](img/000081.png)

![image](img/000082.png)

  *  Una vez solucionado este problema, ya se nos mostrará el instalador web de Drupal correctamente.

![image](img/000083.png)

  *  Lo primero que tenemos que hacer es instalar el paquete del idioma español, por lo que lo buscaremos en la web y lo instalaremos en la ruta que nos indica.

![image](img/000084.png)

![image](img/000085.png)

![image](img/000086.png)

  *  Ahora refrescamos y nos aparecerá el idioma español como opción.

![image](img/000087.png)

  *  Ahora nos enfrentamos a otro "problema", y es que nos dice que no tenemos un fichero de configuración y que tenemos que crearlo manualmente. Es tan sencillo como ir al directorio que nos indica y arreglarlo copiando el fichero default.settings.php y modificar la extenxión.

![image](img/000088.png)

![image](img/000089.png)

  *  Pero ahora nos dirá que hay problemas con los permisos, por lo que una opción rápida (pero no muy eficiente) sera darle permisos a "**todos**".

![image](img/000090.png)

![image](img/000091.png)

![image](img/000092.png)

  *  Segimos con el proceso de instalación.

![image](img/000093.png)

![image](img/000094.png)

![image](img/000095.png)

![image](img/000096.png)

  *  Ya tenemos Drupal instalado, así que ahora lo que haremos serán unas cuantas modificaciones.

![image](img/000098.png)

  *  Lo primero será instalar el modulo de traducción gtranslate, para ello antes debemos activar otro módulo preinstalado llamado Update Manager.

![image](img/000099.png)

![image](img/000100.png)

  *  Descargamos el .zip y lo subimos a Drupal.

![image](img/000101.png)

![image](img/000102.png)

  *  El proceso de instalación de temas también es sencillo, simplemente nos dirigimos a la pestaña apariencia y ahí nos saldrá una opción para subir el tema que deseemos. También es necesario descargar los temas desde internet.

![image](img/000103.png)

![image](img/000104.png)

  *  Para crear una artículos o páginas tenemos que ir a la pestaña contenido, donde elegiremos la opción que necesitemos.

![image](img/000105.png)

![image](img/000106.png)

  *  Una vez creado, le damos a guardar.

![image](img/000107.png)

  *  Para crear un menú, vamos a la pestaña estructura, donde podemos crear nuestro propio menú.

![image](img/000108.png)

![image](img/000109.png)
