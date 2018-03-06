# Instalación y Configuración del Servicio VoIP en Linux

## 1. Máquinas a utilizar:

* Servidor con SO `Asterisk` para la correcta implementación del servicio.

* Cliente con SO Ubuntu, en el cual instalaremos un cliente SIP llamado `Ekiga`.

## 2. Instalación del servidor Asterisk

* Para descargar el servidor Asterisk tenemos que acceder a la web https://www.asterisk.org/downloads, desde donde descargaremos la última versión a ser posible.

![image](images/img/Selección_018.png)

* Una vez realizada la propia instalación del SO, nos toca montar el servidor y su configuración. Para ello, lo primero que nos piden es que nos registremos en su web para así tener acceso a la instalación del servicio de VoIP.

![image](images/img/img1.png)

* Una vez tengamos la constraseña y nos validemos, ya empezaremos la instalación del servicio, empezando por definir un usuario.

![image](images/img/img2.png)

* Ahora nos piden si queremos usar una IP pública o una privada, así que como nosotros lo queremos para una red interna, pillamos la opción de IP privada.

![image](images/img/img3.png)

* Le indicamos que sea privada.

![image](images/img/img4.png)

* Definimos el nombre y dominio.

![image](images/img/img5.png)

* Los puertos los dejamos como están.

![image](images/img/img6.png)

* Elegimos el adaptador de red.

![image](images/img/img7.png)

* Elegimos la extensión para los números, en nuestro caso va a ser la más simple.

![image](images/img/img9.png)

* Seleccionamos la zona horaria.

![image](images/img/img10.png)

* Definimos la extensión del operador.

![image](images/img/img11.png)

* Definimos los datos de registro.

![image](images/img/img12.png)

* Ya estaría instalado.

![image](images/img/img14.png)

* Este es el panel de control del servidor.

![image](images/img/img15.png)

## 3. Cliente SIP softphone Ekiga

* Instalamos el paquete de la instalación de Ekiga.

![image](images/Selección_001.png)

* Una vez instalado, accedemos al cliente de forma gráfica.

![image](images/Selección_002.png)

* Nada más entrar nos sale la pantalla de configuración del programa.

![image](images/Selección_003.png)

* Introducimos nombre de usuario.

![image](images/Selección_004.png)

* Ahora nos avisa de que las dos siguientes páginas son para darnos de alta en el servicio propio de ekiga, pero como vamos a utilizar Asterisk no lo necesitamos.

![image](images/Selección_005.png)

![image](images/Selección_006.png)

![image](images/Selección_007.png)

* Aquí determinamos el tipo de conexión que queremos, en este caso, red de área local.

![image](images/Selección_008.png)

* Esta parte la dejamos tal y como está.

![image](images/Selección_009.png)

* Esta parte tampoco nos interesa tocarla ya que no pretendemos hacer transmisiones de videos.

![image](images/Selección_010.png)

* Aquí por último nos aparece un resumen de la configuración.

![image](images/Selección_011.png)

* Una vez realizada la configuración, entramos a `Editar` y luego elegimos la opción `cuentas`.

![image](images/Selección_012.png)

* Elegimos la opción `Añadir una cuenta SIP`

![image](images/Selección_013.png)

* Añadimos los datos del usuario que con anterioridad creamos en Asterisk.

![image](images/Selección_016.png)

* Y ya tenemos la cuenta preparada para ser utilizada.

![image](images/Selección_017.png)
