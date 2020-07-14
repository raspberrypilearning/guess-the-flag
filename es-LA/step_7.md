## Haz la pregunta

Vamos a pedir al jugador que nombre la bandera para un país en particular.

\--- task \---

En el objeto bandera, de inmediato abajo del bloque que clona banderas, agregar: `enviar mensaje`{:class="block3events"} y «anunciar país».

![Objeto bandera](images/flag-sprite.png)

```blocks3
al presionar bandera verde
crear lista de banderas :: custom
eliminar (todas v) de [banderas elegidas v]
repetir (6)
  elegir bandera al azar :: custom
fin
establecer [respuesta correcta v] en (elemento (número al azar entre (1) y (longitud de [banderas elegidas v]) ) de [banderas elegidas v])
clonar banderas :: custom
+ enviar (anunciar país v)

```

[[[generic-scratch3-broadcast-message]]]

\--- /task \---

\--- task \---

Añade un nuevo objeto a tu elección para sea el experto/a en banderas. En este ejemplo la experta es el objeto que se llama Abby.

![Objeto Abby](images/bear-sprite.png)

\--- /task \---

\--- task \---

Añade algún código al objeto experto/a en banderas, entonces, cuando el objeto reciba el mensaje `anunciar país`{:class="block3events"}, le dirá al jugador que haga clic en el nombre del país, el que está registrado en la variable `respuesta correcta`{:class="block3variables"}.

![Objeto del personaje](images/char-sprite.png)

\--- hints \--- \--- hint \---

`Cuando recibo`{:class="block3events"} el mensaje, `decir`{:class="block3looks"} «haz clic en `respuesta correcta`{:class="block3variables"}».

\--- /hint \---

\--- hint \---

Aquí están los bloques de código que necesitas:

```blocks3
(unir [hacer clic] [])

(respuesta correcta)

decir [] por (2) segundos

cuando recibo [anunciar país v]
```

\--- /hint \---

\--- hint \---

Así es como se debería ver tu código:

```blocks3
al recibir [anunciar país v]
decir (unir [hacer clic] (respuesta correcta :: variables)) por (2) segundos
```

\--- /hint \---

\--- /hints \--- \--- /task \---