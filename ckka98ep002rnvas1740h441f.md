## Debugging en Python con Icecream


Si eres de los que hace debugging en Python utilizando <code>print()</code> o <code>log()</code>, podría ser que esta información te resulte interesante. 

Sucede que existe un módulo llamado Icecream -curioso nombre- que hace de tu debugging una experiencia poco más agradable. Este módulo soporta las versiones 2 y 3 de Python, además de PyPy2 y PyPy3.

## ¿Cómo funciona?

Pues para mostrar sus capacidades no hay nada mejor que un ejemplo. Pero para comenzar a utilizar Icecream tendremos que instalarlo con <code>pip</code> con el siguiente comando:

<code>pip install icecream</code>
 
Una vez instalado el módulo procederemos a realizar el debugging del resultado de una función. Supongamos que tenemos la siguiente función:

```
def msg(text):
    return "Hello, " + text
``` 
Suponiendo que siempre verificamos la función con print() tendríamos que hacer lo siguiente:

```
print(msg('Jeff'))
```
Cuyo resultado sería:

<code>Hello, Jeff</code>

Ahora, este tipo de debugging no nos arroja nada de información relevante más que el resultado de la función que declaramos. Aquí es donde Icecream nos ayuda mostrando los argumentos que ingresamos más la salida que estos devuelven.

Cabe destacar que para utilizar Icecream debemos importar su módulo como sigue:

<code>from icecream import ic</code>

Después de importar su módulo ya solo nos queda probarlo. Para ello solo debemos utilizar ic() y entre sus argumentos ingresamos la función que declaramos.

```
ic(msg('Jeff'))
``` 
El *output* o salida sería la siguiente:

<code>ic | msg('Jeff'): 'Hello, Jeff'</code>


De hecho Icecream también funciona incluso si no se le asignan argumentos. Esto podría ayudarnos a ver qué partes del código se van ejecutando, <code>ic()</code> muestra el nombre del archivo, el número de línea y la función padre o función en la que fue llamada.


```
def foo():
    ic()
    first()
    
    if expression:
        ic()
        second()
    else:
        ic()
        third()
``` 
La consola arrojaría el siguiente resultado (dependiendo del caso):

<code>ic| example.py:4 in foo()</code>
</br>
<code>ic| example.py:11 in foo()</code>

Y bueno, eso sería todo por este post. Icecream tiene muchas más funcionalidades, además de estar disponible para otros lenguajes como PHP, Dart, Rust, C++, Go y Node.js. Por eso si les interesa saber qué más se puede alcanzar con este módulo les invito a leer su documentación en el siguiente enlace:

[Icecream Documentation](https://github.com/gruns/icecream) 










