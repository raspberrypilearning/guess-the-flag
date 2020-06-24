## Crea una lista de banderas

\--- task \---

Haz clic en la pestaña de Código. Hay una lista llamada `banderas`{:class="block3variables"}, en donde guardas los nombres de los países y que además tu juego tiene disfraces para cada uno de ellos.

\--- /task \---

\--- task \---

Añade dos bloques más de código, uno por cada una de las banderas que creaste, así que hay un total de diez bloques que suman un total de diez países en la lista `banderas`{:class="block3variables"}.

![Objeto bandera](images/flag-sprite.png)

```blocks3
add [Country] to [flags v]
```

\--- /task \---

\--- task \---

Haz clic en la bandera verde y comprueba que los países aparezcan en la lista.

\--- /tarea \---

Si presionas la bandera verde más de una vez, los países se vuelven a añadir a la lista y el resultado será una lista de 20 países en lugar de 10.

\--- task \---

Al inicio del código, añade un bloque para `eliminar todos`{:class="block3variables"} los países de la lista antes de añadirlos. Esto impedirá que los países se añadan a la lista más de una vez.

![Objeto bandera](images/flag-sprite.png)

```blocks3
Al presionar la bandera verde
+ eliminar (todas v) las [banderas v]
agregar [Japan] a [banderas v]
agregar [Belgium] a [banderas v]
agregar [Italy] a [banderas v]
agregar [Turkey] a [banderas v]
agregar [Denmark] a [banderas v]
agregar [Chile] a [banderas v]
agregar [Botswana] a [banderas v]
agregar [Bangladesh] a [banderas v]
agregar [Ghana] a [banderas v]
agregar [Luxembourg] a [banderas v]
```

\--- /task \---

A continuación, crea un bloque personalizado. Un bloque personalizado es un bloque especial con un nombre. El bloque personalizado que crearás te permitirá crear una lista de banderas para usar solo este bloque en lugar de un montón de bloques.

\--- task \---

Haz clic en **Mis bloques** y luego haz clic en **Crear un bloque**. Dale el nombre de `crear lista de banderas`{:class="block3myblocks"} a tu bloque personalizado.

![Objeto bandera](images/flag-sprite.png)

![Añadir un bloque](images/add-block.png)

\--- /task \---

\--- task \---

Aparta todo el código que está abajo del bloque `al presionar la bandera`{:class="block3events"} abajo del nuevo bloque `crear lista de banderas`{:class="block3myblocks"}.

```blocks3
definir crear lista de banderas
eliminar (todas v) las [banderas v]
agregar [Japan] a [banderas v]
agregar [Belgium] a [banderas v]
agregar [Italy] a [banderas v]
agregar [Turkey] a [banderas v]
agregar [Denmark] a [banderas v]
agregar [Chile] a [banderas v]
agregar [Botswana] a [banderas v]
agregar [Bangladesh] a [banderas v]
agregar [Ghana] a [banderas v]
agregar [Luxembourg] a [banderas v]
```

\--- /task \---

\--- task \---

Abajo del bloque `al presionar la bandera`{:class="block3events"}, añade el nuevo bloque `crear lista de banderas`{:class="block3myblocks"}.

![Objeto bandera](images/flag-sprite.png)

```blocks3
al presionar en la bandera verde
crear lista de banderas :: custom
```

\--- / tarea \---