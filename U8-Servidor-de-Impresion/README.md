# Servidor de Impresión en Windows
## 1. Impresora compartida

* Rol impresión

  * Vamos al servidor, instalar rol/función de servidor de impresión. Incluir impresión por Internet.

    ![image](img/img1.png)

  * Agregamos la característica.

    ![image](img/img2.png)

  *  Ya esta seleccionada.

    ![image](img/img3.png)

  * Seleccionamos "**Servidor de Impresion y Impresión en Internet**".

    ![image](img/img4.png)

  * Le damos a instalar.

    ![image](img/img5.png)

  * Una vez terminado el proceso le damos a cerrar.

    ![image](img/img6.png)

## 1.2 Instalar impresora PDF

 * Vamos a conectar e instalar localmente una impresora al servidor Windows Server, de modo que estén disponibles para ser accedidas por los clientes del dominio.

 * En nuestro caso, dado que es posible de que no tengan una impresora física en casa y no es de mucho interés forzar la instalación de una impresora que no se tiene, vamos a instalar un programa que simule una impresora de PDF, como "**PDFCreator**".

 *  Descargar PDFCreator (URL recomendada www.pdfforge.org/pdfcreator/download) e instalar.

    * En modo experto y le damos a siguiente.

      ![image](img/img7.png)

    * Le damos el nombre a la impresora.

      ![image](img/img8.png)

    * La Ruta donde se van almacenar la Impresion.

      ![image](img/img9.png)

    * Dejamos por defecto.

      ![image](img/img10.png)

    * Le damos a siguiente.

      ![image](img/img11.png)

    * Instalamos

      ![image](img/img12.png)

    > En la configuración automatica cambiamos la ruta que da por defecto el programa.

  *  En PDFCreator, configurar en perfiles -> Guardar -> Automático. Ahí configuramos carpeta destino.

      ![image](img/img13.png)

    > NOTA: PDFCreator puede requerir NET FrameWork v4.

## 1.3 Probar la impresora en local

  * Para crear un archivo PDF no hará falta que cambies la aplicación que estés usando, simplemente ve a la opción de "imprimir" y selecciona "Impresora PDF", en segundos tendrás creado tu archivo PDF.

    ![image](img/img14.png)

 * Puedes probar la nueva impresora abriendo el Bloc de notas y creando un fichero luego selecciona imprimir. Cuando finalice el proceso se abrirá un fichero PDF con el resultado de la impresión.

    ![image](img/img15.png)


## 1.4 Compartir por red

 * Vamos al servidor -> herramientas -> Administración de impresión -> Servidor de Impresion -> Impresoras -> PDFCreator.

 * Botón derecho -> Propiedades -> Compartir
    Como nombre del recurso compartido utilizar PDFnombrealumnoXX.

    ![image](img/img16.png)

* La siguiente imagen muestra los recursos compartidos en el servidor incluido la impresora:

    ![image](img/img17.png)

* Vamos al cliente:

    * Buscar recursos de red del servidor. Si tarda en aparecer ponemos \\ip-del-servidor en la barra de navegación.

      ![image](img/img18.png)

    Seleccionar impresora -> botón derecho -> conectar.

      ![image](img/img19.png)

    * Ponemos usuario/clave del Windows Server.
    Ya tenemos la impresora remota configurada en el cliente.

    * Probar la impresora remota.

      ![image](img/img20.png)

    * Carpeta donde se almacena las impresión

      ![image](img/img21.png)

## 2. Acceso Web

 * Realizaremos una configuración para habilitar el acceso web a las impresoras del dominio.

## 2.1 Instalar característica impresión WEB

  * Vamos al servidor.
  * Nos aseguramos de tener instalado e servicio "Impresión de Internet".

  >Esto ya lo hicimos en primer paso de la practica.

## 2.1 Configurar impresión WEB

  *  Vamos al cliente.
  *  Abrimos un navegador Web.
  *  Ponemos URL http://<ip-del-servidor>/printers (o http://<nombre-del-servidor>/printers) para que aparezca en nuestro navegador un entorno que permite gestionar las impresoras de dicho equipo, previa autenticación como uno de los usuarios del habilitados para dicho fin (por ejemplo el "Administrador").

  ![image](img/img22.png)

  * Pincha en la opción propiedades y se muestra la siguiente pantalla:

  ![image](img/img23.png)


  *  Agregamos la impresora en el cliente utilizando la URL, como se muestra en la siguiente pantalla:

  ![image](img/img24.png)

## 2.3 Comprobar desde el navegador

* Vamos a realizar seguidamente una prueba sencilla en tu impresora de red:

* A través del navegador pausa todos los trabajos en la impresora.

  ![image](img/img25.png)

*  Envía a imprimir en tu impresora compartida un documento del Bloc de notas. La siguiente pantalla muestra que la impresora esta en pausa y con el trabajo en cola de impresión.

  ![image](img/img28.png)

*  Finalmente pulsa en reanudar el trabajo para que tu documento se convierta a PDF. Comprobar que se puede imprimir desde un cliente Windows.

  ![image](img/img29.png)

  ![image](img/img30.png)
