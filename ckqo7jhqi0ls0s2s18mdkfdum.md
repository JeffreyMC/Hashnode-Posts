## Cambia tu animación de inicio en Linux

En la actualidad soy usuario de Ubuntu MATE 20.04, es una distribución que conozco desde hace muchos años y que, a pesar de que MATE -al día de hoy- parezca un entorno de escritorio obsoleto, sigue satisfaciendo mis necesidades.

Pero bueno, no vengo a hablar de esta distribución, sino que, uno de los aspectos que no me gusta de ella es su animación de inicio o como se le conoce técnicamente: **boot animation** o **splash screen**. La animación en cuestión se ve algo así:



![Peek 2021-07-03 13-09.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1625339378608/bd_WjaJfz.gif)

Así que, si estás en una situación similar en la que yo estuve, te mostraré cómo cambiar el boot animation y en su lugar poner uno de tu gusto.

>Cabe resaltar que este tutorial va dirigido a aquellas distribuciones basadas en Debian, en otras como Fedora el proceso varía un poco.

# Plymouth

Plymouth es la aplicación encargada de mostrar la animación al inicio y apagado de los sistemas operativos de Ubuntu. Todos los temas que instalemos deben estar en la siguiente ruta para su correcto funcionamiento: <code>/usr/share/plymouth/themes/</code>.

Gracias a los repositorios oficiales de Ubuntu podemos tener a la mano todas las animaciones de los diferentes sabores de Ubuntu, tales como: Ubuntu, Ubuntu MATE, Ubuntu Budgie, Xubuntu, Kubuntu, Lubuntu, etc.

Para poder ver la lista completa de los temas que podemos instalar, debemos dirigirnos a la terminal e ingresar el siguiente comando:


```bash
apt list plymouth-theme*
``` 


![terminal.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1625340133165/uzzcyBlZY.png)

Luego, si deseamos instalar uno de esa lista debemos ingresar el siguiente comando: 

```bash
sudo apt install plymouth-theme-[nombre del tema]-logo plymouth-theme[nombre del tema]-text
``` 


Una vez instalado ya podemos seleccionarlo y configurarlo como tema por defecto en nuestra distribución, el comando que debemos ingresar es el siguiente:


```
sudo update-alternatives --config default.plymouth
``` 

Este comando mostrará la siguiente pantalla:


![Screenshot at 2021-07-03 13-32-20.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1625340755080/GHA4ZJE5R.png)

El tema que aparece con un asterisco (*) es el que tenemos configurado por defecto, para cambiarlo solo debemos digitar el número al que pertenece el tema que acabamos de instalar y luego presionar la tecla ENTER.

Finalmente, solo quedaría actualizar el archivo <code>initramfs</code> y listo. Por lo cual debemos ejecutar el siguiente comando:

```bash
sudo update initramfs -u
``` 

De esta manera ya tendríamos nuestra nueva *boot animation* instalada y configurada correctamente.

## Instalando temas de terceros

Por la web existen muchos sitios que ofrecen distintos temas para el boot animation, su instalación es muy sencilla y la veremos a continuación.

Si desean ver varios temas les recomiendo el repositorio de [Aditya Shakya](https://github.com/adi1090x/plymouth-themes/) que se encuentra en Github.


![53.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1625341380796/-ptMPZi5y.gif)

### Paso 1

Descargamos el tema que nos guste y los descomprimimos en la ruta: <code>/usr/share/plymouth/themes/</code>. 

### Paso 2

Instalamos el tema con el siguiente comando.
```bash
sudo update-alternatives --install /usr/share/plymouth/themes/default.plymouth default.plymouth /usr/share/plymouth/themes/[nombre_directorio_tema]/[nombre_tema] 100
```
 
### Paso 3

Seleccionamos el tema que instalamos:


```bash
sudo update-alternatives --config default.plymouth
``` 

### Paso 4

Actualizamos el archivo <code>initramfs</code>


```Bash
sudo update-initramfs -u
``` 

---

Y eso sería todo. Nuestra distribución GNU/Linux ya quedaría con una animación de inicio personalizada.

Nos leemos en una próxima.

