## Haz la pregunta

Vamos a pedir al jugador que nombre la bandera para un país en particular.

--- task ---

En el objeto bandera, de inmediato abajo del bloque que clona banderas, agregar: `enviar mensaje`{:class="block3events"} y «anunciar país».

![Objeto bandera](images/flag-sprite.png)

```blocks3
when green flag clicked
crear lista de banderas :: custom
delete (all v) of [banderas elegidas v]
repeat (6)
    elegir bandera al azar :: custom
end
set [respuesta correcta v] to (item (pick random (1) to (length of [banderas elegidas v])) of [banderas elegidas v])
clonar banderas :: custom
+ broadcast (anunciar país v)
```

[[[generic-scratch3-broadcast-message]]]

--- /task ---

--- task ---

Añade un nuevo objeto a tu elección para sea el experto/a en banderas. En este ejemplo la experta es el objeto que se llama Abby.

![Objeto Abby](images/bear-sprite.png)

--- /task ---

--- task ---

Añade algún código al objeto experto/a en banderas, entonces, cuando el objeto reciba el mensaje `anunciar país`{:class="block3events"}, le dirá al jugador que haga clic en el nombre del país, el que está registrado en la variable `respuesta correcta`{:class="block3variables"}.

![Objeto del personaje](images/char-sprite.png)

--- hints ---
 --- hint ---

`Cuando recibo`{:class="block3events"} el mensaje, `decir`{:class="block3looks"} «haz clic en `respuesta correcta`{:class="block3variables"}».

--- /hint ---

--- hint ---

Aquí están los bloques de código que necesitas:

```blocks3
(join [haz clic en] [])

(respuesta correcta)

say [] for (2) seconds

when I receive [anunciar país v]
```

--- /hint ---

--- hint ---

Así es como se debería ver tu código:

```blocks3
when I receive [anunciar país v]
say (join [haz clic en] (respuesta correcta :: variables)) for (2) seconds
```

--- /hint ---

--- /hints --- --- /task ---