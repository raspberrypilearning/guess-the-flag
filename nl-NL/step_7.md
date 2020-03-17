## Stel de vraag

Laten we de speler vragen de vlag voor een bepaald land te noemen.

\--- task \---

In de vlag sprite `zend signaal`{:class="block3events"} 'kondig land aan' direct na het blok dat de vlaggen kloont.

![Vlag sprite](images/flag-sprite.png)

```blocks3
wanneer op de groene vlag wordt geklikt
maak vlaggenlijst :: custom
verwijder (alle v) van [gekozen vlaggen v]
herhaal (6)
    kies willekeurige vlag :: custom
einde
maak [goed antwoord v] (item (willekeurig getal tussen (1) en (lengte van [gekozen vlaggen v])) van [gekozen vlaggen v])
kloon vlaggen :: custom
+ zend signaal (kondig land aan v)

```

[[[generic-scratch3-broadcast-message]]]

\--- /task \---

\--- task \---

Voeg een nieuwe sprite naar keuze toe als je quizmaster. De quizmaster in het voorbeeld is de sprite genaamd Abby.

![Abby sprite](images/bear-sprite.png)

\--- /task \---

\--- task \---

Voeg wat code toe aan de quizmaster sprite zodat, wanneer de sprite het signaal van `kondig land aan`{:class="block3events"} ontvangt, het de speler vertelt op de landnaam te klikken die is opgeslagen in de variabele `goed antwoord`{:class="block3variables"}.

![Personage-sprite](images/char-sprite.png)

\--- hints \--- \--- hint \---

`Wanneer ik signaal`{:class="block3events"} ontvang, zeg ``{:class="block3looks"} 'klik op `goed antwoord`{:class="block3variables"}'.

\--- /hint \---

\--- hint \---

Dit zijn de codeblokken die je nodig hebt:

```blocks3
(voeg [klik op] en [] samen)

(goed antwoord)

zeg [] (2) sec.

wanneer ik signaal [kondig land aan v] ontvang
```

\--- /hint \---

\--- hint \---

Dit is hoe je code eruit zou moeten zien:

```blocks3
wanneer ik signaal [kondig land aan v] ontvang
zeg (voeg [klik op] en (goed antwoord :: variables) samen) (2) sec.
```

\--- /hint \---

\--- /hints \--- \--- /task \---