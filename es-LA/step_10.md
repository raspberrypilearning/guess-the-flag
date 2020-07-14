## Comienza una nueva ronda

Por el momento solo hay una ronda en el cuestionario, por lo que el cuestionario no dura mucho. Vas a configurar múltiples rondas.

\--- task \---

Crea un `mensaje`{:class="block3control"} que diga «comenzar la ronda».

![Objeto bandera](images/flag-sprite.png)

```blocks3
enviar (comenzar la ronda v)
```

\--- /task \---

\--- task \---

Añade el bloque `al recibir «comenzar la ronda»`{:class="block3events"} y luego mueve todo el código debajo del bloque `al presionar la bandera verde`{:class="block3events"} y agregalo abajo de este nuevo bloque.

![Objeto bandera](images/flag-sprite.png)

```blocks3
+ al presionar bandera verde
establecer [puntuación v] en [0]
crear lista de banderas :: custom
eliminar (todas v) de [banderas elegidas v]
repetir (6)
  elegir bandera al azar :: custom
fin
establecer [respuesta correcta v] en (elemento (número al azar entre (1) y (longitud de [banderas elegidas v]) ) de [banderas elegidas v])
clonar banderas :: custom
+ enviar (anunciar país v)
```

\--- /task \---

\--- task \---

Quita el bloque `fijar la puntuación a 0`{:class="block3variables"} y colócalo de nuevo abajo del bloque `al hacer clic en la bandera verde`{:class="block3control"}. Ahora añade el nuevo bloque `enviar`{:class="block3events"} debajo de ambos.

![Objeto bandera](images/flag-sprite.png)

```blocks3
al hacer clic en la bandera verde
establecer [puntuación v] en [0]
enviar (comenzar la ronda v)
```

\--- /task \---

\--- task \---

Después del código que comprueba si la respuesta está correcta, añade otro bloque `enviar`{:class="block3events"} para que comience una nueva ronda después de que se responda la pregunta.

![Objeto bandera](images/flag-sprite.png)

```blocks3
when this sprite clicked
if <(costume [name v]) = (correct answer :: variables)> then
    change [score v] by [1]
    say [Correct] for (2) seconds
else
    say [Sorry, that was wrong] for (2) seconds
end
+ broadcast (start the round v)
```

\--- /task \---

\--- task \---

Haz clic en la bandera verde para probar tu código. Haz clic en una de las banderas para jugar la ronda. ¿Te das cuenta que la siguiente ronda no se configura de manera correcta?

![La siguiente ronda no funciona](images/next-round-does-not-work.png)

\--- /task \---

Esto se debe a que antes que el juego comience otra ronda, el juego primero tiene que limpiar las banderas clonadas.

\--- task \---

Crea otro `enviar`{:class="block3events"} que se llame «limpiar».

![Objeto bandera](images/flag-sprite.png)

```blocks3
enviar (limpiar v)
```

\--- /task \---

\--- task \---

Establece la bandera en `eliminar este clon`{:class="block3control"} cuando reciba el mensaje `limpiar`{:class="block3events"}.

![Objeto bandera](images/flag-sprite.png)

```blocks3
al recibir [limpiar v]
eliminar este clon
```

\--- /task \---

\--- task \---

Coloca el bloque enviar `limpiar`{:class="block3events"} justo sobre el bloque comenzar una nueva ronda, después de obtener respuesta.

```blocks3
al presionar este objeto
crear lista de banderas :: custom
si <(elemento (disfraz [nombre v]) de [banderas v]) = (respuesta correcta :: variables)> then
    decir [Correct] por (2) segundos
    cambiar [puntuación v] en [1]
sino
    decir [Lo siento, respuesta equivocada] por (2) segundos
fin
+ enviar (limpiar v)
enviar (comenzar la ronda v)
```

\--- /task \---

\--- task \---

Prueba tu código de nuevo y comprueba si funciona el juego en varias rondas, y que la puntuación aumenta a medida que obtienes respuestas correctas.

\--- /task \---

\--- task \---

¡Asegúrate de ocultar la variable `respuesta correcta`{:class="block3variables"} para que el jugador no pueda verla!

\--- /task \---