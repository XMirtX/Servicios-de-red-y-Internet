### Preparación de la maquinas

* Servidor: Dos tarjetas de red una con acceso exterior y una interna.

![image](img/dhl5.png)

> Configuramos la interna para que reparta IP a nuestro dominio.

![image](img/dhl6.png)

* Cliente: Con una sola tarjeta que la pondremos en modo dhcp

![image](img/dhl06.png)

![image](img/dhl21.png)

### Instalación de servicio DHCP en ubuntu

Abrimos un terminal y intrducimos el comando:

>sudo apt-get install isc-dhcp-server

![image](img/dhl0.png)

### Creación de Rangos de Cesión

En el terminal vamos a la ruta "/etc/dhcp/dhcp.conf" y modificamod el archivo

![image](img/dhl4.png)

Leventamos el servicio y hacemos na pequeña comprobación para ver si funciona.

![image](img/dhl08.png)

Vamos a la maquina cliente y ejecutamos el comando ifconfig para ver si esta repartiendo bien el rango establecido.

![image](img/dhl15.png)

Incluimos dentro de nuestro rango, el router y dominio.

![image](img/dhl11.png)

Hacemos una reverva para nuestra maquina cliente.

![image](img/dhl16.png)

Y unas configuracion globales.

> Configuramos el tiempo de la reverva de la cesión.

![image](img/dhl17.png)

Ya que levantamos el servicio antes , para que carguen las nuevas opciones hacemos un reset del servidor.

![image](img/dhl14.png)

Comprobamos que el servicio esta activo

![image](img/dhl18.png)

### Comprobación en maquina cliente

Vamos al terminal introducimos el comando "ifconfig" y vemos si reparte la ip reservada.

![image](img/dhl19.png)

Tambien podemos comprobarlo mediante entorno grafico.

![image](img/dhl20.png)
