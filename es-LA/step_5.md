## Elige la respuesta correcta

Ahora que tienes la lista con seis banderas seleccionadas, elije la que ahora será la respuesta correcta.

\--- task \---

Crea una nueva variable que se llame `respuesta correcta`{:class="block3variables"}.

\--- /task \---

\--- task \---

Después de elegir las seis banderas, fija la variable `respuesta correcta`{:class="block3variables"} para ser un elemento aleatorio de la lista `banderas elegidas`{:class="block3variables"}.

![Flag sprite](images/flag-sprite.png)

```blocks3
when green flag clicked
create flag list :: custom
delete (all v) of [chosen flags v]
repeat (6)
    choose random flag :: custom
end
+ set [correct answer v] to (item (pick random (1) to (length of [chosen flags v]) ) of [chosen flags v])
```

\--- /task \---