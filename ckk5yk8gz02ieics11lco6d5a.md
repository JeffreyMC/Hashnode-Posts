## Enviar ficheros a la papelera vía terminal

Si llevas tiempo utilizando Linux quizás te has dado cuenta que hacer uso de rm en la terminal elimina los ficheros de manera definitiva, pues hoy te traigo una solución a ese inconveniente.

A la hora de utilizar el comando rm es importante verificar el comando dos veces, no vaya a ser que eliminemos un fichero que no deseamos. Una manera de evitar un borrado accidental es hacer uso del flag o parámetro <code>-i</code>, este parámetro hará que la consola pregunte si es correcto el o los ficheros a eliminar, el comando quedaría de la siguiente manera:


<code>sudo rm -i fichero.txt</code>

Sin embargo, podrán haber ocasiones en las que quizá más adelante necesitemos esos archivos por algún motivo, por lo que sería más útil contar con un comando para enviar los ficheros directamente a la papelera de reciclaje, de esta forma en caso de accidente o de necesitar estos ficheros solamente debamos dirigirnos a la papelera de reciclaje. El comando en cuestión se llama **gio**.

</br>

# Comando gio

Lo primero que hay tener en cuenta es que este comando envía los archivos a la siguiente ruta: <code>~/.local/share/Trash/files</code> en lugar de <code>~/.trash</code>. Esto es importante recordarlo en caso de buscar algún fichero eliminado.


## Eliminar fichero

Para eliminar uno o más archivos se debe ejecutar el siguiente comando:

<code>gio trash [file] </code>

## Listar ficheros

<code>gio list trash://</code>

El comando anterior viene siendo lo mismo que si ejecutáramos:

<code>ls ~/.local/share/Trash/files</code>

## Vaciar papelera

<code>gio trash --empty</code>

El comando gio tiene muchas opciones aparte de enviar ficheros a la papelera de reciclaje, para poder ver la lista de parámetros se puede utilizar el comando de «man pages» o manuales de la siguiente manera:

<code>man gio</code>



Y bueno, esos serían los usos principales de gio, que como usuarios de Linux es bueno saberlos, ya que nos podrían servir en alguna que otra ocasión. Así que espero que les sea de gran utilidad, nos leemos en una próxima.




