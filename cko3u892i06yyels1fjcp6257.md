## Dale un bonito formato a tus tablas con PrettyTable | Python

Muchas veces trabajamos con datos en consola a los que debemos darle un formato de tabla para desplegar la información de forma ordenada, sin embargo, suele pasar que la tabla no respeta el diseño que le damos, ya sea por el tamaño de las palabras o por un error nuestro. Afortunadamente topé en Instagram con una recomendación muy buena de una librería de Python llamada **prettytable**.

# prettytable

prettyable -sí, así en minúscula- es una es una librería de Python que hace uso de su clase **PrettyTable** para crear tablas relacionales.

## Instalación

La instalación se realiza vía pip (o pip3) mediante el siguiente comando:

<code>pip install prettytable</code>

## Uso

Lo primero que debemos hacer es importar la librería y su clase:

```Python
from prettytable import PrettyTable
```

Luego especificamos los encabezados de la tabla:

```python
myTable = PrettyTable(["Name", "LastName", "Profession"])
```
Para agregar datos a las filas seguimos la siguiente sintaxis:

```python
myTable.add_row(["Bryan", "Cárcamo Luna", "Developer"])
myTable.add_row(["Jeffrey", "Muñoz Castro", "Developer"])
myTable.add_row(["Maureen", "Muñoz Martínez", "Tech. Support"])
myTable.add_row(["María", "Vargas León", "Teacher"])
```
Finalmente solo debemos imprimir la tabla:

```python
print(myTable)

```

El resultado sería este:


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1619756679919/sc0Y-IGc-.png)


## Resumen del código

```python
from prettytable import PrettyTable

#encabezados
myTable = PrettyTable(["Name", "LastName", "Profession"])

##filas
myTable.add_row(["Bryan", "Cárcamo Luna", "Developer"])
myTable.add_row(["Jeffrey", "Muñoz Castro", "Developer"])
myTable.add_row(["Maureen", "Muñoz Martínez", "Tech. Support"])
myTable.add_row(["María", "Vargas León", "Teacher"])

#Imprime la tabla
print(myTable)

```

---

Y ese es el uso más sencillo que se le puede dar. PrettyTable tiene otras funciones interesantes como la de importar datos desde un archivo <code>CSV</code> o incluso importar tablas de una base de datos.

Más información [en este enlace.](https://pypi.org/project/prettytable/)