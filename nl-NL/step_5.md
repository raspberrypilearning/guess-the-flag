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
verwijder (alle v) van [gekozen vlaggen v]
herhaal (6)
    kies willekeurige vlag :: custom
einde
+ maak [goed antwoord v] (item (willekeurig getal tussen (1) en (lengte van [gekozen vlaggen v]) ) van [gekozen vlaggen v])
```

--- /task ---