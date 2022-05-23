## Virtualiza macOS con tan solo un comando | Linux

Virtualizar el sistema operativo de la manzana mordida es todo un tema. Si has tratado de virtualizarlo en Windows te habrás dado cuenta que alcanzar este objetivo no es nada fácil, hay que ejecutar varios comandos en el PowerShell para poder configurar bien el arranque de la máquina virtual y así poder bootear sin problemas. Y ni hablar de las famosas Hackintosh, quien ha intentado crear una sabe los dolores de cabeza que genera: que no funciona el sonido, el wifi, el video, la instalación de kexts, Clover, el booteo desde el disco duro o SSD, etc. Es todo un tema.

Pero volviendo al título, los que somos usuarios de Linux la tenemos un poquito más fácil, al menos para virtualizar macOS. Solamente debemos instalar un programa y ejecutar un comando y *voilà*, el resto se hace prácticamete solo.

# Sosumi

Sosumi es un paquete Snap desarrollado por **Alan Pope** que se encarga de virtualizar macOS por medio de la máquina virtual **Qemu**. Este paquete funciona en las distribuciones más populares de Linux como Ubuntu, Fedora, Linux Mint, entre otras.

## Requerimientos

Para poder ejecutar Sosumi sin ningún inconveniente, debemos cumplir con ciertos requisitos, nada fuera de lo normal para virtualizar, por ejemplo:

* Contar con un procesador que soporte virtualización (tener la opción activada, por supuesto).
* Tener instalada la administración de paquetes snap, en caso contrario ejecutar <code>sudo apt install snapd</code> (Debian). Para las demás distribuciones pueden ver la documentación en [este enlace](https://snapcraft.io/docs/installing-snapd).
* Tener al menos 68GB de almacenamiento libres.

> NOTA IMPORTANTE: recordar que el acuerdo de licencia de Apple no permite ejecutar macOS en una máquina virtual o hardware que no sea hecho por Apple. Así que puedes continuar con el tutorial bajo tu propio riesgo.

# Instalación

El primer paso es instalar Sosumi mediante el siguiente comando:

```bash
sudo snap install sosumi
```
Una vez instalada ya la puedes encontrar en tu listado de aplicaciones. La ejecutamos y se abrirá una terminal en la que iniciará la máquina virtual. No está de más decir que esa terminal no puede ser cerrada durante todo el proceso, ya que esto detendría el progreso y habría que comenzar de nuevo.

Por defecto Sosumi descarga la versión de macOS 10.15 Catalina, así es; no debes descargar ni siquiera la imagen del sistema. Las características por defecto de la máquina virtual son:

* 2GB de memoria RAM.
* Procesador de 2 núcleos

Estas características se pueden cambiar, pero más adelante veremos el proceso.


Luego de descargar el sistema operativo, que son alrededor de unos 2 GB, se desplegará la siguiente pantalla:


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1625537539320/ftbVzYOqn.png)

Si estás familiarizado con macOS ya esta parte te será familiar, no cambia en lo absoluto. Para los demás, debemos realizar los siguientes pasos:

>Nota: para tomar o soltar el control del cursor en la máquina virtual podemos presionar la combinación de teclas CTRL + ALT + G.

### Paso 1

Selecionamos la opción que dice **boot macOS install [...]**. Seguidamente, debemos seleccionar la opción de **disk utility** para proceder a darle formato a la unidad virtual que creamos.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1625537874794/pq33_-w7x.png)

### Paso 2

Una vez en el disk utility seleccionamos el disco que creamos, aparece con el nombre **Apple Inc. VirtIO** que será de unos ~68.72GB. 


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1625538284695/Mwt8a79de.png)

En la parte superior seleccionamos la opción **erase**. Se desplegará una pequeña ventana como la siguiente:


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1625538486579/9jWXMtWqe.png)

En ella le ponemos un nombre a la unidad y el resto de opciones las dejamos como vienen por defecto. Hecho esto ya podemos cerrar la ventana de Disk Utility.

### Paso 3

Seleccionamos la opción de reinstall macOS.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1625538651997/umwR63kIi.png)

### Paso 4

Seleccionamos la opción de **agree**.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1625538706116/EAcxY5Pxy.png)

### Paso 5

Seleccionamos la unidad que formateamos hace un momento y le damos en instalar.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1625538886408/h2IZvTohR.png)


### Paso 6

Tomarse una taza de café y esperar. La duración de la instalación puede variar dependiendo de las especificaciones de tu máquina. Puede ir de los 23 a los 55 minutos.


![giphy.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1625539114270/OpGkPITii.gif)

Luego aparecerá de nuevo la pantalla de Clover, pero esta vez debemos seleccionar la opción que dice **Boot mac OS from [nombre de tu unidad] **. Seguidamente comenzará la típica configuración de usuario: nombre, contraseña, localización, activación de servicios, etc.

>TIP: para entrar o salir del modo de pantalla completa en la máquina virtual debemos presionar la combinación de teclas **CTRL + ALT + F**.

Una vez que ya estás dentro del sistema operativo verás que la resolución de pantalla no es la correcta, para ello debemos de configurar ciertas cosas, las cuales veremos a continuación.

## Cambiar resolución de pantalla

Manos a la obra. Dentro de macOS debemos abrir una terminal,  esto lo podemos conseguir si nos dirigimos al Launchpad y buscamos "terminal".


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1625540162194/NKStDrg-A.png)

Una vez tenemos la terminal abierta debemos ejecutar el siguiente comando:

```bash
diskutil list
```
Este comando desplegará las unidades que podemos montar, la que debemos ubicar es una que se llama <code>EFI</code>. En la parte superior de **Linux File System**.

![Screen Shot 2021-07-05 at 21.09.15.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1625541896558/SYbsU6SbX.png)

Para montarla ejecutamos un comando con los siguientes parámetros: 

```bash
sudo diskutil mount disk[número correspondiente]s[número que corresponde a la partición EFI]
```

De esta manera, el comando en mi caso quedaría así:

```bash
sudo diskutil mount disk2s1
```
Una vez ejecutado el comando la partición EFI estará montada, si nos vamos al Finder la podremos ubicar.


![Screen Shot 2021-07-05 at 21.15.17.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1625542182449/3HbxlVcDZ.png)

El paso siguiente es entrar al directorio EFI, luego al directorio llamado **CLOVER**. Una vez allí veremos un archivo llamado <code>config.plist</code> el cual tendremos que editar.


![Screen Shot 2021-07-05 at 21.16.12.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1625542395451/IwMb1uvF2.png)

Para editarlo daremos click derecho sobre el archivo y buscamos la opción de abrir con una aplicación, la que debemos buscar se llama <code>TextEdit</code>.


![Screen Shot 2021-07-05 at 21.16.58.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1625542475644/L7Mz4ic0g.png)

Una vez abierto el archivo buscamos la línea que diga **screen resolution**, bajo esta línea debemos cambiar lo que esté entre las etiquetas **string** por la resolución que deseamos poner. 


![Screen Shot 2021-07-05 at 21.17.56.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1625542616901/smYuKvfx3.png)

Guardamos los cambios y listo.

Ahora, reiniciamos la máquina virtual, y apenas inicie presionamos la tecla **ESC** para entrar al BIOS. Una vez allí seleccionamos la opción de **Device Manager**.

![1.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1625543029361/PBYDAYZA5.png)

Acto seguido seleccionamos la opción **OVMF Platform Configuration**.

![2.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1625543061566/0ZOdG57Lj.png)

Seleccionamos la resolución que deseamos.


![3.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1625543090966/H23tSSjI-.png)

Finalmente presionamos **F10** para guardar los cambios y salimos del BIOS. Ya tenemos configurada la resolución de la pantalla.

## Cambiar capacidad de memoria ram y núcleos del procesador

Como mencioné anteriormente, la máquina virtual se crea con 2GB de memoria RAM y con dos núcleos por defecto. Para cambiar esto debemos editar un archivo que se encuentra en el directorio de Sosumi.

Por defecto snap crea un directorio en **home** en el que se encuentran todas las aplicaciones snap instaladas. La ruta en cuestión sería la siguiente:

<code>/[nombre de usuario]/snap/sosumi/</code>.

Una vez dentro veremos los siguientes directorios:


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1625543454003/rlvWh2R-g.png)

Luego debemos entrar al directorio llamado **COMMON** y ubicar el archivo con el nombre de <code>launch</code>.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1625543538870/tIQHKZ5TL.png)

>ADVERTENCIA: se sugiere realizar una copia de respaldo de ese archivo, ya que en caso de cometer un error podemos volver a un estado anterior.

En ese archivo tenemos que dar click derecho y editarlo con la aplicación de nuestra preferencia. Nos encontraremos con algo como esto:


![Screenshot at 2021-07-05 22-14-42.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1625544897382/DaXQLYxk4.png)

Las líneas que debemos ubicar son las siguientes:

* -m 2G: cambiamos ese 2 por la cantidad de GB de RAM que queremos asignarle.
* -core=2: cambiamos ese 2 por la cantidad de núcleos que queremos asignarle.

Y con esto ya finalizaríamos la configuración total de nuestra máquina virtual con macOS Catalina.


## Sobre el incremento de memoria gráfica 

Este tema es una cuestión bastate interesante, ya que Sosumi o más bien QEMU en esta configuración utiliza un dispositivo llamado **virtio vga**.  El asunto con este dispositivo es que no cuenta con memoria de video dedicada, es decir; no cuenta con opciones para aumentar el tamaño de la memoria de video. Un detalle a tomar en cuenta.

Si desean profundizar más sobre este tema pueden leer [esta documentación](https://www.kraxel.org/blog/2019/09/display-devices-in-qemu/).

___

Y bueno, eso sería todo de mi parte, espero que este tutorial les haya servido. 

Nos leemos en una próxima.