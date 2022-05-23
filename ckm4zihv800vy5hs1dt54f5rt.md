## ¿Qué rayos es un link simbólico en Linux?

¿Alguna vez has escuchado acerca de los links simbólicos en Linux? En caso de que lo hayas escuchado o no, acá te traigo un pequeño artículo acerca de qué es un link simbólico, para qué sirve, cómo funciona, entre otras cosas.

# Links simbólicos

También conocido como *soft links*, los links simbólicos son un tipo especial de archivo que apunta hacia otro archivo o directorio. Sí, se podría decir que son similares a los accesos directos de Windows.

Es por esto que, si accedes a un link simbólico, estás accediendo al fichero o directorio objetivo (*target*). Por lo cual es importante mencionar que todos los cambios que se realicen en un link simbólico van a afectar también a los ficheros a los que apunta.

## ¿Cómo identifico un link simbólico?

En la mayoría de distribuciones los links simbólicos se diferencian de los demás por contener el símbolo <code>-></code>, que hace referencia hacia el fichero al que apunta. Además, en la parte izquierda donde se visualizan los permisos de acceso, es decir; donde se indica de qué tipo de archivo se trata, comienza con la letra <code>l</code>. 

De igual forma en algunas distros aparecen con un color diferente.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1615332405136/hRO-MJsjB.png)

## ¿Para qué funcionan?

Bueno, si lo comparamos con los accesos directos de Windows, podríamos decir que cumplen la misma función, es decir; nos permite acceder a un archivo desde cierto punto sin tener que estar navegando entre directorios y/o *paths* extensos.

## ¿Cómo crear un link simbólico?

Para crear un link simbólico tenemos que valernos del comando <code>ln</code> con el *flag* <code>-s</code> como argumento, luego debemos poner la dirección del *target* o archivo objetivo seguido del nombre que tendrá nuestro link simbólico. Por ejemplo:


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1615332855539/ARqBedcmQ.png)

El argumento <code>-s</code> especifica que se trata de un link simbólico, en caso de no ponerlo se crearía lo que se conoce como [Hard Link](https://jeffcoding.com/hard-links).

## Detalles a tomar en cuenta

Si eres muy observador supongo que te diste cuenta que los links simbólicos se crean con todos los permisos, es decir <code>777</code> o <code>rwxrwxrwx</code>. ¿Que pasa si el link está apuntando a un fichero que tiene permisos específicos? No pasa nada. Esto parecería una brecha de seguridad importante, pero no lo es.

Los links simbólicos se crean por defecto con todos los permisos, pero respeta los permisos del fichero *target*, esto quiere decir que aunque crees un link simbólico de un archivo que no cuenta con permisos de lectura -por ejemplo-, no quiere decir que el usuario ya podría leerlo.

Otro aspecto interesante es que no puedes saber a qué tipo de archivo apunta el link simbólico hasta que sigas la ruta a la que apunta. No, ni siquiera con el argumento <code>-l</code> de <code>ls</code>.


---

Y eso sería todo por este post, nos leemos en una próxima.