# Instalación del DHCP FailOver

  * Preparación de la maquina "**DHCP FailOver**".
    * Sistema Windows 2012 Server
    * IP estatica:
    ![image](img/Selección_002.png)

    * Unión al dominio
    ![image](img/Selección_003.png)

  * Instalación del servicio **DHCP**.

    * Vamos al apartado agregar roles y carateristicas y elgimos el dhcp.
    ![image](img/Selección_004.png)

    * Le damos siguiente y sleccionamos la "**Instalación basada en roles**".
    ![image](img/Selección_005.png)

    * Seleccionamos el servidor.
    ![image](img/Selección_006.png)

    * Agregamos el servicio "**DHCP**"
    ![image](img/Selección_007.png)

    * Y le damos a instalar
    ![image](img/Selección_008.png)

    * Una vez terminada la instalación vamos a la configuración.
    ![image](img/Selección_010.png)

    * Le damos a siguiente.
    ![image](img/Selección_011.png)

    * Y autorizamos el servidor.

    * Una vez terminado tendria que quedar asi.
    ![image](img/Selección_012.png)

  * Servicio DHCP FailOver

    * Vamos a nuestro servidor **DHCP Principal** creamos un ambito nuevo.
    ![image](img/dhcpf.png)

    * Le damos a siguiente y elegimos el tiempo de concesión por IP.
    ![image](img/dhcpf1.png)

    * Siguimos y elegimos el dominio.
    ![image](img/dhcpf3.png)

    * Colocamos la puerta de enlace.
    ![image](img/dchp2.png)

    * Y finalizamos.
    ![image](img/dhcpf4.png)

    * Ahora vamos a añadir nuestro servidor "**DHCP FailOver**" para que replique el ambito que acabamos de crear."Vamos al apartado "**Elegimos el servidor**"
    ![image](img/dhcpf5.png)

    * Modificamos los parametros.
    ![image](img/dhcpf6.png)

    * Y le damos a finalizar.
    ![image](img/dhcpf7.png)

    * Vamos al servidor FailOver y comprobamos que el ambito se replico.
  ![image](img/Selección_013.png)

    * Activamos el ambito en el servidor espejo.
    ![image](img/Selección_016.png)

---

# Comprobación en equicos clientes.

  * Bajamos el ambito en el servidor principal y comprobamos si funciona el "**DHCP FailOver**"

  * Vamos a un equipo cliente y con el comando ``ipconfig /release`` dejamos libre la tarjeta de red.

  ![image](img/Selección_017.png)

  * Ahora con el comando ``ipconfig /renew`` vamos a pedir una IP.

  ![image](img/Selección_018.png)

  > Vemos que se le asigno una IP del servidor DHCPFailOver.
