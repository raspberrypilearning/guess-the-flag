## Elige banderas al azar

Para cada ronda del cuestionario, elige al azar seis banderas de la lista `banderas`{:class="block3variables"} para que sean las opciones.

--- task ---

Crea una nueva lista llamada `banderas elegidas`{:class="block3variables"}. Esta lista almacenará las seis banderas elegidas al azar.

--- /task ---

--- task ---

Crea una variable llamada `número de bandera`{:class="block3variables"}.

--- /task ---

--- task ---

Crea un bloque personalizado y llámalo `elegir bandera al azar`{:class="block3myblocks"}.

![Objeto bandera](images/flag-sprite.png)

```blocks3
define elegir bandera al azar
```

--- /task ---

--- task ---

Añade código al bloque personalizado para establecer a la variable `número de bandera`{:class="block3variables"} números al azar entre el `1` y la cantidad de elementos de la lista `banderas`{:class="block3variables"}.

![Objeto bandera](images/flag-sprite.png)

Hay un bloque especial en la pestaña Variables para encontrar el número de elementos en una lista.

--- hints ---
 --- hint ---

Establece la variable `número de bandera`{:class="block3variables"} a un `número al azar`{:class="block3operators"} entre `1` y la `longitud de la lista de «banderas»`{:class="block3variables"}.

--- /hint ---

--- hint ---

Aquí están los bloques de código que necesitas:

```blocks3
(length of [banderas v])

(pick random (1) to (10))

define choose random flag

set [número de bandera v] to []
```

--- /hint ---

--- hint ---

Así quedaría tu código:

```blocks3
define elegir bandera al azar
set [número de bandera v] to (pick random (1) to (length of [banderas v]))
```

--- /hint ---

--- /hints --- --- /task ---

Ese bloque elige a un elemento de la lista a través de un número:

```blocks3
(item (10 v) of [banderas v])
```

--- task ---

Combina este bloque con la variable `número de bandera`{:class="block3variables"} para conseguir el texto del elemento de la lista de `banderas`{:class="block3variables"} que se eligió al azar. Luego añade el elemento de texto a la lista `banderas`{:class="block3variables"}. Añade este código a tu bloque personalizado:

![Objeto bandera](images/flag-sprite.png)

```blocks3
define elegir bandera al azar
set [número de bandera v] to (pick random (1) to (length of [banderas v]))
+ add (item (número de bandera) of [banderas v]) to [banderas elegidas v]
```

--- /task ---

--- task ---

Añade el bloque personalizado `eligir bandera al azar`{:class="block3myblocks"} al código que se ejecuta después de hacer clic en la bandera verde.

![Objeto bandera](images/flag-sprite.png)

```blocks3
when green flag clicked
crear lista de banderas :: custom
+ elegir bandera al azar :: custom
```

--- /task ---

--- task ---

Prueba si funciona tu código al presionar varias veces en la bandera verde y comprueba que cada vez aparecen distintos países en la lista de `banderas`{:class="block3variables"}. (Si ocultas la lista, marca la casilla que está junto al nombre de la lista para que la lista se vea).

--- /task ---

¿Notas que al presionar muchas veces en la bandera verde, tu lista de `banderas elegidas`{:class="block3variables"} se llena más rápido con más de seis objetos?

--- task ---

Antes de elegir seis banderas para el cuestionario, añade bloques para eliminar todos los elementos de la lista `banderas elegidas`{:class="block3variables"}.

![Objeto bandera](images/flag-sprite.png)

```blocks3
when green flag clicked
crear lista de banderas :: custom
+ delete (all v) of [banderas elegidas v]
+ repeat (6)
    elegir bandera al azar :: custom
end
```

--- /task ---

--- task ---

Prueba otra vez tu código, presiona varias veces en la bandera verde y comprueba que en la lista de `banderas` siempre se completen seis países.

--- /task ---

Notarás que a veces se añade más de una vez el mismo país a la lista.

![Países duplicados](images/duplicate-countries.png)

--- task ---

Cambia tu bloque `eligir una bandera al azar`{:class="block3myblocks"} para que nunca se agregue el mismo país más de dos veces a la lista `banderas elegidas`{:class="block3variables"}.

Añade un bloque al final del bloque personalizado, para eliminar el `número de bandera`{:class="block3variables"} de la lista de `banderas`{:class="block3variables"}, una vez que se haya añadido a la lista de `banderas elegidas`{:class="block3variables"}.

![Objeto bandera](images/flag-sprite.png)

```blocks3
define elegir bandera al azar
set [número de bandera v] to (pick random (1) to (length of [banderas v]))
add (item (número de bandera) of [banderas v]) to [banderas elegidas v]
+ delete (número de bandera) of [banderas v]
```

--- /task ---

Si quieres ocultar las listas y variables para que no ocupen espacio en el escenario, ve a la sección Datos y desactiva las casillas junto a la lista de nombres o nombres de variables. Si deseas mostrar otra vez las listas y variables, solo selecciona las casillas.