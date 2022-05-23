## Siete extensiones que utilizo en VSCode

Visual Studio Code es uno de los editores de código más populares en la actualidad, su potencia y personalización lo convierten en una de las mejores herramientas para los desarrolladores de aplicaciones web, móvil y de escritorio. Por esta razón les traigo 7 extensiones que utilizo en Visual Studio Code para programar en web. 

## 1. LiveServer

![Live-Server.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1611177088591/lZ-_U296X.gif)

Esta extensión permite al usuario crear una especie de servidor de desarrollo. La ventaja de esto radica en que el usuario puede ver los cambios que se le hacen al sitio web de manera instantánea con tan solo guardar el archivo. Esto evita que tengamos que refrescar la página web para poder visualizar los cambios realizados.


## 2. JavaScript (ES6) code snippets

Esta extensión contiene decenas de snippets para trabajar con JavaScript ECMAScript 6 (ES6). Los snippets se podrían interpretar como plantillas que nos permiten agilizar y reutilizar código por medio de shortcuts o accesos directos. De esta manera, y por poner un ejemplo, podemos digitar csg + tabulador, que vendría siendo el siguiente código:


```
console.log(object)
``` 


## 3. Prettier – Code Formatter
En muchas ocasiones nuestro código puede ser un desastre hablando propiamente de su formato, y su lectura se nos puede dificultar bastante, es acá donde entra Prettier. Esta extensión formatea el código de manera que su legibilidad sea óptima.

Además se puede configurar para que formatee el código cada vez que guardemos un fichero. Para poder utilizar esta característica debemos escribir el siguiente código en el archivo settings.json:


```
"editor.formatOnSave": true
``` 

## 4. Quokka.js

![quokka.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1611177318272/z5IJtF7W6.gif)


Quokka es una extensión que permite ir visualizando en tiempo real los valores de nuestras variables y objetos. Esto vendría a ser una alternativa a algunas de las herramientas para desarrollador que ofrecen los diferentes navegadores web.

Luego de instalar la extensión se debe digitar **CTRL + SHIFT + P** y escribir quokka, entre las opciones debemos elegir nuevo archivo quokka. En el caso de que quisiéramos utilizar esta extensión en un archivo ya creado, debemos digitar CTRL + K y luego digitar la tecla **Q** y ya nuestro archivo estaría listo para utilizar la extensión.


## 5. Material Icon Theme

Material Icon Theme es una extensión que si bien no aporta nada en funcionalidad, sí lo hace a nivel visual, ya que coloca el ícono correspondiente dependiendo del lenguaje de programación que estemos trabajando, dándole un toque visual bastante agradable.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611177426112/7_ARnvpAH.png)



## 6. Html tag wrapper

![preview.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1611177470053/pHWRO9eMV.gif)

Esta extensión nos permite encapsular el código HTML con otra etiqueta. Solamente debemos seleccionar la porción de código que queremos encapsular y acto seguido digitar la combinación de teclas **CTRL + i**, dando como resultado nuestro código encapsulado en unas etiquetas div.


## 7. Settings Sync

Esta es una de mis extensiones favoritas. Permite sincronizar todas (o casi todas) las configuraciones de nuestro editor de código, ya sean extensiones, temas, espacios de trabajo, fuentes, etc. entre múltiples máquinas. Con esta extensión ya podemos dejar de preocuparnos por configurar todo de nuevo si es que migramos a otra máquina o si es que trabajamos con diferentes computadoras.

Para ello es importante tener una cuenta de Github, ya que es ahí en donde se guardará toda nuestra configuración. Ya en la nueva máquina debemos instalar Settings Sync, y luego presionar CTRL + SHIFT + P y digitar **Sync** y entre la opciones seleccionamos la que dice **Sync: Download Settings** y en cuestión de segundos nuestro editor de código quedará configurado.

En caso de que queramos subir o actualizar las configuraciones, solo digitamos **CTRL + SHIFT + P** y escribimos **Sync**, y entre las opciones seleccionamos la que dice Sync: **Upload/Update Settings** y listo.


Y esas serían 7 de las extensiones que utilizo, me parece que son de las principales, pero esto podría variar dependiendo del flujo de trabajo que tengas. Y como mencioné, son extensiones propiamente para desarrolladores web, sin embargo algunas de estas pueden funcionar sin ningún problema para otro tipo de desarrolladores.