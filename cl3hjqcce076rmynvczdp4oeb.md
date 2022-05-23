## Mejorando el aspecto de Zsh

Luego de un largo tiempo he vuelto al blog. La verdad, no he tenido el tiempo que quisiera para escribir artículos y tutoriales, he estado ocupado con muchas cosas últimamente, pero saqué un espacio para escribir algo relacionado con la terminal, ya que llevo mucho tiempo utilizándola y estos últimos meses hice el cambio de Bash a Zsh (las razones las diré en otro artículo).

# ¿Qué es Zsh?
Para hacer el cuento corto, Zsh es una de varias shells que puedes usar en tu sistema operativo basado en Unix. Existen muchas shells además de Bash, como por ejemplo: Dash, Fish, Zsh, etc. En este caso, el tutorial va orientado a los que utilizan Linux, pues es el sistema que utilizo en mi día a día.

# ¿Qué es Oh my Zsh?
Cuando se trata de configurar y cambiar el aspecto  de Zsh, Oh My Zsh es la clave. Se trata de un framework de código abierto que te permite cambiar la configuración, funcionamiento y aspecto de Zsh. Oh My Zsh permite añadir temas, helpers y plugins de manera sencilla.

# ¿Qué es Powerlevel10k?
Powerlevel10k es un tema para Oh My Zsh que cuenta con varios estilos predefinidos, en los que el usuario puede hacer una combinación de varias configuraciones y conseguir un tema visualmente atractivo.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1653173460054/nmLChgual.png align="left")

# Instalación
Para poder realizar la instalación sin ningún inconveniente, es necesario cumplir con ciertos requisitos, los cuales menciono a continuación:
* Zsh 
* Git 
* Curl
* Fuentes Meslo. (Las pueden descargar ["acá"](https://icedrive.net/s/tWGGBD2V7yVFZgagZfRafWhN78aS))

## Instalación de  Oh My Zsh
En este punto ya deberían tener instalado todos los requerimientos del punto anterior. La terminal con Zsh debe tener el siguiente aspecto por defecto:

![zsh_raw.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1653174250345/FxvW36DKC.png align="left")

Así que, lo primero que hay que hacer es copiar y pegar el siguiente comando en la terminal:

```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
``` 
El comando descargará e instalará Oh My Zsh. Al final, nos debería aparecer en la terminal lo siguiente:

![zsh_oh_my_bash.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1653174199764/SXHE16A5a.png align="left")

La terminal cambió de aspecto, se ve mejor, pero se puede mejorar por mucho. Así que lo siguiente sería cambiar las fuentes de nuestra terminal.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1653174521914/ekmvG6uLv.png align="left")


Se debe seleccionar la fuente *MesloLGS NF Regular* y el tamaño que desees.

## Instalación de PowerLevel10k

Ahora corresponde el turno del framework para escoger nuestro tema. Para descargarlo e instalarlo, necesitamos copiar y pegar el siguiente comando en la terminal:


```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
``` 

En el siguiente paso debemos indicarle a Oh My Zsh que utilize el tema de PowerLevel10k. Para eso debemos editar el archivo <code>~/.zshrc</code>. En este archivo se encuentra toda la configuración de Zsh, por lo que debe editarse con sumo cuidado.

Nos posicionamos en la línea que dice **ZSH_THEME**, borramos lo que está entre comillas y colocamos lo siguiente:  <code>powerlevel10k/powerlevel10k</code>. Debería quedarnos algo similar a la siguiente imagen:


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1653175108157/P9b09ndnp.png align="left")

Guardamos los cambios y cerramos el archivo. En este punto ya deberíamos tener todo listo, solo quedaría cerrar y volver a iniciar la sesión de la terminal, pero para agilizar este paso, solo colocamos el siguiente comando en la terminal:


```
source ~./zshrc
``` 

> Ahora también podemos refrescar la configuración de Zsh con tan solo ejecutar el comando <code>exec zsh</code> 

Y listo, nos debería aparecer el menú de PowerLevel10K y seleccionamos todas las opciones que nos gusten.


![power10_menu.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1653175454642/lqCIx4cxO.png align="left")

En caso de no aparecer el menú, ejecutamos el siguiente comando para iniciarlo:

```
p10k configure
``` 


> IMPORTANTE: Para utilizar Zsh por defecto en nuestra terminal, debemos digitar lo siguiente: <code>chsh -s /bin/zsh</code>

## Resultado
En mi caso, las opciones que seleccioné dieron el siguiente resultado:


![Final_result.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1653175736052/j_jri-ghO.png align="left")

---
# Conclusiones

Oh My Zsh + PowerLevel10k son una buena combinación para mejorar el aspecto de nuestra terminal, pero no olvidemos que el poder de Zsh está en sus plugins. Por defecto Oh My Zsh viene con el plugin de Git instalado, que le da un aspecto bastante llamativo cuando trabajamos un repositorio con el control de versiones. Pero existen muchos plugin más para diferentes propósitos (tal vez en otra ocasión escribo un artículo sobre los plugins que utilizo).

Si desean ver la lista de plugins, pueden ingresar a [este enlace](https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins)

Nos leemos en una próxima.

