## OnionShare: comparte archivos de forma anónima y segura

Luego de todo el revuelo que han causado las políticas que WhatsApp quiere implementar en cuanto a la privacidad de los datos de la aplicación, muchas compañías de software han aprovechado el momento y han hecho publicidad con productos que respetan la privacidad de sus usuarios. Podría mencionar los casos más sonados como Telegram o Signal, pero en esta ocasión quiero mostrarles una aplicación para compartir archivos llamada **OnionShare**.

Pero antes de entrar de lleno con este programa, me parece importante explicar de manera muy general en qué consiste la red Tor, de la cual depende OnionShare.

## Tor

Tor es el acrónimo de **T**he **O**nion **R**outer, que en español vendría siendo algo como «enrutador cebolla». Su analogía con la cebolla se debe a que Tor hace uso de nodos que protegen y enmascaran (como las capas de una cebolla) de alguna forma el tráfico que se genera y que de otro modo podría ser monitorizado.

### ¿Cómo funciona?

Para enrutar el tráfico de navegación, Tor hace uso de tres nodos (conocido como circuito Tor) antes de llegar al destino. De esta forma, alguien que quisiera espiar debería monitorizar al mismo tiempo tanto la conexión del nodo de entrada como la del nodo de salida o sitio web de destino para así poder descubrir su ubicación.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1614399448807/KcRKIHQ-f.png)

Los nodos son mantenidos por voluntarios, de hecho [acá](https://tormap.void.gr/) se pueden ver algunos de los nodos utilizados. Por otra parte, los datos se cifran entre cada nodo para que nadie pueda ver en qué consiste su tráfico o dónde pasa el siguiente nodo. Sin embargo, el tráfico a través de conexiones inseguras (no HTTPS) no se cifrará entre el nodo de salida y el servidor de destino, lo que significa que debes tener cuidado al usar sitios web que no ofrecen certificados de seguridad mediante el protocolo HTTPS.

Y ya explicado por encima todo lo referente a Tor, podemos entrar en materia.

## OnionShare

OnionShare es una aplicación de software libre desarrollada por **Micah Lee**, cuya función es la de mantener la seguridad y el anonimato de la persona que comparte los archivos. Esta aplicación utiliza la red de **Tor** para el envío de ficheros, lo cual hace muy difícil el rastreo del origen de envío.

En su más reciente actualización añadieron nuevas funciones que la vuelven aún más atractiva. Ahora puedes recibir archivos localmente, hospedar sitios web y crear un chat para intercambiar mensajes de forma anónima.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1614378617645/Rfb2VRR4e.png)

En palabras de Lee:

> Básicamente es 100% *darknet* o red oscura.

Y es que el problema de la mayoría de servicios para compartir archivos recae en que el usuario debe confiar en ellos. Sin embargo, existen leyes en diferentes países que dado el caso exigen que estos datos sean revelados por equis razón. Con OnionShare no pasa así, puesto que una vez el archivo es recibido, no queda existencia en la red.

> Tan pronto la persona descarga el archivo, puedes cancelar el servidor web y el archivo quedará inaccesible para cualquiera.
- Micah Lee

## ¿Cómo funciona?

Cuando el usuario desea enviar un archivo, el programa crea una dirección web (URL) protegida por una contraseña, la cual es alojada en la red Tor, esto se conoce como servicio oculto de Tor. Al destinatario se le provee la URL y la contraseña de manera cifrada.

Una vez el usuario ingresa a esa URL por medio del navegador Tor -esto es muy importante- podrá tener acceso a los archivos, y al ser descargados (al emisor se le notifica) se puede detener el servidor web y los archivos quedarán totalmente inaccesibles.

### Envío de archivos:

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1614380555152/iSpL6c0Dj.png)

### Recibo de archivos (desde el navegador Tor):

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1614380464312/DNuLbvxxX.png)

### Recibo de archivos de manera local

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1614380824002/Kh211i4xV.png)


---

## Conclusiones

Luego de probar todas las funciones de OnionShare puedo decir que cumple con lo que promete, además, es una gran mejora respecto a su versión anterior, la cual presentaba problemas importantes de velocidad al enviar o recibir archivos. 

Hay que tener presente que toda la transferencia se realiza por medio de la red Tor, así que tampoco se puede esperar una velocidad como la que estamos acostumbrados con otros servicios, este es el costo de la privacidad y anonimato.

Lo que sí echo bastante en falta es la disponibilidad de un tema oscuro, espero que en futuras versiones agreguen esta característica, que si bien no perjudica su funcionamiento, perjudica la experiencia de usuario de muchos.

---

OnionShare está disponible para Windows, MacOS y Linux, se puede descargar del siguiente enlace:

[Descargar OnionShare](https://onionshare.org/)

Y acá puedes descargar el navegador Tor.

[Descargar Tor Browser](https://www.torproject.org/download/)

---

**Fuente consultada:**

Hougen, A. (2021). Tor Browser Review. Recuperado de: https://www.cloudwards.net/tor-review/