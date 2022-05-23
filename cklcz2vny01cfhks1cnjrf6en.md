## Cómo integrar git-bash en Visual Studio Code (Windows)

Como usuario de Linux que tiene que recurrir de vez en cuando a Windows para realizar ciertas tareas que por una u otra razón no se pueden concretar en Linux, integrar la terminal de Git en Visual Studio me ha caído como anillo al dedo. Dejo claro que programo muy poco desde Windows, pero es bueno estar cubierto por ese lado.

También supongo que si entraste a este post doy por hecho que conoces Git y VS Code. Lo menciono porque acá no voy a explicar qué es cada cosa; esto simplemente es un minitutorial que le llegará a servir a más de uno.

## Requisitos

* Visual Studio Code instalado
* Git instalado (también la opción de git-bash).

## ¿Por qué cambiar la terminal que viene por defecto?

Cuando instalamos VS Code por primera vez, nos damos cuenta que la terminal que viene por defecto es <code>CMD</code>, es decir, la terminal que utiliza por defecto Windows. En algunas ocasiones también estará disponible la terminal PowerShell. Sin embargo, las ventajas que ofrece <code>git-bash</code> en comparación con las otras dos terminales que mencioné, son muchas.

Por ejemplo, desde git-bash puedes utilizar comandos básicos y típicos de <code>bash</code> -esto es una alegría si vienes de Linux o MacOS-. Además, puedes ejecutar comandos de <code>NodeJS</code>, sí, git-bash es superior a la terminal de NodeJS.

## Configuración

Para configurar es muy sencillo, hay varios modos de hacerlo, pero aquí te voy a enseñar la más sencilla a mi parecer.

Primero, debes teclear F1 y te saldrá los siguiente:

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1613777756139/wInHHlrmN.png)

En ese buscador solo debes poner <code>Open Settings(JSON)</code> y lo seleccionas. Luego te saldrá el siguiente archivo JSON.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1613777978477/ZV75xMA82.png)

Ahí debes buscar la línea que dice <code>terminal.integrated.shell.windows</code>. En esa línea debes colocar la dirección en donde se encuentra el archivo ejecutable de Bash. En mi caso es esa dirección que aparece allí. Esto puede cambiar dependiendo de dónde hayas instalado Git.

Algo a tener en cuenta es que para poner la dirección debes poner dos barras inclinadas para separar directorios, es decir <code>//</code>, ya que de otro modo te mostrará un error.

Finalmente, si abres la terminal de VS Code (<code>CTRL + Ñ</code>) ya te saldría por defecto git-bash, tal y como se ve a continuación:

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1613778278601/6nHp-qHlP.png)

Otra manera de conseguir esto es mediante <code>File</code> luego <code>Preferences</code>, seguido de <code>Settings</code>. Una vez allí hay que poner en el buscador la palabra <code>terminal</code> y buscamos la opción que dice <code>terminal > Integrated > Automation Shell: Windows</code>. Una vez allí haces *click* donde dice <code>edit in settings.json</code>

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1613778810573/U7Uqqm1Tb.png)

Luego se te abrirá el archivo JSON que vimos anteriormente y ahí es solo de seguir los pasos que indiqué más atrás.

___

Y bueno, eso es todo por este post, espero que les haya servido de algo. Nos leemos en una próxima.