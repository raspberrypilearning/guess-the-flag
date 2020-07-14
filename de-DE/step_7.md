## Stelle eine Frage

Frage den Spieler nun, die Flagge für ein bestimmtes Land zu benennen.

--- task ---

In der Fahnenfigur, `sende die Nachricht`{:class="block3events"} 'Land ankündigen' direkt nach dem Block, der die Flaggen klont.

![Flaggenfigur](images/flag-sprite.png)

```blocks3
when green flag clicked
erstelle Flaggen-Liste :: custom
delete (all v) of [ausgewählte Flaggen v]
repeat (6)
    wähle zufällige Flagge :: custom
end
set [richtige Antwort v] to (item (pick random (1) to (length of [ausgewählte Flaggen v])) of [ausgewählte Flaggen v])
clone flags :: custom
+ broadcast (Land ankündigen v)

```

[[[generic-scratch3-broadcast-message]]]

--- /task ---

--- task ---

Füge eine neue Figur deiner Wahl hinzu, damit sie dein Quizmaster wird. Der Quizmaster im Beispiel ist die Figur namens Abby.

![Abby Figur](images/bear-sprite.png)

--- /task ---

--- task ---

Füge der Quiz-Master-Figur etwas Code hinzu. Sobald die Figur damit die Figur die `Land ankündigen`{:class="block3events"} Nachricht erhält, soll sie dem Spieler sagen, dass er auf den Ländernamen klicken soll der in der Variablen `richtige Antwort`{:class="block3variables"} gespeichert ist.

![Charakter Figur](images/char-sprite.png)

--- hints ---
 --- hint ---

`Wenn ich die Nachricht erhalte`{:class="block3events"}, `sage`{:class="block3looks"} 'klicke auf `richtige Antwort`{:class="block3variables"}'.

--- /hint ---

--- hint ---

Hier sind die Codeblöcke die du brauchst:

```blocks3
(join [klicke auf] [])

(richtige Antwort)

say [] for (2) seconds

when I receive [Land ankündigen v]
```

--- /hint ---

--- hint ---

So sollte dein Code aussehen:

```blocks3
when I receive [Land ankündigen v]
say (join [klicke auf] (richtige Antwort :: variables)) for (2) seconds
```

--- /hint ---

--- /hints --- --- /task ---