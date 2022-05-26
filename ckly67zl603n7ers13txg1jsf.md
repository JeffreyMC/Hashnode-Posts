## Cambia la apariencia de la terminal con OhMyBash (Linux)

Si estás cansado de ver la misma apariencia en la terminal de Linux o solamente quieres darle un nuevo rostro, entonces este *framework* te puede interesar. 

OhMyBash es un *framework* de código abierto que permite administrar la configuración de bash. Además, con este framework no solamente puedes instalar temas, sino que también tienes la posibilidad de instalar [plugins](https://github.com/ohmybash/oh-my-bash/tree/master/plugins).

Un ejemplo de su uso es cuando tenemos un directorio que trabaja con <code>git</code>, la terminal utiliza ciertos colores para identificar en qué estado se encuentran los archivos: si han sido modificados, si están listos para un *commit* o si todo se encuentra actualizado.

## Requisitos

* <code>git</code> instalado
* <code>curl</code> o <code>wget</code> instalado
* Fuentes powerline instaladas

## Instalación

### Vía curl


```
bash -c "$(curl -fsSL https://raw.githubusercontent.com/ohmybash/oh-my-bash/master/tools/install.sh)"
``` 


### Vía wget

```
bash -c "$(wget https://raw.githubusercontent.com/ohmybash/oh-my-bash/master/tools/install.sh -O -)"
```

## Configuración

El tema que viene por defecto puede no ser el más bonito, pero es relativamente fácil cambiarlo. En [este enlace](https://github.com/ohmybash/oh-my-bash/wiki/Themes) puedes ver los temas disponibles, solamente debes recordar el nombre del tema para poder activarlo.

### Pasos

* Debes abrir el fichero llamado <code>.bashrc</code> que se encuentra en la ruta <code>~/.bashrc</code>
* Debes localizar la línea que dice <code>OSH_THEME="Your Theme Here"</code>
* Debes colocar el nombre del tema dentro de las comillas

En mi caso yo utilizo el tema llamado <code>powerline</code>. El archivo quedaría de la siguiente manera:

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1614984267301/AiOUExCKO.png)

>IMPORTANTE: debes reiniciar bash con el comando <code>src</code> para poder ver los cambios.

De esta manera la apariencia de la terminal pasaría de verse así:

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1614983827484/l5DaJnawn.png)

A verse de esta forma:

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1614984220580/LKQUolrP5.png)

> IMPORTANTE: Debes tener instaladas las fuentes Powerline para visualizar correctamente los temas. En cualquier caso, se pueden instalar con el comando <code>sudo apt install fonts-powerline</code>. Luego solo las seleccionas en las preferencias de la terminal y listo.

## Ejemplo de un directorio trabajando con git

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1614984365887/5FRPGGxDR.png)

Dependiendo de los estados de los archivos que se estén monitoreando, los colores variarán, lo cual facilita la identificación de sus estados.

Sitio web oficial de OhMyBash: https://ohmybash.nntoan.com/

## Desinstalación

Para remover los cambios que se han hecho sobre la terminal solo debemos ejecutar el siguiente comando.

```
uninstall_oh_my_bash
```

Este comando regresará a la configuración que tenías antes de instalar OhMyBash.

---

Y eso sería todo por este post, nos leemos en una siguiente publicación.