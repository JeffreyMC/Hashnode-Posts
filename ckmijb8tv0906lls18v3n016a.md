## ¿Qué rayos es un hard link en Linux?

En una publicación anterior mencioné lo que significaban los [soft links](https://jeffcoding.com/link-simbolicos) en Linux, además de cómo crearlos y utilizarlos de forma correcta. Sin embargo, faltó definir los *hard links*, que se crean con el mismo comando <code>ln</code>, pero su funcionamiento es particularmente distinto.

Es por esto que en esta publicación trataré de explicar el funcionamiento de un *hard link*, cómo crearlos y en lo que se diferencian de los links simbólicos o *soft links*.

# Hard Links

Primeramente hay que comprender que en Linux cada fichero comienza con un *hard link* por defecto. Este link es un enlace del nombre del fichero hacia los datos que este almacena en el sistema de archivos. Así que crear otro *hard link* de ese mismo fichero implica otras cosas.

Por ejemplo, puedes crear un nuevo nombre de archivo que apunte exactamente a los datos a los que apunta otro archivo con el mismo o distinto nombre. ¿confuso, no? Me explico: lo que quise decir es que existirían dos archivos apuntando hacia un mismo banco de datos.

## Ejemplo de hard link

Supongamos que creo un archivo en <code>~/Desktop/</code> con el nombre <code>test.txt</code> y escribo "hello world" dentro, puedo verificar mediante <code>ls</code> que se acaba de crear un *hard link* con el texto "hello world" en su interior.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1616288570001/AR3RkCdYy.png)

Si observan en la información desplegada en la terminal, aparece un **1** antes del nombre del propietario del archivo, que en este caso es **jeff**. Ese número indica los links que apuntan hacia ese fichero.

Ahora, creamos un *hard link* con el nombre <code>new_test.txt</code> que apunte hacia el <code>test.txt</code> que se creó anteriormente, pero en una diferente ruta:

La sintaxis sería: <code>ln (ruta del archivo orginal) (nueva ruta y nombre de archivo)</code>


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1616290117264/txMiNU7bw.png)

Así que, si realizamos un <code>ls</code> en la ruta en la que se encuentra el *hard link* creado se obtiene lo siguiente:


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1616290162234/neJFYUGkQ.png)

Podemos verificar que ahora aparece un número **2** antes del nombre del propietario del archivo, lo cual indica que existen dos links que apuntan a ese fichero.

Por otro lado, si desplegamos la información de ese nuevo archivo, podemos verificar que muestra exactamente lo mismo que el archivo original.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1616291065015/AieDsZnhL.png)


## Detalles por tener en cuenta

* Los cambios realizados a un archivo afectarán de igual manera al otro fichero.
* Ambos archivos comparten los mismos permisos y propietarios.
* Si se borra el archivo original, los datos seguirán existiendo en el *hard link* creado.
* Los datos solo pueden ser borrados desde la unidad una vez se hayan eliminado todos los links vinculados.
* Inicialmente no se pueden crear *hard links* de directorios o archivos especiales.

## ¿Cómo comprobar si un archivo es un hard link?

Como los datos de los *hard links* son idénticos a los datos del archivo original, comparten el mismo número de <code>inode</code> en el sistema de archivos. Por ejemplo, si realizamos un <code>ls -i</code> a los ficheros creados en los ejemplos de este artículo, veríamos lo siguiente:


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1616291869414/7XRxQnl3p.png)

El *flag* o argumento <code>i</code> utilizado con el comando <code>ls</code> permite visualizar los inodes de los archivos. En el ejemplo anterior se puede comprobar que ambos comparten la misma numeración de <code>inode</code> (**12718340**), lo cual nos indica que se tratan de *hard links*.

## ¿Cuándo utilizar hard o soft links?

Pues en realidad esto depende de la situación en que te encuentres, uno o el otro podría encajar dependiendo de tu necesidad. Aún así, es bueno tener en claro lo siguiente:

* Los *soft links* son archivos que SIEMPRE apuntan de un nombre de archivo a otro nombre de archivo, que luego apuntan a información dentro de la unidad de almacenamiento.
* Los *hard links* son archivos que SIEMPRE apuntan a datos dentro de la unidad de almacenamiento.

---

Y eso sería todo en cuanto a los conceptos básicos de los *hard links*, al principio el concepto parecerá un poco confuso, pero en la práctica se vuelve más claro y fácil de entender.

Nos leemos en una próxima.