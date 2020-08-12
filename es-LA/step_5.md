## Elige la respuesta correcta

Ahora que tienes la lista con seis banderas seleccionadas, elije la que ahora será la respuesta correcta.

--- task ---

Crea una nueva variable que se llame `respuesta correcta`{:class="block3variables"}.

--- /task ---

--- task ---

Después de elegir las seis banderas, fija la variable `respuesta correcta`{:class="block3variables"} para ser un elemento aleatorio de la lista `banderas elegidas`{:class="block3variables"}.

![Objeto bandera](images/flag-sprite.png)

```blocks3
when green flag clicked
crear lista de banderas :: custom
delete (all v) of [banderas elegidas v]
repeat (6)
    banderas elegidas :: custom
end
+ set [respuesta correcta v] to (item (pick random (1) to (length of [banderas elegidas v]) ) of [banderas elegidas v])
```

--- /task ---