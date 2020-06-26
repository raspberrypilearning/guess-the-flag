## Elige banderas al azar

Para cada ronda del cuestionario, elige al azar seis banderas de la lista `banderas`{:class="block3variables"} para que sean las opciones.

\--- task \---

Crea una nueva lista llamada `banderas elegidas`{:class="block3variables"}. Esta lista almacenará las seis banderas elegidas al azar.

\--- /task \---

\--- task \---

Crea una variable llamada `número de bandera`{:class="block3variables"}.

\--- /task \---

\--- task \---

Crea un bloque personalizado y llámalo `elige una bandera al azar`{:class="block3myblocks"}.

![Flag sprite](images/flag-sprite.png)

```blocks3
definir elegir bandera al azar
```

\--- /task \---

\--- task \---

Añade código al bloque personalizado para establecer a la variable `número de bandera`{:class="block3variables"} números al azar entre el `1` y la cantidad de elementos de la lista `banderas`{:class="block3variables"}.

![Flag sprite](images/flag-sprite.png)

Hay un bloque especial en la pestaña Variables para encontrar el número de elementos en una lista.

\--- hints \--- \--- hint \---

Establece la variable `número de bandera`{:class="block3variables"} a un `número al azar`{:class="block3operators"} entre `1` y la `longitud de la lista de «banderas»`{:class="block3variables"}.

\--- /hint \---

\--- hint \---

Aquí están los bloques de código que necesitas:

```blocks3
(longitud de [banderas v])

(elegir número al azar entre (1) y (10))

definir elegir bandera al azar

establecer [número de bandera v] en []
```

\--- /hint \---

\--- hint \---

Así quedaría tu código:

```blocks3
definir elegir bandera al azar
establecer [número de v] a (elegir número al azar (1) a (longitud de [banderas v]))
```

\--- /hint \---

\--- /hints \--- \--- /task \---

Ese bloque elige a un elemento de la lista a través de un número:

```blocks3
(elemento (10 v) de [banderas v])
```

\--- task \---

Combina este bloque con la variable `número de bandera`{:class="block3variables"} para conseguir el texto del elemento de la lista de `banderas`{:class="block3variables"} que se eligió al azar. Luego añade el elemento de texto a la lista `banderas`{:class="block3variables"}. Añade este código a tu bloque personalizado:

![Flag sprite](images/flag-sprite.png)

```blocks3
definir elegir bandera al azar
establecer [número de v] a (elegir número al azar (1) a (longitud de [banderas v]))
+ añadir (elemento (número bandera) de [banderas v]) a [banderas elegidas v]
```

\--- /task \---

\--- task \---

Añade el bloque personalizado `eligir bandera al azar`{:class="block3myblocks"} al código que se ejecuta después de hacer clic en la bandera verde.

![Flag sprite](images/flag-sprite.png)

```blocks3
al presionar bandera verde
crear lista de banderas :: custom
+ elegir banderas al azar :: custom
```

\--- /task \---

\--- task \---

Prueba si funciona tu código al presionar varias veces en la bandera verde y comprueba que cada vez aparecen distintos países en la lista de `banderas`{:class="block3variables"}. (Si ocultas la lista, marca la casilla que está junto al nombre de la lista para que la lista se vea).

\--- /task \---

¿Notas que al presionar muchas veces en la bandera verde, tu lista de `banderas elegidas`{:class="block3variables"} se llena más rápido con más de seis objetos?

\--- task \---

Antes de elegir seis banderas para el cuestionario, añade bloques para eliminar todos los elementos de la lista `banderas elegidas`{:class="block3variables"}.

![Flag sprite](images/flag-sprite.png)

```blocks3
al presionar bandera verde
crear lista de banderas :: custom
+ eliminar (todos v) de [banderas elegidas v]
+ repetir (6)
    elegir banderas al azar :: custom
fin
```

\--- /task \---

\--- task \---

Test your code again by clicking the green flag several times and checking that the `chosen flags` list is filled with six countries each time.

\--- /task \---

Notarás que a veces se añade más de una vez el mismo país a la lista.

![Duplicate countries](images/duplicate-countries.png)

\--- task \---

Cambia tu bloque `eligir una bandera al azar`{:class="block3myblocks"} para que nunca se agregue el mismo país más de dos veces a la lista `banderas elegidas`{:class="block3variables"}.

Add a block to the end of your custom block code to delete the `flag number`{:class="block3variables"} from the `flags`{:class="block3variables"} list after it has been added to the `chosen flags`{:class="block3variables"} list.

![Flag sprite](images/flag-sprite.png)

```blocks3
define choose random flag
set [flag number v] to (pick random (1) to (length of [flags v]))
add (item (flag number) of [flags v]) to [chosen flags v]
+ delete (flag number) of [flags v]
```

\--- /task \---

If you want to hide the lists and variables so that they don't take up space on the Stage, go to the Data section and unselect the boxes next to the list names or variable names. If you want to show the lists and variables again, just select the boxes.