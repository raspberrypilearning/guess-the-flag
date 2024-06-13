## Kies een correct antwoord

Nu je een lijst hebt met zes gekozen vlaggen, kies je deze keer het juiste antwoord.

--- task ---

Maak een nieuwe variabele met de naam `goed antwoord`{:class="block3variables"}.

--- /task ---

--- task ---

Nadat de zes vlaggen zijn gekozen, stel je de variabele `goed antwoord`{:class="block3variables"} in op een willekeurig item uit de `gekozen vlaggen`{:class="block3variables"} lijst.

![Vlag sprite](images/flag-sprite.png)

```blocks3
when flag clicked
maak vlaggenlijst :: custom
delete (alle v) of [gekozen vlaggen v]
repeat (6)
    kies willekeurige vlag :: custom
end
+ set [goed antwoord v] to (item (pick random (1) to (length of [gekozen vlaggen v]) ) of [gekozen vlaggen v])
```

--- /task ---