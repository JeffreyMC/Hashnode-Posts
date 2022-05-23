## Enviar mensajes de WhatsApp desde Python

En esta ocasión les traigo una librería de Python bastaste interesante, con ella se pueden enviar mensajes a WhatsApp en un determinado tiempo y lo mejor es que es una librería muy fácil de utilizar.

## Instalación
<code>pip install pywhatkit</code>

Dependiendo de la versión de Python que utilices puede que <code>pip</code> no te funcione y tengas que recurrir a <code>pip3</code>. Así que no te asustes si te aparece un mensaje de error señalando que no tienes <code>pip</code> instalado, esto me pasó a mí utilizando Ubuntu 20.04, pero es porque tengo Python 3.8 por defecto.

## Importando la librería

Para importar esta librería se tiene que seguir los pasos habituales de Python, por lo tanto solo tendríamos que escribir el siguiente código:
</br></br><code>import pywhatkit</code>

## Enviado nuestro primer mensaje

La sintaxis para enviar un mensaje desde pywhatkit es sumamente sencilla y fácil de entender, tan solo debemos ingresarle 4 argumentos y listo. A continuación se muestra el ejemplo:


```
import pywhatkit as pw

pw.sendwhatmsg("+919876543210", "Hello, World", 15,00)

``` 

## Argumentos

Como se ve en el ejemplo anterior, la sintaxis es fácil de entender y sus argumentos son básicos para enviar un mensaje. Debemos usar la función <code>sendwhatmsg</code> y dentro colocar el número telefónico de la persona a quien va dirigido (incluyendo el código de páis), luego el mensaje, para finalmente colocar la hora (en formato de 24 horas) seguido por el minuto en que se desea enviar.

## Detalles a tomar en cuenta

El script cuando es ejecutado toma en cuenta el tiempo en que demora abriendo WhatsApp Web para luego enviar el mensaje. De hecho, en la terminal muestra el tiempo en que va a conectarse a abrir el sitio web y la hora en que será enviado el mensaje.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611697147247/AXJ54SF7l.png)

Creo que está de más mencionar que necesitas tener una conexión a internet para poder ejecutar el script, no funciona de la manera en que lo hace Telegram con sus mensajes programados en los que se escoge la fecha y la hora y el mensaje es enviando independientemente de si hay conexión o no a internet.

## Conclusiones

Me parece que este módulo o librería es una manera bastante fácil para programar el envío de mensajes a WhatsApp. Tiene muchas limitaciones por supuesto, pero puede ser una opción a tomar en cuenta en esas ocasiones en que estamos trabajando en la computadora y necesitamos enviar un mensaje urgente a una hora determinada; este script nos podría ayudar en ese sentido.

También mencionar que <code>pywhatkit</code> tiene otras funciones, las cuales están detalladas en el siguiente enlace:  [Documentación](https://pypi.org/project/pywhatkit/) 

Y sin más por el momento, nos leemos después en otro post.

 