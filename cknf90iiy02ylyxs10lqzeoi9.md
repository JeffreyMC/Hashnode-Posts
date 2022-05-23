## Cómo minimizar la app de Signal a la bandeja del sistema (panel)

Si eres usuario de Linux y de la app de Signal, ya te habrás percatado de que una vez que cierras el programa no se minimiza al panel o la bandeja del sistema. Por eso acá te traigo un pequeño tutorial de cómo conseguir el *tray icon* de Signal.

Primeramente, cabe destacar que la aplicación de escritorio de Signal solo está disponible para distribuciones Linux basadas en Debian o Ubuntu, es decir: Debian, Ubuntu, Linux Mint, Elementary OS, entre otras.

Elegí la distribución de Ubuntu (en tres sabores) para verificar los pasos, ya que dependiendo del entorno de escritorio podrían variar las configuraciones. Los entornos de escritorio que utilicé para este fin fueron: <code>Gnome</code>, <code>KDE Plasma</code> y <code>XFCE</code>.

# Comandos

Al *launcher* de la aplicación se le debe asignar un parámetro para hacerle saber que la aplicación hará uso de un *tray icon* o ícono de bandeja. Para conseguir esto se debe agregar el siguiente argumento:


```
--use-tray-icon
``` 

En este momento te estarás preguntando que dónde diablos se coloca ese comando, así que te mostraré de forma gráfica dónde y cómo colocamos este argumento.



## Kubuntu (KDE Plasma)

Lo primero que debemos hacer es dirigirnos al menú y buscar la aplicación de Signal, luego damos click derecho y elegimos la opción de editar aplicación.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1618263214696/s3Gw9Qp9w.png)

Cuando nos aparece la ventana de edición nos movemos a la pestaña de aplicación. Allí buscamos la opción que dice comando y colocamos el comando <code>--use-tray-icon</code> antes del argumento <code>%U</code>.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1618263309975/Eo5r34Fgx.png)

Damos click en <code>OK</code> y si iniciamos la aplicación ya nos aparecería el ícono en el panel.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1618263384514/Ma_gGc7GQA.png)


## Xubuntu (XFCE)

El caso de Xubuntu es prácticamente igual al de KDE Plasma. Debemos seguir los siguientes pasos:

* Menú
* Editar aplicación
* Agregar <code>--use-tray-icon</code> al comando de ejecución

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1618265945906/EBD_kslW4.png)


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1618266040402/BdRMGIDyg.png)

De esta manera si abrimos la aplicación veríamos su ícono en el panel.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1618266091033/nkYMcHJu8.png)

## Ubuntu (Gnome)

En cuanto a Ubuntu en su versión de Gnome la cosa no es tan fácil, no se pueden editar las propiedades de las aplicaciones de manera gráfica como en KDE Plasma, XFCE o MATE. Es cierto que se pueden instalar aplicaciones como <code>MenuLibre</code> para realizar los pasos; sin embargo, me parece más oportuno hacer uso de la terminal, ya que no tendríamos que instalar nada y el problema lo solucionaríamos con un par de comandos.

Destacar que estos pasos sirven de igual manera para los entornos de escritorios anteriores, recordemos que estamos haciendo uso de distribuciones de Ubuntu, así que no habría problema con ninguna de las distribuciones basadas en Debian o Ubuntu (como Linux Mint).

### Paso 1 

Abrimos la terminal y colocamos la ruta en la que se encuentran las aplicaciones, esto puede ser a nivel root o a nivel de usuario.

* Nivel root

```
cd /usr/share/applications
``` 
* Nivel de usuario


```
cd ~/.local/share/applications
``` 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1618267956777/gBxjTvWK7.png)

### Paso 2

Luego verificamos que la aplicación se encuentre, por eso mencioné que es importante si la aplicación está instalada a nivel root o a nivel de usuario. Para verificar digitamos el siguiente comando:


```
ls -l | grep signal
``` 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1618268122287/HiWvzVMEN.png)

### Paso 3

Una vez que sabemos que la aplicación aparece listada, procedemos a editar el archivo de configuración, que en este caso aparece como <code>signal-desktop.desktop</code>. Puedes utilizar el editor de texto que desees, en este caso yo utilicé **nano**. 

> Importante recordar el archivo solo se puede editar con permisos de súperusuario.

Así que en mi caso solo debería ejecutar el siguiente comando.


```
sudo nano signal-desktop.desktop
``` 
Luego buscamos la línea que comienza con la palabra <code>Exec</code> y colocamos el argumento <code>--use-tray-icon</code> justo antes de el argumento <code>%U</code> que por lo general se encuentra al final de esa línea.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1618268215558/oz0rQZUfD.png)

Guardamos el archivo editado y procedemos a abrir la aplicación. Ya debería aparecernos en el panel.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1618268325495/dYhZUOfMh.png)

---

Y eso sería todo por mi parte. Seguramente los desarrolladores de Signal solucionen este incoveniente en futuras actualizaciones; por el momento espero que este tutorial les funcione de algo.

Nos leemos en una próxima.