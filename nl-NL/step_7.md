## Stel de vraag

Laten we de speler vragen de vlag voor een bepaald land te noemen.

--- task ---

In de vlag sprite `zend signaal`{:class="block3events"} 'kondig land aan' direct na het blok dat de vlaggen kloont.

![Vlag sprite](images/flag-sprite.png)

```blocks3
when flag clicked
maak vlaggenlijst :: custom
delete (alle v) of [gekozen vlaggen v]
repeat (6)
    kies willekeurige vlag :: custom
end
set [goed antwoord v] to (item (pick random (1) to (length of [gekozen vlaggen v])) of [gekozen vlaggen v])
kloon vlaggen :: custom
+ broadcast (kondig land aan v)

```

[[[generic-scratch3-broadcast-message]]]

--- /task ---

--- task ---

Voeg een nieuwe sprite naar keuze toe als je quizmaster. De quizmaster in het voorbeeld is de sprite genaamd Abby.

![Abby sprite](images/bear-sprite.png)

--- /task ---

--- task ---

Voeg wat code toe aan de quizmaster sprite zodat, wanneer de sprite het signaal van `kondig land aan`{:class="block3events"} ontvangt, het de speler vertelt op de landnaam te klikken die is opgeslagen in de variabele `goed antwoord`{:class="block3variables"}.

![Personage-sprite](images/char-sprite.png)

--- hints ---
 --- hint ---

`Wanneer ik signaal`{:class="block3events"} ontvang, `zeg`{:class="block3looks"} 'klik op `goed antwoord`{:class="block3variables"}'.

--- /hint ---

--- hint ---

Dit zijn de codeblokken die je nodig hebt:

```blocks3
(join [klik op] [])

(goed antwoord)

say [] for (2) seconds

when I receive [kondig land aan v]
```

--- /hint ---

--- hint ---

Dit is hoe je code eruit zou moeten zien:

```blocks3
when I receive [kondig land aan v]
say (join [klik op] (goed antwoord :: variables)) for (2) seconds
```

--- /hint ---

--- /hints ---
--- /task ---