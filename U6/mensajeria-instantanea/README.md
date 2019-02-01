# Instalación y Configuración de un Servidor de Mensajería Instantánea

### 1. Descarga e instalación del servidor de mensajería instantánea OpenFire para Windows

![image](images/Selección_033.png)

* Curiosamente nos pide encarecidamente la instalación de `Java`, así que lo instalamos para el correcto funcionamiento del servidor.

![image](images/Selección_034.png)

* Ahora ejecutamos de nuevo el instalador y seguimos el proceso.

![image](images/Selección_036.png)

![image](images/Selección_037.png)

![image](images/Selección_038.png)

![image](images/Selección_039.png)

![image](images/Selección_040.png)

![image](images/Selección_042.png)

![image](images/Selección_044.png)

### 2. Crear una base de datos en blanco en MySqQL a través de phpMyAdmin

* Entramos como administradores a `phpmyadmin` y creamos una base de datos vacía a la que llamaremos en nuestro caso `correo`

![image](images/Selección_047.png)

* Creamos un usuario llamado `user_correo` y le damos todos los privilegios para manipular la base de datos correo.

![image](images/Selección_048.png)

### 3. Ejecutar el script de instalación de Openfire desde un navegador web del servidor, mediante la url `http://127.0.0.1:9090` y seguir la instalación

* Seleccionamos el idioma Español.

![image](images/Selección_045.png)

* Ponemos el nombre y dominio del servidor.

![image](images/Selección_049.png)

* Elegimos conexión Estándard

![image](images/Selección_050.png)

* Sustituimos la máscara por defecto en la casilla `URL de la base de datos` colocando los datos correspondientes y ponemos nombre de usuario y contraseña.

![image](images/Selección_055.png)

* Configuramos la cuenta del administrador del servidor.

![image](images/Selección_057.png)

* Se ha terminado el proceso, ahora toca loguearse.

![image](images/Selección_058.png)

* La primera vez no nos deja, pero después de un reinicio todo funciona.

![image](images/Selección_059.png)

![image](images/Selección_060.png)

### 4. Una vez instalado el servidor OpenFire, vamos a descargar e instalar un cliente de Mensajería

* Descargamos e instalamos el cliente de mensajería Spark en el servidor y cliente.

![image](images/Selección_061.png)

![image](images/Selección_062.png)

![image](images/Selección_063.png)

![image](images/Selección_064.png)

![image](images/Selección_065.png)

![image](images/Selección_066.png)

![image](images/Selección_068.png)

### 5. Creamos dos usuarios en OpenFire para establecer una conversación

![image](images/Selección_070.png)

![image](images/Selección_071.png)

![image](images/Selección_072.png)

### 6. Iniciamos la conversación a través de Spark

* Antes que nada, tenemos que acceder a la pestaña `avanzado` y marcar estas dos opciones.

![image](images/Selección_074.png)

* Y ya nos podemos loguear tranquilamente.

![image](images/Selección_073.png)

![image](images/Selección_075.png)

* Ahora con el usuario "mamel" en el cliente

![image](images/Selección_076.png)

* Ahora desde el servidor con "suso" le mandamos una solicitud de amistad a "mamel", que aceptará desde el cliente

![image](images/Selección_077.png)

![image](images/Selección_078.png)

* Agregado el contacto, ya pueden enviarse mensajes entre ellos.

![image](images/Selección_079.png)

![image](images/Selección_080.png)

* Ahora vamos a crear una sala de conferencias, para ello volvemos a OpenFire y hacemos click en la pestaña `Conferencias`

![image](images/Selección_081.png)

* Rellenamos los datos que sean necesarios y la creamos.

![image](images/Selección_082.png)

![image](images/Selección_083.png)

* Ahora desde los usuarios en el cliente Spark buscamos la conferencia creada y nos agregamos a ella.

![image](images/Selección_085.png)

![image](images/Selección_086.png)

* Le toca a "mamel"

![image](images/Selección_087.png)

![image](images/Selección_088.png)

* Y claro, desde aquí también se pueden mensajear.

![image](images/Selección_089.png)

* También se pueden tranferir ficheros entre usuarios desde Spark, haciendo click en el elemento señalado.

![image](images/Selección_090.png)

![image](images/Selección_091.png)

* Desde el terminal de "mamel" se ve como recibe la petición de envío de fichero, la cual debe aceptar para recibirlo.

![image](images/Selección_092.png)

![image](images/Selección_093.png)

* También se pueden enviar capturas de pantallas entre ambos usuarios ...

![image](images/Selección_094.png)

![image](images/Selección_095.png)

* Y como antes, el otro usuario debe aceptar la petición.

![image](images/Selección_096.png)

![image](images/Selección_097.png)
