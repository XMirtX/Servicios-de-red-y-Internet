# Instalación y Configuración de un Servidor Web Avanzado

## Carpetas Seguras

* Crea una nueva zona de búsqueda directa en los servicios DNS asociado al dominio
miEmpresa.

  * Vamos al servidor, Herramintas -> DNS -> Crear una nuva zona directa.

  * Lo dejamos en Zona principal.

    ![image](img/img0.png)

  * La segunda opcion

    ![image](img/img1.png)

  * Le damos un nomnre a la nueva zona.

    ![image](img/img3.png)

  * Dejamos la opcion recomendada.

    ![image](img/img4.png)

  * Le damos a finalizar.

    ![image](img/img5.png)

  * Comprobacion y creamos dentro de nuestra nueva zona , "**CNAME, HOST A**"

    ![image](img/img6.png)

    ![image](img/img7.png)

* Crea también una carpeta miEmpresa en C:\ y una subcarpeta ‘principal’.

    ![image](img/img2.png)

* Crea  un  nuevo  sitio  web  denominado miEmpresa en  IIS  asociado  a  la  subcarpeta  anterior  y  con  
acceso a través de la dirección www.miEmpresa.com , Actualiza DNS adecuadamente.

  * Vamos a Herramientas -> Servidor ISS -> Sitios -> Nuevo sitio WEB.

    ![image](img/img8.png)

* Crea  un  nuevo  sitio web (denominado ‘pagos’) como subdominio de miEmpresa (pagos.miEmpresa.com) y configura este último para ser accedido de forma segura, vía ‘https’.

  ![image](img/img16.png)

    * Crea el sitio web, asociado a una carpeta (miEmpresa\pagos) y con la configuración adecuada en IIS y en los servicios DNS.

      ![image](img/img11.png)

    * Vamos al DNS y creamos Subdominio llamado "**Pagos**"

      ![image](img/img9.png)

    * Dentro de la carpeta C:\miEmpresa\pagos, colocamos el Index.html.

      ![image](img/img10.png)

      ![image](img/img11.png)

    * Comprueba el acceso (aún vía ‘http’) con un navegador desde el propio servidor y desde un cliente W7.

      ![image](img/img12.png)

    * Configuración  A:  
      Configura  el  nuevo  sitio  para  que se pueda acceder (sólo) como sitio web seguro (https) con un Certificado Autofirmado.

    * Creamos el Certificado Autofirmado.

      ![image](img/img13.png)

      > Lo dejamos en Personal.

      ![image](img/img14.png)

    * Creamos el sitio web con el certificado autofirmado.

      ![image](img/img15.png)

    * Comprobamos desde el servidor.

      ![image](img/img17.png)

      > Tenemos un error, no somos una empresa certificadora.

    * Configuración B:
    Crearemos un nuevo sitio seguro (tienda.miempresa.com) con la generación de un  Certificado  Digital a  través  de  la  aplicación  OpenSSL.  Para  empezar,  realizaremos  la  solicitud  de un nuevo certificado de servidor para nuestro sitio seguro (crear fichero certreq.txt).

      * Creamos una carpeta en C:\miempresa\tienda donde vamos a colocar nuestra pagina web.

        ![image](img/img19.png)

      * Creamos en el DNS un subdominio llamado tienda.

        ![image](img/img18.png)

      * Creamos una solicitud de certificado.

        ![image](img/img20.png)

      * Rellenamos los campos a solicitar para el cerificado.

        ![image](img/img21.png)

      * Elegimos una longitud de 2048 bits.

        ![image](img/img22.png)

      * Le expecificamos la ruta donde va a estar la solicitud.

        ![image](img/img23.png)

    * Descargar e instalar OpenSSL para Windows.

      * Instalamos OpenSSL.

        ![image](img/img24.png)

    * A través de OpenSSl genera un nuevo certificado de servidor.

      * Generar una clave privada de  la  entidad  certificadora.

        ![image](img/img25.png)

      * Crear  un  certificado  digital  de  la  entidad  certificadora  y,  finalmente.

        ![image](img/img26.png)

      * Crear un certificado digital de nuestra web.

        ![image](img/img27.png)

    * Importar  el  nuevo  certificado  de  servidor  creado  para  completar  la  petición  pendiente  en  nuestro sitio seguro "tienda".

      ![image](img/img28.png)

    * Requerir  que  nuestros  sitio  seguros  sólo  se  pueda  acceder  mediante  una  conexión  segura  y  reiniciar los sitios web.

    * Creamos el sitio web tienda que solo se podra acceder solo por https, con el certificado creado anteriormente.

      ![image](img/img29.png)

    * Finalmente, acceder mediante http y mediante https a los sitios seguros desde el propio servidor y desde un cliente W7, aceptando los posibles problemas con la entidad certificadora.

      * Pagos certificado autofirmado.

        ![image](img/img34.png)

      * Pagos sin certificado

        ![image](img/img34.png)

      * Tienda

        ![image](img/img35.png)


## Carpetas Privadas.

* Vamos  a  crear  un  nuevo  sitio  web  (empleados.miEmpresa.com) destinado a almacenar información privada de los empleados, con las siguientes características:

    * Necesitamos  crear  una  carpeta  empleados  (dentro  de  miEmpresa)  y,  dentro  de  esta,  tres  o  cuatro subcarpetas personales con nombres de empleados y una, denominada común, a la que tendrán acceso todos los empleados, pero no otros usuarios sin identificar.

      * Crear la carpeta empleado.

        ![image](img/img36.png)

      * SubCarpetas.

        ![image](img/img37.png)

    * Crearemos  el  nuevo  sitio  web,  como  subdominio  de  nuestro  dominio  principal,  asociado  a  la  carpeta genérica empleados.

      * Creamos el subdominio llamado empleados.

        ![image](img/img39.png)

      * Creamos el nuevo sitio web para empleados.

        ![image](img/img38.png)

    * Colocar un fichero index.html diferente en cada una de las carpetas creadas, con el objetivo de poder comprobar el acceso desde un  navegador.

      ![image](img/img40.png)

      * Comprobamos.

        ![image](img/img41.png)
        ![image](img/img42.png)
        ![image](img/img43.png)
        ![image](img/img44.png)
        ![image](img/img45.png)
        ![image](img/img47.png)
        ![image](img/img48.png)

    * Para el sitio web creado y para cada una de sus carpetas, deshabilitamos el acceso anónimo.

      ![image](img/img49.png)

    * Agregar función de Autenticación Básica a nuestro Servicio de IIS a través de la Administración
    del Servidor.

      ![image](img/img50.png)

    * En   Active   Directory,   crearemos   un   usuario   para   cada   empleado   (tantos   como   carpetas   personales) y un grupo Empleados que los incluya a todos.

      * Ususarios
        ![image](img/img51.png)
      * Grupo
        ![image](img/img52.png)

        ![image](img/img53.png)

    * Desactivamos, para la carpeta empleados, los permisos heredables a través de las opciones avanzadas en la ficha de seguridad.

      ![image](img/img54.png)

    * Añadimos grupo de Administradores con Control Total y grupo Empleados con Lectura y Ejecución+ Mostrar Carpeta+Leer.

      ![image](img/img61.png)

      ![image](img/img62.png)

    * Realizamos   el   mismo   procedimiento   para   cada   una   de   las   carpetas   personales   de   los empleados, colocando como usuarios autorizados el Grupo de Administradores (Control Total) y el empleado propietario de cada carpeta (con los permisos que creas convenientes).

      * Ususarios

      ![image](img/img56.png)

      ![image](img/img57.png)

      ![image](img/img58.png)

      ![image](img/img59.png)

      ![image](img/img60.png)


  * Realizamos   el   mismo   procedimiento   para   la   carpeta ‘comun’, colocando como usuarios autorizados  el  Grupo  de  Administradores (Control_Total) y el grupo Empleados (con los permisos que creas convenientes).

      ![image](img/img63.png)

  * Comprobamos  el  acceso,  tanto  desde  el  servidor  como  desde cliente  W7,  a  las  diferentes  carpetas con distintos usuarios.

  * Servidor

    ![image](img/img64.png)
    ![image](img/img47.png)

    ![image](img/img65.png)
    ![image](img/img45.png)

    ![image](img/img66.png)
    ![image](img/img44.png)

    ![image](img/img67.png)
    ![image](img/img43.png)

    ![image](img/img68.png)
    ![image](img/img42.png)


  * Cliente

    ![image](img/img69.png)
    ![image](img/img47.png)

    ![image](img/img70.png)
    ![image](img/img45.png)

    ![image](img/img71.png)
    ![image](img/img44.png)

    ![image](img/img72.png)
    ![image](img/img43.png)

    ![image](img/img73.png)
    ![image](img/img42.png)
