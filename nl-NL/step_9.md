## Een score toevoegen

--- task ---

Maak een nieuwe variabele met de naam `score`{:class="block3variables"} en stel de score in op `0`{:class="block3variables"} wanneer op de groene vlag wordt geklikt.

![Vlag sprite](images/flag-sprite.png)

```blocks3
when flag clicked
+ maak [score v] [0]
```

--- /task ---

--- task ---

Tel telkens `1`{:class="block3variables"} op bij de score wanneer de speler een goed antwoord geeft.

![Vlag sprite](images/flag-sprite.png)

```blocks3
wanneer op deze sprite wordt geklikt
als <(uiterlijk [naam v]) = (goed antwoord :: variables)> dan
+ verander [score v] met [1]
    zeg [Goed!] (2) sec.
anders
    zeg [Sorry, dat was niet goed] (2) sec.
einde
```

--- /task ---