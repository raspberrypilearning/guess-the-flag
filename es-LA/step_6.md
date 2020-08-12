## Muestra las banderas

La persona que toma el cuestionario necesita ver las fotos de las banderas en la lista `banderas elegidas`{:class="block3variables"}.

--- task ---

Crea otro bloque personalizado, y dale el nombre de `clonar banderas`{:class="block3myblocks"}.

![Objeto bandera](images/flag-sprite.png)

```blocks3
define clonar banderas
```

--- /task ---

Este bloque personalizado clonará seis veces el objeto Bandera, una vez por cada bandera que se debe mostrar.

La primera bandera se debe mostrar en la esquina superior izquierda del escenario.

--- task ---

Como parte de las instrucciones para el bloque `clonar banderas`{:class="block3myblocks"}, haz visible la bandera, y añade el bloque `ir a`{:class="block3motion"} para decirle al objeto que aparezca en las coordenadas `-170`{:class="block3motion"}, `120`{:class="block3motion"} en la esquina superior izquierda del escenario.

![Objeto bandera](images/flag-sprite.png)

```blocks3
define clonar banderas
show
go to x: (-170) y: (120)
```

--- /task ---

--- task ---

Debajo de ese código, añade un bucle que se repita seis veces.

![Objeto bandera](images/flag-sprite.png)

Dentro del bucle, añade bloques de código para cambiar el disfraz del objeto a la primera bandera de la lista `banderas elegidas`{:class="block3variables"} y clona el objeto. Luego, añade bloques de código para eliminar la primera bandera de la lista, y para mover el objeto a la posición de la segunda bandera, escribe `110`{:class="block3motion"} en la coordenada `x`{:class="block3motion"}.

--- hints ---
 --- hint ---

`Repetir`{:class="block3control"} seis veces: `Cambiar disfraz`{:class="block3looks"} al `primer objeto de las banderas elegidas`{:class="block3variables"}. `Clona el objeto`{:class="block3control"}. `Eliminar`{:class="block3variables"} el `primer elemento de las banderas elegidas`{:class="block3variables"}. `Mover a la derecha en 110`{:class="block3motion"}.

--- /hint ---

--- hint ---

Aquí están los bloques de código que necesitas añadir:

```blocks3
(item (1) of [banderas elegidas v])

change x by (110)

create clone of (myself v)

switch costume to ( v)

delete (1) of [banderas elegidas v]

repeat (6)
end
```

--- /hint ---

--- hint ---

Así es como se debería ver tu código:

```blocks3
define clonar banderas
show
go to x: (-170) y: (120)
+ repeat (6)
    switch costume to (item (1) of [banderas elegidas v])
    create clone of (myself v)
    delete (1) of [banderas elegidas v]
    change x by (110)
end
```

--- /hint ---

--- /hints --- --- /task ---

--- task ---

Añade el bloque `clonar banderas`{:class="block3myblocks"} al final del código que se ejecuta al hacer clic en la bandera verde.

![Objeto bandera](images/flag-sprite.png)

```blocks3
when green flag clicked
crear lista de banderas :: custom
delete (all v) of [banderas elegidas v]
repeat (6)
  elegir bandera al azar :: custom
end
+ clonar banderas :: custom
```

--- /task ---

--- task ---

Prueba tu código. Observa que aparecen distintas banderas, pero algunas están cortadas por el borde del escenario.

![Las banderas salen de la pantalla](images/flags-off-the-screen.png)

--- /task ---

Crea dos filas de tres banderas en lugar de poner las seis banderas en una fila.

--- task ---

Añade algo de código dentro del bucle `repetir`{:class="block3control"} de `clonar banderas`{:class="block3myblocks"} para mover el objeto Bandera hacia abajo si quedan tres banderas en la lista `banderas elegidas`{:class="block3variables"}.

![Objeto bandera](images/flag-sprite.png)

Es posible mover el objeto una fila hacia abajo al usar otro bloque `ir a`{:class="block3motion"} y mantener la coordenada `x`{:class="block3motion"} igual que el punto de partida, pero debes disminuir la coordenada `y`{:class="block3motion"} para que se mueva hacia abajo.

```blocks3
define clonar banderas
show
go to x: (-170) y: (120)
repeat (6)
    switch costume to (item (1) of [banderas elegidas v])
    create clone of (myself v)
    delete (1) of [banderas elegidas v]
    change x by (110)
+   if <(length of [banderas elegidas v]) = [3]> then
        go to x: (-170) y: (50)
    end
end
```

--- /task ---

--- task ---

Haz clic en la bandera verde y comprueba que las banderas se ven en las dos filas.

--- /task ---

Al parecer la última bandera se muestra dos veces. Esto se debe a que la bandera original todavía está visible en el final.

--- task ---

Añade un bloque `ocultar`{:class="block3looks"} al final del código dentro del bloque `clonar banderas`{:class="block3myblocks"} para ocultar el objeto original.

![Objeto bandera](images/flag-sprite.png)

--- /task ---

Si gustas, puedes intentar que los objetos de la bandera aparezcan uno por uno o que se reproduzca un sonido (un pop, por ejemplo) cada vez que aparece una bandera.