## Stelle eine Frage

Frage den Spieler nun, die Flagge für ein bestimmtes Land zu benennen.

\--- task \---

In der Fahnenfigur, `sende die Nachricht`{:class="block3events"} 'Land verkünden' direkt nach dem Block, der die Flaggen klont.

![Flaggenfigur](images/flag-sprite.png)

```blocks3
when green flag clicked
create flag list :: custom
delete (all v) of [chosen flags v]
repeat (6)
    choose random flag :: custom
end
set [correct answer v] to (item (pick random (1) to (length of [chosen flags v])) of [chosen flags v])
clone flags :: custom
+ broadcast (announce country v)

```

[[[generic-scratch3-broadcast-message]]]

\--- /task \---

\--- task \---

Füge eine neue Figur deiner Wahl hinzu, damit sie dein Quizmaster wird. Der Quizmaster im Beispiel ist die Figur namens Abby.

![Abby Figur](images/bear-sprite.png)

\--- /task \---

\--- task \---

Füge der Quiz-Master-Figur etwas Code hinzu. Sobald die Figur damit die Figur die `Land verkünden`{:class="block3events"} Nachricht erhält, soll sie dem Spieler sagen, dass er auf den Ländernamen klicken soll der in der Variablen `richtige Antwort`{:class="block3variables"} gespeichert ist.

![Charakter Figur](images/char-sprite.png)

\--- hints \--- \--- hint \---

`Wenn ich die Nachricht erhalte`{:class="block3events"}, `sage`{:class="block3looks"} 'klicke auf `korrekte Antwort`{:class="block3variables"}'.

\--- /hint \---

\--- hint \---

Hier sind die Codeblöcke die du brauchst:

```blocks3
(join [click on] [])

(correct answer)

say [] for (2) seconds

when I receive [announce country v]
```

\--- /hint \---

\--- hint \---

So sollte dein Code aussehen:

```blocks3
when I receive [announce country v]
say (join [click on] (correct answer :: variables)) for (2) seconds
```

\--- /hint \---

\--- /hints \--- \--- /task \---