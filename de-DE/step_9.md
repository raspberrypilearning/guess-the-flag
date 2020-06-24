## Füge Punkte hinzu

\--- task \---

Erstelle eine neue Variable mit dem Namen `Punktestand`{:class="block3variables"} und setze die Punktzahl auf `0`{:class="block3variables"}, wenn auf die grüne Flagge geklickt wird.

![Flaggenfigur](images/flag-sprite.png)

```blocks3
when green flag clicked
+ set [score v] to [0]
```

\--- /task \---

\--- task \---

Füge `1`{:class="block3variables"} jedes Mal zum Punktestand hinzu, wenn der Spieler eine korrekte Antwort gibt.

![Flaggenfigur](images/flag-sprite.png)

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