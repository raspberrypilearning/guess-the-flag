## Elige la respuesta correcta

Ahora que tienes la lista con seis banderas seleccionadas, elije la que ahora será la respuesta correcta.

\--- task \---

Crea una nueva variable que se llame `respuesta correcta`{:class="block3variables"}.

\--- /task \---

\--- task \---

Después de elegir las seis banderas, fija la variable `respuesta correcta`{:class="block3variables"} para ser un elemento aleatorio de la lista `banderas elegidas`{:class="block3variables"}.

![Objeto bandera](images/flag-sprite.png)

```blocks3
al presionar bandera verde
crear lista de banderas :: custom
eliminar (todos v) de [banderas elegidas v]
repetir (6)
    elegir banderas al azar :: custom
fin
+ establecer [respuesta correcta v] en (elemento (número al azar entre (1) y (longitud de [banderas elegidas v]) ) de [banderas elegidas v])
```

\--- /task \---