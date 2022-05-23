## Cambiando el branch por defecto en Git (de master a main)

Tal vez llegué un poco tarde a este tema, pero he notado que hay pocos sitios web en español que indican cómo realizar el cambio de branch por defecto en Git. Así que acá va un mini tutorial para poder conseguirlo.

Como algunos sabrán, desde octubre pasado Github comenzó a cambiar el branch de los repositorios de <code>master</code> a <code>main</code>. De acuerdo al comunicado que brindó el sitio la decisión se tomó para ir erradicando algunos términos que podrían contener connotaciones negativas. 

El problema que algunos desarrolladores comenzaron a notar es que Git init tenía por defecto el Branch master, claro que se podría crear uno nuevo con el nombre <code>main</code> y listo, pero esto resulta ser algo tedioso suponiendo que se tendría que hacer la misma dinámica en cada proyecto.

Además, si hacías el push a Github sin realizar este cambio te subía el proyecto al branch master, pero si entrabas a tu repositorio veías que existían dos branch: master y main, este último porque como te venía diciendo, Github asignó a main como branch por defecto.

Pero bueno, explicaciones aparte, acá te muestro lo que debes de hacer para evitar estos conflictos, que aunque son pequeños, llegan a ser molestos con el tiempo.

## Requisitos previos

Para poder cambiar el branch por defecto desde Git necesitas tener al menos la versión <code>2.28</code> instalada. Esto porque en esta versión ya se agregaron características que permiten este cambio directamente desde la terminal. Además, si estás por instalar <code>Git</code> en Windows en alguna de las ventanas de instalación te preguntará el nombre del branch que vas a utilizar por defecto, ya en este caso podrías obviar el siguiente comando.

## Comando

El siguiente comando te permitirá asignar el nombre *main* como branch por defecto. 

<code>git config --global init.defaultBranch main</code>


___

Y bueno, eso es todo lo que hay que realizar, no es nada complicado, pero te libra de algunos dolores de cabeza.

Nos leemos en una próxima.
