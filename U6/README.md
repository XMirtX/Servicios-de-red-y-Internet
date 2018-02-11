# Servidor de correo Linux

## Instalación del servicio SMTP

* Iniciamos la instalación del servicio `Postfix` mediante el comando:

```
apt-get install Postfix
```

* En madio de la instalación nos saldrá esta especie de asistente.

![image](images/000214.png)

* Escoger instalación como Sitio de Internet

![image](images/000215.png)

* Creamos dominio miempresa.edu

![image](images/000216.png)

* Una vez terminada la instalación, comprobamos servicio (y puerto) SMTP activo y a la escucha con `netstat– utap`

![image](images/000217.png)

* Realizar  una  prueba  de  envío  de  mensaje  entre  dos  usuarios  del  sistema  mediante
telnet.

![image](images/000219.png)

* Comprobamos que ahora ya nos han asignado un puerto para la conexión.

![image](images/000220.png)

* Completamos el mensaje y comprobamos que está dentro de la carpeta de `/var/mail/` del usuario.

![image](images/000221.png)

![image](images/000222.png)

* Instalamos un cliente de correo electrónico en un cliente.

![image](images/000225.png)

* Crear  dos  nuevas  entradas  en  /etc/hosts:  smtp.miempresa.edu  y  pop.miempresa.edu
asociadas a la IP del servidor.

![image](images/000224.png)

* Crear al menos dos cuentas asociadas a usuarios existentes en el servidor y asociadas al
dominio creado en Postfix.

![image](images/000226.png)

![image](images/000227.png)

![image](images/000228.png)

![image](images/000229.png)

![image](images/000230.png)

* Enviamos un mensaje de un usuario a otro.

![image](images/000231.png)

* Comprobamos que el mensaje se encuentra en el directorio del usuario.

![image](images/000232.png)

## Instalación del servicio IMAP

* Instalar servicio IMAP con:

```console

apt-get install dovecot-imapd

```

![image](images/000233.png)

* Comprobar servicio (y puerto) IMAP activo y a la escucha con `netstat –utap`

![image](images/000234.png)

* Instalar aplicación correo web SquirrelMail.

![image](images/000236.png)

* Carpeta de configuración en /etc/squirrelmail

![image](images/000237.png)

* Acceder desde una máquina cliente, vía HTTP, al gestor de correo SquirrelMail instalado.

![images](images/000242.png)

* Enviar  y  recibir  correos  entre  las  dos  cuentas  creadas  desde  el  cliente  y  utilizando  el gestor de correo web SquirrelMail

  * Maquina Cliente.

  * Accedemos con el ususario suso previamente creado en el servidor.

    ![images](images/000243.png)

  * Enviamos un correo al usuario alu2302.

    ![images](images/000247.png)

  * Accedemos al segundo ususario **alu2302** y comprobamos que tenemos el mensaje del ususario suso.

    ![images](images/000248.png)

  * Le mandamos un correo al ususrio suso y comprobamos que lo recibe.

    ![images](images/000250.png)

    ![images](images/000251.png)

* Comprobar que los mensajes enviados desde ambas cuentas se siguen encontrando en
los respectivos buzones de los usuarios en /var/mail.

![images](images/000249.png)

![images](images/000252.png)

### Instalar servicio POP3:

* Instalar servicio POP3 con apt-get install dovecot-pop3d

![images](images/000253.png)

* Comprobar servicio (y puerto) POP3 activo y a la escucha con netstat –utap.

![images](images/000254.png)

* Configurar  MUA  (gestor  de  correo  cliente  Evolution  o  similar)  en  máquina  cliente  para que  acceda  a  la  recepción  de  correo  a  través  del  protocolo  POP3  instalado  en  el servidor.

* Usaremos el Cliente Evolution , creamos el primer usuario.

  * alu2302
    ![images](images/000255.png)

  * Elegimos el tipo de servidor de recepción, la ip del servidor y el ususario.

    ![images](images/000256.png)

  * Elegimos el tipo de servidor de envio, la ip del servidor y el usuario.

    ![images](images/000257.png)

    ![images](images/000258.png)

  * Seguimos los mismos paso con el siguiente ususario.

    ![images](images/000259.png)
* Enviar y  recibir  correos  entre  las  dos  cuentas  creadas  desde  el  cliente  y  utilizando  el gestor de correo del cliente

  * Enviamos un correo a suso con el cliente alu2302.

    ![images](images/000260.png)

  * Enviamos un correo de respuesta a alu2302 con el usuario suso.

    ![images](images/000262.png)

  > Dejamos el resultados de envio en la parte de comprobación de /var/mail.

* Comprobar  que  los  correos  enviados  y  recibidos  han  desaparecido  (han  sido  extraídos
por POP3) de los buzones respectivos de los usuarios en /var
/mail.

  * Primer mensaje alu2302

    ![images](images/000261.png)

  * Segundo mensaje suso

    ![images](images/000262.png)
