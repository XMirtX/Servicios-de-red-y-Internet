# Práctica Servidor Web Apache - Linux - Pasos e indicaciones

## Objetivos

  * Dominio principal: miempresa.com (o similar)

  * Alias página principal: www.miempresa.com

  * Sitio seguro (https): pagos.miempresa.com (o miempresa.com/pagos)

  * Carpetas privadas protegidas: empleados.miempresa.com (o miempresa.com/empleados)

  * Instalación PHP, MySQL, phpMyAdmin

  * Gestión bases de datos: phpmyadmin.miempresa.com (o miempresa.com/phpmyadmin)

  * Instalación y configuración plataforma Drupal, Joomla, Moodle, Gallery, osCommerce, etc. en página principal

## Preparación de la maquina

  *  Configurar MV Ubuntu o similar en adaptador Puente (acceso a Internet)

      ![image](img/img0.png)

  * Configuración de Red

      ![image](img/img0.1.png)

## Instalación Apache:

  * Instalar Apache: `sudo apt-get install apache2`

    ![image](img/img1.png)

  * Comprobar carpeta raíz sitio web: `/var/www`

    ![image](img/img2.png)

  * Comprobar acceso a localhost //It works!

    ![image](img/img3.png)

  * Añadir línea www.miempresa.com asociada a IP servidor en `/etc/hosts` o servidor DNS.

    ![image](img/img4.png)

  * Comprobar acceso con la ip asociada.

    ![image](img/img6.png)

  * Reiniciar apache: `sudo /etc/init.d/apache2` restart ó reload.

    ![image](img/img5.png)

  * Error + Access logs: /var/log/apache2


## Instalación PHP

  * Instalar php: sudo apt-get install php5

    ![image](img/img7.png)

  * Comprobar acceso a index.php -<?php phpinfo(); ?>-

    ![image](img/img8.png)

### Crear Hosts Virtuales en Apache.

  * Ejemplo:
    ```
    <VirtualHost *:80>

    ServerAdmin webmaster@miempresa.com

    ServerName empleados.miempresa.com //Añadir también a hosts o serviodor DNS

    DocumentRoot /var/www/empleados

    <Directory /var/www/empleados> // No es necesario para VirtualHost sencillos

    Opciones típicas...

    </Directory>

    </VirtualHost>
    ```

  * Crear la carpeta de los Hosts Virtuales.

    ![image](img/img24.png)

  * Asociar carpetas con sitios web (ej: empleados.miempresa.com --> /var/www/empleados) y establecer configuración (`/etc/apache2/sites-available/000-default.conf`)

    ![image](img/img28.png)

  * Añade en /etc/hosts la web de empleados.

    ![image](img/img22.png)

    > Ya que no tenemos un DNS propio usamos este archivo para que resuelva los nombres de dominio.

  * Reinicia el servidcio de apache para cargar la nueva configuración.

  `sudo systemctl restart apache2.service`

  * Comprobación

    ![image](img/img36.png)


###  Configurar sitio web seguro pagos:

  * Al instalar Apache, se instala también SSL.
  *  Generar certificado autofirmado:

  *  § openssl genrsa -des3 -out server.key 1024.

  ![image](img/img11.png)


  > Nos pide una contraseña poner una contraseña para el certificado.


  *  § openssl rsa -in server.key -out server.pem.

  ![image](img/img12.png)

  *  § openssl req -new -key server.key -out server.csr.

  ![image](img/img13.png)


  > Datos de empresa.


  *  § openssl x509 -req -days 360 -in server.csr -signkey server.key -out server.crt.

  ![image](img/img14.png)


  > Una vez terminados los certificados copiarlos a la carpeta de apache2


  ![image](img/img17.png)


  * Modificar /etc/apache2/sites-available/000-default.conf.

    ![image](img/img16.png)

  *  Habilitar módulo SSL apache: sudo a2enmod ssl

    ![image](img/img15.png)

  * Reinicia el servicio de apache.

    `sudo systemctl restart apache2.service`

  * Comprobacion

    ![image](img/img18.png)

###  Acceso a carpetas privadas

  *  Autenticación mediante .htaccess:

    ![image](img/img26.png)

  *  Estructura: empleados.miemepresa.com (acceso a todos los empleados pero no anónimos) y subcarpetas personales de empleados (dos o tres, con acceso limitado al usuario).

  * Carpetas de empleados.

    ![image](img/img25.png)

  > Dentro de cada carpeta de empleados tenemos que tener el .htaccess.

  * Crea la carpeta para alamcenar las claves de los empleados.

    ![image](img/img38.png)

    ![image](img/img37.png)

  * Comprobación de el acceso con empleados.

    * Juan

    ![image](img/img30.png)

    ![image](img/img39.png)

    * Pepe

    ![image](img/img29.png)

    ![image](img/img40.png)

### Instalación de MySQL

  * Instalamos el servicio `MySQL` mediante el siguiente comando:

    ```console

    sudo apt-get install mysql-server

    ```

    ![image](img/000110.png)

  * Comprobamos la versión instalada (útil para prevenir posibles problemas de compatibilidad con otros programas futuros)

    ![image](img/000111.png)

  * Instalamos además el soporte para PHP de MySQL con el siguiente comando:

    ```console

    sudo apt-get install php-mysql

    ```
    ![image](img/000112.png)

### Instalación de phpMyAdmin

  * Descargamos la última versión de phpMyAdmin que se encuentre en la pag oficial `www.phpmyadmin.net`, y lo descargamos en formato tar.gz

    ![image](img/000113.png)

  * Acto seguido, lo movemos hasta `/var/www`

    ![image](img/000114.png)

  * Y le cambiamos el nombre a uno más simple como `phpMyAdmin`

    ![image](img/000115.png)

  * Una vez hecho esto, y previamente habiendo reiniciado el servicio de apache, accedemos mediante la web a `phpMyAdmin`

    ![image](img/000116.png)

    ![image](img/000117.png)

  * Ahora creamos la base de datos cms.

    ![image](img/000118.png)

  * Y también al usuario `cmuser`, que será el que controle la base de datos `cms`

    ![image](img/000119.png)

    ![image](img/000120.png)

### Instalación y configuración de cms Drupal

  * Descargamos la versión 7.56 de Drupal.

    ![image](img/000122.png)

  * Descomprimimos el contenido de la del archivo comprimido y (en nuestro caso) lo metemos dentro de `/var/www/html`

    ![image](img/000124.png)

  * Y le cambiamos el nombre a algo más simple.

    ![image](img/000123.png)

    ![image](img/000125.png)

  * También tenemos que modificar el fichero de configuración del virtual host en `/etc/apache2/sites-enabled`, incluyendo la línea que define al directorio `principal`

    ![image](img/000126.png)

  * Despues de reiniciar el servicio de apache de nuevo, comprobamos el acceso al directorio `/principal`, en donde se encuentra `Drupal`

    ![image](img/000128.png)

  * Configuramos el idioma para que se instale en español. Para ello tenemos que ir a la web de Drupal e instalar el paquete del lenguaje español.

    ![image](img/000129.png)

    ![image](img/000130.png)

    ![image](img/000131.png)

  * Configuramos la base de datos

    ![image](img/000133.png)

  * El programa realiza algunas instalaciónes como la carga del idioma seleccionado.

    ![image](img/000134.png)

  * Ahora configuramos los datos del sitio web, como el usuario que accederá o el nombre del sitio.

    ![image](img/000135.png)

  * Y completamos la instalación.

    ![image](img/000136.png)

  * Una vez entramos podemos configurar algunos módulos tales como `GTranslate`, que se encarga de buscar traducciones automáticas para el sitio que creemos. Para ello descargamos el paquete desde la web de `Drupal` y luego lo instalamos.

    ![image](img/000137.png)

    ![image](img/000138.png)

  * También podemos aplicar otros temas para cambiar la apariencia de la web a nuestro antojo. En este caso vamos a activar el tema `Garland 7.56` previamente descargado.

    ![image](img/000139.png)

    ![image](img/000140.png)

  * Por último también podemos realizar artículos y temas para nuestra web, para llenarla de contenido.

    ![image](img/000142.png)

    ![image](img/000143.png)
