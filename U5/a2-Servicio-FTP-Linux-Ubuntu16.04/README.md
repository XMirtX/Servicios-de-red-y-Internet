# Instalación y Configuración del Servicio FTP en Linux

### 1. Crear dos usuarios en el sistema, con diferentes privilegios y niveles de acceso al filesystem.

* Abrimos el terminal y creamos los dos usuarios.

  ![img](img/img5l.png)

* Vamos al panel de usuarios y otorgamos privilegios.

  * Abraham => Administrador.

    ![img](img/img14l.png)

  * Carlos => Estándar

    ![img](img/img15l.png)

### 2. Instalar Servicio SSH en el servidor Linux.

  * Abrimos el terminal ejecutamos el comando para instalar **SSH**

    ``sudo apt install ssh``

    ![img](img/img16l.png)

#### 2.1 Configurar el archivo "sshd_config" para ejecutar programas.

  * Vamos a la ruta del archivo ``cd /etc/ssh``

  ![img](img/img17l.png)

  * Tenemos que modificar la linea X11Forwarding por defecto viene activado.

  ![img](img/img18l.png)

#### 2.2 Comprobar, desde una máquina cliente, acceso de los usuarios mediante ssh.

  * Conexion con Carlos.

  ![img](img/img19l.png)
  ![img](img/img20l.png)

### 3. Instalar el paquete proftpd (Servicio FTP).

  * Vamos al terminal ejecutamos el comandp para instalar.

  ``sudo apt install proftpd``

  ![img](img/img2l.png)

  * Elegimos idependiente

  ![img](img/img1l.png)

  * Abrimos el terminal y comprobamos que podemos acceder.

  ![img](img/img4l.png)

#### 3.1 Editar el fichero de configuración /etc/proftpd/proftpd.conf buscando información en Internet.

  > Modificamos el archivos y incluimos a los usuarios para dar privilegios en el servicio ftp.

  * Abraham puede acceder a raiz **/** y carlos solo puede acceder a su home **/homr/carlos**

    ![img](img/img10l.png)

### 4. Conectar al servicio ftp gestionado por proftpd tanto desde el servidor como desde un cliente.

#### 4.1 Servidor protocolo ftp.

  * Conexión Usuario Abraham.

    ![img](img/img12l.png)

    > Vemos que tenemos acceso a la carpeta raiz.

  * Conexión Usuario Carlos.

    ![img](img/img11l.png)

    > Intentamos acceder a raiz pero aunque el comando funcione solo mostrara su /home/.

  * Subimos y descargamos archivos.

    ![img](img/img13l.png)

#### 4.2 Cliente protocolo sftp.

  * Conexión Usuario Abraham.

    ![img](img/img24l.png)

  * Subimos y descargamos archivos.

    ![img](img/img25l.png)

  * Conexión Usuario Carlos y Subimos , descargamos archivos.

    ![img](img/img26l.png)
