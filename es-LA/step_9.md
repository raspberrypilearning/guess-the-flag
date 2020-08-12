## Añade una puntuación

--- task ---

Crea una nueva variable que se llame `puntuación`{:class="block3variables"} y establece la puntuación a `0`{:class="block3variables"} al hacer clic en la bandera verde.

![Objeto bandera](images/flag-sprite.png)

```blocks3
when green flag clicked
+ set [puntuación v] to [0]
```

--- /task ---

--- task ---

Añade `1`{:class="block3variables"} a la puntuación cada vez que el jugador elige la respuesta correcta.

![Objeto bandera](images/flag-sprite.png)

```blocks3
when this sprite clicked
if <(costume [name v]) = (respuesta correcta :: variables)> then
+ change [puntuación v] by [1]
    say [Correcto] for (2) seconds
else
    say [Lo sentimos, no es la respuesta correcta] for (2) seconds
end
```

--- /task ---