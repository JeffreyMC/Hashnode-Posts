## ¿Qué es una AppImage? ¿Cómo se instala y ejecuta?

Muchos de los que estamos familiarizados con las paqueterías de Linux quizá ya sabemos las respuestas a las preguntas planteadas en el título. Sin embargo, existen algunos otros, tal vez nuevos en Linux o quizá pocos actualizados en las paqueterías, que están acostumbrados a los paquetes más comunes, como los <code>.deb</code> o los <code>.rpm</code>, pero no tienen idea de qué rayos es una <code>AppImage</code>. Es por esta razón que trataré de explicar de la forma más clara y sencilla estos «nuevos» paquetes.

# ¿Qué es una AppImage?

De acuerdo con su [sitio web](https://appimage.org/), una AppImage se define de la siguiente manera:
> Aplicaciones Linux que corren donde sea.

Además explican que la idea principal de este proyecto es tener una aplicación que contenga en sí misma todas las dependencias que necesita para ejecutarse correctamente. Detalle que muchas veces nos da dolores de cabeza a la hora de instalar un .deb o un .rpm. Este problema también es resuelto con paquetes <code>snap</code> o <code>flatpak</code>, pero involucra otras desventajas como su rendimiento o espacio en disco, tema que quedará para otro post.

## Ventajas

* **Fácil de ejecutar: ** Más adelante explico el proceso, que de verdad no tiene mucha ciencia.
* **Confiable: **  Con estas aplicaciones recibes el paquete directamente del autor, sin necesidad de intermediarios.
* **Veloz: ** Su ejecución es más veloz que paquetes snap o flatpak.
* **Compatibilidad: ** AppImage es compatible con todas las distribuciones populares de Linux, tales como: Debian, Arch, Ubuntu, Fedora, OpenSUSE, Red Hat, entre otras.
* **Open Source: ** Esta paquetería es de código abierto, lo cuál permite ser utilizado en aplicaciones personales y/o comerciales.

## Desventajas

* De momento lo único que puede considerarse como una «desventaja» y ojo, no todos opinan igual, es que muchas de estas aplicaciones no crean accesos directos en menús o escritorio, por lo que esta parte se tiene que hacer de manera manual, que vamos, tampoco es algo que requiera de muchos conocimientos en el sistema, pero entendiendo que hay personas que no cuentan con el tiempo para realizar esto y por eso se puede considerar como un punto negativo.


# Instalación

Aquí va la parte que muchos aman de estos paquetes, y es que ni siquiera necesitas permisos root para poder ejecutarlos. Tan solo necesitas brindarle permisos de ejecución y listo. Sí, así como lees, solo te queda dar doble click y la aplicación se ejecutará.

Existen dos maneras de brindar permisos de ejecución a una AppImage: a nivel gráfico y a nivel de terminal. Ya quedará de tu parte decidir cuál te resulta más fácil o más cómoda.

## Modo gráfico

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1612127507138/HOoww_u2r.png)

En este caso solo debes dar click derecho sobre la aplicación e ir a la pestaña de permisos. Luego solo debes marcar la casilla en la que permites al archivo poder correr como un programa.

## Modo terminal

Para asignarle permisos de ejecución a una AppImage solamente se tiene que ejecutar el siguiente comando:

<code>chmod a+x example.AppImage</code>

En donde <code>example</code> es el nombre de la aplicación que deseas ejecutar.



# Ejecución


## Modo gráfico

En este caso simplemente debes dar doble click sobre la aplicación. Fácil ¿no?

## Modo terminal

Para esta otra opción -para los adictos a la terminal- deben ejecutar el siguiente comando:

<code>./example.AppImage</code>

En donde <code>example</code> es el nombre de la aplicación. También debes estar posicionado sobre el directorio en donde se encuentra la aplicación, de otra manera tendrás que indicarle la ruta absoluta o relativa, según sea el caso.

---

Y bueno, esos serían los conceptos básicos acerca de esta paquetería, muchos lo amarán y otros no tanto. Al final queda en cada quién evaluar qué tipo de paquete se le hace más sencillo u óptimo para utilizar; pero sin lugar a duda es un proyecto muy ambicioso que hará más fácil la vida de muchos.

Nos leemos en una próxima.