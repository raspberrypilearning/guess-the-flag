## Wähle eine richtige Antwort aus

Nachdem du nun eine Liste mit sechs ausgewählten Flags hast, wähle aus, welche davon diesmal die richtige Antwort sein soll.

--- task ---

Erstelle eine neue Variable mit dem Namen `richtige Antwort`{:class="block3variables"}.

--- /task ---

--- task ---

Nachdem die sechs Flaggen ausgewählt wurden, setze die `richtige Antwort`{:class="block3variables"} Variable auf ein zufälliges Element aus der `ausgewählte Flaggen`{:class="block3variables"} Liste.

![Flaggenfigur](images/flag-sprite.png)

```blocks3
when green flag clicked
erstelle eine Flaggenliste :: custom
delete (all v) of [ausgewählte Flaggen v]
repeat (6)
    wähle zufällige Flagge :: custom
end
+ set [richtige Antwort v] to (item (pick random (1) to (length of [ausgewählte Flaggen v]) ) of [ausgewählte Flaggen v])
```

--- /task ---