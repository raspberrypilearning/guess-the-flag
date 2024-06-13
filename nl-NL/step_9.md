## Een score toevoegen

--- task ---

Maak een nieuwe variabele met de naam `score`{:class="block3variables"} en stel de score in op `0`{:class="block3variables"} wanneer op de groene vlag wordt geklikt.

![Vlag sprite](images/flag-sprite.png)

```blocks3
when green flag clicked
+ set [score v] to [0]
```

--- /task ---

--- task ---

Tel telkens `1`{:class="block3variables"} op bij de score wanneer de speler een goed antwoord geeft.

![Vlag sprite](images/flag-sprite.png)

```blocks3
when this sprite clicked
if <(costume [naam v]) = (goed antwoord :: variables)> then
+ change [score v] by [1]
    say [Goed!] for (2) seconds
else
    say [Sorry, dat was niet goed] for (2) seconds
end
```

--- /task ---