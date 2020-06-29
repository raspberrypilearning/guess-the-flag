## Muestra las banderas

La persona que toma el cuestionario necesita ver las fotos de las banderas en la lista `banderas elegidas`{:class="block3variables"}.

\--- task \---

Crea otro bloque personalizado, y dale el nombre de `clonar banderas`{:class="block3myblocks"}.

![Flag sprite](images/flag-sprite.png)

```blocks3
define clone flags
```

\--- /task \---

Este bloque personalizado clonará seis veces el objeto Bandera, una vez por cada bandera que se debe mostrar.

La primera bandera se debe mostrar en la esquina superior izquierda del escenario.

\--- task \---

Como parte de las instrucciones para el bloque `clonar banderas`{:class="block3myblocks"}, haz visible la bandera, y añade el bloque `ir a`{:class="block3motion"} para decirle al objeto que aparezca en las coordenadas `-170`{:class="block3motion"}, `120`{:class="block3motion"} en la esquina superior izquierda del escenario.

![Flag sprite](images/flag-sprite.png)

```blocks3
definir clonar banderas
mostrar
ir a x: (-170) y: (120)
```

\--- /task \---

\--- task \---

Debajo de ese código, añade un bucle que se repita seis veces.

![Flag sprite](images/flag-sprite.png)

Dentro del bucle, añade bloques de código para cambiar el disfraz del objeto a la primera bandera de la lista `banderas elegidas`{:class="block3variables"} y clona el objeto. Luego, añade bloques de código para eliminar la primera bandera de la lista, y para mover el objeto a la posición de la segunda bandera, escribe `110`{:class="block3motion"} en la coordenada `x`{:class="block3motion"}.

\--- hints \--- \--- hint \---

`Repetir`{:class="block3control"} seis veces: `Cambiar disfraz`{:class="block3looks"} al `primer objeto de las banderas elegidas`{:class="block3variables"}. `Clona el objeto`{:class="block3control"}. `Eliminar`{:class="block3variables"} el `primer elemento de las banderas elegidas`{:class="block3variables"}. `Mover a la derecha en 110`{:class="block3motion"}.

\--- /hint \---

\--- hint \---

Aquí están los bloques de código que necesitas añadir:

```blocks3
(elemento (1) de [banderas elegidas v])

cambiar x en (110)

crear clon de (mí mismo/a v)

cambiar disfraz a ( v)

eliminar (1) de [banderas elegidas v]

repetir (6)
fin
```

\--- /hint \---

\--- hint \---

Así es como se debería ver tu código:

```blocks3
definir clonar banderas
mostrar
ir a x: (-170) y: (120)
+ repetir (6)
    cambiar disfraz a (elemento (1) de [banderas elegidas v])
    crear clon de (mí mismo v)
    eliminar (1) de [banderas elegidas v]
    cambiar x en (110)
fin
```

\--- /hint \---

\--- /hints \--- \--- /task \---

\--- task \---

Añade el bloque `clonar banderas`{:class="block3myblocks"} al final del código que se ejecuta al hacer clic en la bandera verde.

![Flag sprite](images/flag-sprite.png)

```blocks3
al presionar bandera verde
crear lista de banderas :: custom
eliminar (todas v) de [banderas elegidas v]
repetir (6)
  elegir bandera al azar :: custom
fin
+ clonar banderas :: custom
```

\--- /task \---

\--- task \---

Prueba tu código. Observa que aparecen distintas banderas, pero algunas están cortadas por el borde del escenario.

![Flags go off the screen](images/flags-off-the-screen.png)

\--- /task \---

Crea dos filas de tres banderas en lugar de poner las seis banderas en una fila.

\--- task \---

Añade algo de código dentro del bucle `repetir`{:class="block3control"} de `clonar banderas`{:class="block3myblocks"} para mover el objeto Bandera hacia abajo si quedan tres banderas en la lista `banderas elegidas`{:class="block3variables"}.

![Flag sprite](images/flag-sprite.png)

You can the sprite move down a row by using another `go to`{:class="block3motion"} block and keeping the `x`{:class="block3motion"} coordinate the same as the starting point, but decreasing the `y`{:class="block3motion"} coordinate to move downwards.

```blocks3
define clone flags
show
go to x: (-170) y: (120)
repeat (6)
    switch costume to (item (1) of [chosen flags v])
    create clone of (myself v)
    delete (1) of [chosen flags v]
    change x by (110)
+   if <(length of [chosen flags v]) = [3]> then
        go to x: (-170) y: (50)
    end
end
```

\--- /task \---

\--- task \---

Click the green flag and check that the flags display in two rows.

\--- /task \---

It looks like the last flag is displayed twice. This is because the original Flag sprite is still visible at the end.

\--- task \---

Add a `hide`{:class="block3looks"} block at the end of the code inside the `clone flags`{:class="block3myblocks"} block to hide the original sprite.

![Flag sprite](images/flag-sprite.png)

\--- /task \---

If you want to, you can try making the flag sprites appear one by one or playing a sound (a pop, for example) each time a flag appears.