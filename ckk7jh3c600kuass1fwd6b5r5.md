## Generador de contraseñas | Password generator | Python

Recientemente estaba retomando algunos conceptos básicos de Python y me puse jugar con algunas librerías gráficas, entre ellas <code>Tkinter</code>, <code>Gi</code> y <code>PyGtk</code>. Mientras practicaba realicé dos pequeños proyectos: una calculadora con GTK y un generador de contraseñas con Tkinter.

Y como pudieron ver en el título hoy solo explicaré el código del generador de contraseñas, el de la calculadora lo dejaré para después. Además, no comentaré la parte gráfica, solo me enfocaré en el algoritmo que utilicé para generar contraseñas aleatorias mediante algunos parámetros.


## Caracteres utilizados

Para esta parte me valí de los más comunes y más utilizados para establecer contraseñas seguras, es decir: letras mayúsculas, minúsculas, números y finalmente algunos símbolos especiales.

```
minusculas = 'abcdefghijklmnopqrstuvwxyz'
mayusculas = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
numeros = '0123456789'
simbolos = '[]{}%&$;._-'
``` 

Luego de esto declaré una variable que junta las variables anteriores en un solo string.

```
caracteres = minusculas + mayusculas + numeros + simbolos
``` 

Una vez hecho lo anterior se tiene que declarar la longitud que tendrá la contraseña, en mi caso entendí que con 16 caracteres de longitud es más que suficiente.

```
passLongitud = 16
``` 

Finalmente viene la parte en la que se genera la contraseña de manera aleatoria, para ello debemos importar el **módulo random** y colocarlo al inicio del archivo, tal y como se hace con todos los módulos de Python.

```
import random
``` 
Para generar la contraseña debemos incluir el siguiente código.

```
password = " ".join(random.sample(caracteres, passLongitud))
``` 
El código anterior lo que hace es que asignar a una variable llamada password el string generado mediante random y su método sample.  Random comienza a generar un string de 16 caracteres de longitud con letras y símbolos aleatorios contenidos en la variable caracteres.

Si queremos verificar el password generado solamente debemos hacer un print.

```
print (password)
``` 

El código completo quedaría de la siguiente manera:

```
import random

minusculas = 'abcdefghijklmnopqrstuvwxyz'
mayusculas = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
numeros = '0123456789'
simbolos = '[]{}%&$;._-'

caracteres= minusculas + mayusculas + numeros + simbolos

passLongitud = 16

password = " ".join(random.sample(caracteres, passLongitud))

print (password)

``` 

Si desean ver el código funcionando ya de manera gráfica, les dejo el proyecto en Github en el que utilicé Tkinter. El programa es simple, solo tiene una entrada y dos botones: uno para generar la contraseña y otro para copiar al portapapeles.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611274782352/43qYfeqWZ.png)

Proyecto en Github:  [Generador de contraseñas](https://github.com/JeffreyMC/Password-Generator) 







