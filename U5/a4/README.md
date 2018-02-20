# Servicio SMTP Windows 2012 Server

### 1. Instalar Servicio SMTP en Windows 2012 Server

Vamos al panel de agregar roles y caracteristicas y buscamos  el Servicio SMTP.

  ![img](img/img1.png)

Seleccionamos Servidor SMTP  

  ![img](img/img2.png)

Pulsamos Instalar

  ![img](img/img3.png)

### 2. Configuración de servicio SMTP a través del administrador de aplicaciones (IIS) 6.0. Realizar las siguientes acciones de configuración:

  * Establecer como IP todas las asignadas , Limitar el número de conexiones a 50 y Habilitar el registro en formato W3C, diario y en una carpeta determinada.

    ![img](img/img5.png)

  * Configurar envío de mensajes dentro de nuestra red local: Aceptar la conexión al servidor y la retransmisión de mensajes a todos los equipos menos los que aparecen en la lista (incluir una IP cualquiera en la lista
  para impedir su acceso y retransmisión)

    ![img](img/img7.png)

  * Establecer autenticación anónima

    ![img](img/img6.png)

  * Comprobar la existencia del dominio AD predeterminado. Crea un dominio de tipo alias para disponer de cuentas en otro dominio.

    ![img](img/img9.png)

  * Comprueba carpetas de correo creados en
  ``C:\Inetpub\mailroot.``

    ![img](img/img8.png)


### 3. Autenticación Anonima.

  * En el cliente Windows:

  * Configurar el cliente de correo Live mail agregando dos cuentas de correo. cualesquiera (usuarios AD -dominio- y no AD). Se deberá especificar: usuario / buzón, contraseña,  servidor SMTP.

      ![img](img/img12.png)

  > Usamos el correo de Opera.

  * Iniciamos sesion.

      ![img](img/img13.png)

  * Colocamos nuestro servidor.

      ![img](img/img14.png)

  * Y ya tenemos un usuario listo para comprobar que funciona nuestro servicio SMTP.

      ![img](img/img15.png)


  > Creamos otro usuario y comprobamos el envio de mensajes.


  * Enviar varios correos desde / hacia las diferentes cuentas y comprobar envío (real o ficticio) y carpetas mailroot. Las carpetas existentes en mailroot alojan mensajes en cola (Queue), mensajes para destinatarios desconocidos (Badmail) y mensajes entregados (Drop).

    ![img](img/img16.png)

  * Entramos en las carpeta Drop para ver los mensajes que se enviaron.

    ![img](img/img17.png)


### Autenticación Basica.

  * Nueva configuración de servicio SMTP a través del administrador de aplicaciones (IIS) 6.0. Establecer autenticación básica de Windows. Probar diferentes configuraciones de dominio predeterminado, cifrado TLS, etc.

    ![img](img/img4.png)


  * Quitamos la autenticación anonima y seleccionamos la autenticación basica.

    ![img](img/img18.png)

  > Esto cogera los ususarios que tenemos en nuestro Directorio Activo.


  * Activamos cifrado TLS en nuestro servidor.

    ![img](img/img21.png)

  > Usara un certificado que ya tengamos en nuestro servidor.

  * Creamos las cuentas de mail para nuestro usuarios de Directorio Activo.

    * Abraham:

      ![img](img/img23.png)

    * FelipeC

      ![img](img/img24.png)


  *  Enviar varios correos desde / hacia las diferentes cuentas y comprobar envío y carpetas mailroot. En este caso sólo tendrán acceso al servidor SMTP cuentas del dominio y correspondientes a usuarios de AD.

  * Enviamos un mensaje desde Abraham a FelipeC

    ![img](img/img25.png)

  * Un error de seguridad por el certificado ya que no esta registrado.

    ![img](img/img26.png)

  * Vamos a las carpeta donde se almacenan los correos.

    ![img](img/img27.png)

  * Y vamos que llego correctamente al destinatario.

    ![img](img/img28.png)
