## Überprüfe die Antwort

Deine Figur bittet nun den Spieler, auf die richtige Flagge zu klicken. Dann muss das Spiel prüfen, ob die angeklickte Flagge die richtige Antwort ist.

--- task ---

Gehe zurück zum Figur-Code und füge dann einen Block hinzu, um einen neuen Abschnitt des Codes zu starten, der ausgeführt wird `wenn diese Figur angeklickt wird`{:class="block3events"}.

![Flaggenfigur](images/flag-sprite.png)

--- /task ---

Dann muss dein Quiz überprüfen, ob der Kostümname der angeklickten Flaggenfigur mit der richtigen Antwort übereinstimmt.

--- task ---

Füge Code hinzu, um 'Korrekt' zu sagen, wenn der Kostümname der Flagge die gleiche ist wie die `richtige Antwort`{:class="block3variables"} Variable, oder "Entschuldigung, aber das ist falsch" zu sagen, wenn der Name und die Variable nicht identisch sind.

Du kannst diesen nützlichen Block auch hier verwenden.

```blocks3
(item (10 v) of [Flaggen v])
```

Kombiniere es diesmal mit einem `Kostümnamen`{:class="block3looks"} Block, um den Namen des aktuellen Flaggenfigur-Kostüms abzurufen.

![Flaggenfigur](images/flag-sprite.png)

--- hints ---
 --- hint ---

`Wenn auf diese Figur geklickt wird`{:class="block3events"}, `falls`{:class="block3control"} dieser `Kostümname`{:class="block3looks"} gleich de `richtige Antwort`{:class="block3variables"} ist, `sage`{:class="block3looks"} 'Korrekt' oder `ansonsten`{:class="block3control"} `sage`{:class="block3looks"} 'Entschuldigung, aber das ist falsch'.

--- /hint ---

--- hint ---

Hier sind die Codeblöcke die du brauchst:

```blocks3
say [Entschuldigung, aber das ist falsch] for (2) seconds

say [Korrekt] for (2) seconds

if <> then
else
end

(costume [name v])

<[] = []>

(richtige Antwort)

when this sprite clicked
```

--- /hint ---

--- hint ---

So sollte dein Code aussehen:

```blocks3
when this sprite clicked
if <(costume [name v]) = (richtige Antwort :: variables)> then
    say [Korrekt] for (2) seconds
else
    say [Entschuldigung, aber das ist falsch] for (2) seconds
end
```

--- /hint ---

--- /hints --- --- /task ---

--- task ---

Klicke auf grüne Flagge und teste deinen Code zweimal: einmal durch Auswahl der richtigen Flagge und einmal durch Auswahl einer Falschen. Überprüfe, ob die richtige Nachricht angezeigt wird, je nachdem, ob du die richtige oder die falsche Antwort angibst.

![Klicke auf die Flagge](images/click-on-flag.png)

--- /task ---