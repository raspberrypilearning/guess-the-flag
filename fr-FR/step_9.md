## Ajouter un score

\--- task \---

Crée une nouvelle variable appelée `score`{:class="block3variables"} et mets le score à `0`{:class="block3variables"} quand le drapeau vert est cliqué.

![Sprite drapeau](images/flag-sprite.png)

```blocks3
when green flag clicked
+ set [score v] to [0]
```

\--- /task \---

\--- task \---

Ajoute `1`{:class="block3variables"} au score chaque fois que le joueur donne une réponse correcte.

![Sprite drapeau](images/flag-sprite.png)

```blocks3
when this sprite clicked
if <(costume [name v]) = (correct answer :: variables)> then
+ change [score v] by [1]
    say [Correct] for (2) seconds
else
    say [Sorry, that was wrong] for (2) seconds
end
```

\--- /task \---