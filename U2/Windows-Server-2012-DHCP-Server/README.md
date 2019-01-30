# Instalación y Configuración de DHCP en Windows 2012 server

* Instalación del servicio DHCP

 Vamos al asistente de agregar roles y características y elegimos la primera opción

 ![image](img/dh1.png)

 Elegimos el servidor previamente creado

 ![image](img/dh2.png)

 Agregamos el servicio DHCP

 ![image](img/dh3.png)

 En la siguiente pantalla le damos a siguiente.

 ![image](img/dh5.png)

 En la siguiente pantalla nos dice que tengamos una ip estatica , esto ya esta confugurado previamente en el servidor

 ![image](img/dh6.png)

 Le damos a instalar

 ![image](img/dh7.png)

 Una vez instalado cerramos la ventana.

 ![image](img/dh8.png)

 * Configuración servicio DHCP

 Empezamos la Configuración para crear los administradores y usuarios del "DHCP"

 ![image](img/dh9.png)

 Le damos permiso al usuario administrador credenciales para administar el servicio.

 ![image](img/dh10.png)

 En esta pantalla nos dice el resumen de la configuración.

 ![image](img/dh11.png)

 ### Creación de Ambitos

 Vamos a administrador del servicio, herramientas, DHCP

 ![image](img/dh12.png)

 Ahora estamos en el panel de control de DHCP vamos a nuestro servidor, IPv4 y agregamos el Ambito

 ![image](img/dh13.png)

 Nos saldra un asistente le damos a siguiente

 ![image](img/dh14.png)

 Aqui le agregamos el rango de direccion de IP

 ![image](img/dh15.png)

 Le ponemos Nombre al Ambito

 ![image](img/dh16.png)

 Agregamos exclusiones de IP

 ![image](img/dh17.png)

 Aqui le ponemos el tiempo que una maquina va estar con la Ip asignada.

 ![image](img/dh19.png)

 Ahora vamos a configurar el Ambito

 ![image](img/dh20.png)

 Le ponemos la puerta de enlace

 ![image](img/dh21.png)

 Aqui agregamos el dominio creamos previamente

 ![image](img/dh22.png)

 Servidores WINS lo dejamos

 ![image](img/dh23.png)

 Le damos activar el Ambito y finalizar

  ![image](img/dh24.png)

  ![image](img/dh25.png)

  ### Reserva

  Vamos a crear una reserva para nuestra maquina Windows 10, vamos al panel de control, IPv4, ambito, reserva; le damos que sea compatible con DHCP:

  ![image](img/dh26.png)

  ### Comprobación

  Vamos a la maquina de Windows 10 cliente y renovamos la ip con el comando "ipconfig /renew" y vemos como nos da la ip reservada

  ![image](img/dh27.png)
