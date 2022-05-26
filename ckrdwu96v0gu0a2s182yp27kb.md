## Crea un USB booteable desde la terminal | Linux

En Linux existen muchos programas gráficos para crear USB's booteables. Por ejemplo, Start Disk Creator es uno de ellos, liviano y muy fácil de utilizar, solo seleccionas el fichero .ISO y el dispositivo USB que vas a utilizar y eso es todo.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1626894513045/P54J1oN3t.png)

Sin embargo, habemos muchos usuarios que preferimos no salir tanto de la terminal para realizar ciertas tareas y es por eso que acá explico cómo crear un USB booteable vía terminal. Solo se necesitamos montar el dispositivo que vamos a utilizar y luego ejecutar un comando.

# PASOS

## 1. Identificar la ruta del dispositivo USB

Para ellos nos valemos del comando <code>lsblk</code>

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1626895240327/oKlsUYCIQj.png)

En mi caso mi dispositivo es el que aparece subrayado, es decir; la unidad <code>sdb</code>. De todas formas, si se te dificulta ubicar tu dispositivo USB puedes utilizar el comando <code>sudo fdisk -l</code>.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1626896636597/rkv-Y1KSj.png)

Mi dispositivo aparece subrayado. Lo que vamos a necesitar es saber su ruta, para este ejemplo sería <code>/dev/sdb</code>.

## 2. Identificar la ruta de la imagen ISO

En mi caso la ruta de la imagen iso es <code>/home/jeff/Downloads/imagen.iso</code>. 

## 3. Comando dd

El comando para crear el USB booteable es <code>dd</code>. Para realizar esto necesitamos brindarle algunos parámetros, en cuestión los más importantes son 2:
* **if**: quiere decir **i**nput **f**ile, acá debemos colocar la ruta en la que se encuentra la imagen ISO.
* **of**: quiere decir **o**utput **f**ile, acá debemos colocar la ruta en la que se encuentra el dispositivo USB.

Solamente con esos parámetros ya podríamos crear el USB booteable. Por otra parte, si lo ejecutas podrás ver que la terminal no muestra ninguna barra de progreso, solo quedará como "congelada" esperando a que termine de realizar la tarea. Sin embargo, dd cuenta con un parámetro llamado <code>status=progress</code> que nos permitirá visualizar el progreso del copiado.

Así que para este ejemplo el comando quedaría así:

```bash
sudo dd if=/home/jeff/Downloads/[imagen_iso] of=/dev/sdb status=progress
```

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1626896417314/SakHARbLr.png)

Y eso sería todo, tendríamos una USB totalmente booteable.

---
Nos leemos en una próxima.
