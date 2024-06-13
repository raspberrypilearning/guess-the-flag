## Begin een nieuwe ronde

Op dit moment is er maar één ronde in de quiz, dus de quiz duurt niet lang. Je gaat meerdere rondes opzetten.

--- task ---

Maak een nieuw `signaal`{:class="block3events"} die het bericht 'Begin het spel' verzendt.

![Vlag sprite](images/flag-sprite.png)

```blocks3
broadcast (begin het spel v)
```

--- /task ---

--- task ---

Voeg een `wanneer ik signaal 'Begin het spel' ontvang`{:class="block3events"} blok toe en verplaats dan alle code van het `wanneer de op groene vlag wordt geklikt`{:class="block3events"} blok naar de onderkant van dit nieuwe blok.

![Vlag sprite](images/flag-sprite.png)

```blocks3
+ when I receive [begin het spel v]
set [score v] to [0]
maak vlaggenlijst :: custom
delete (alle v) of [gekozen vlaggen v]
repeat (6)
    kies willekeurige vlag :: custom
end
set [goed antwoord v] to (item (pick random (1) to (length of [gekozen vlaggen v])) of [gekozen vlaggen v])
kloon vlaggen :: custom
+ broadcast (kondig land aan v)
```

--- /task ---

--- task ---

Verwijder het `maak score 0`{:class="block3variables"} blok en plaats het terug onder het `wanneer op de groene vlag wordt geklikt`{:class="block3control"} blok. Voeg vervolgens het nieuwe blok `zend signaal`{:class="block3events"} onder beide toe.

![Vlag sprite](images/flag-sprite.png)

```blocks3
when green flag clicked
set [score v] to [0]
broadcast (begin het spel v)
```

--- /task ---

--- task ---

Na de code die controleert of het antwoord goed is, voeg je nog een `zend signaal`{:class="block3events"} blok toe zodat een nieuwe ronde kan beginnen zodra een vraag is beantwoord.

![Vlag sprite](images/flag-sprite.png)

```blocks3
when this sprite clicked
if <(costume [naam v]) = (goed antwoord :: variables)> then
    change [score v] by [1]
    say [Goed!] for (2) seconds
else
    say [Sorry, dat was niet goed] for (2) seconds
end
+ broadcast (begin het spel v)
```

--- /task ---

--- task ---

Klik op de groene vlag om je code te testen. Klik op een van de vlaggen om een ronde te spelen. Merk je dat de volgende ronde niet goed wordt uitgevoerd?

![Volgende ronde werkt niet](images/next-round-does-not-work.png)

--- /task ---

Dit komt omdat voordat het spel een nieuwe ronde begint, het spel eerst de gekloonde vlaggen moet opruimen.

--- task ---

Maak nog een nieuw `zend signaal`{:class="block3events"} met de naam 'wissen'.

![Vlag sprite](images/flag-sprite.png)

```blocks3
broadcast (wissen v)
```

--- /task ---

--- task ---

Stel de vlag sprite in op `verwijder deze kloon`{:class="block3control"} wanneer deze het signaal `wissen`{:class="block3events"} ontvangt.

![Vlag sprite](images/flag-sprite.png)

```blocks3
when I receive [wissen v]
delete this clone
```

--- /task ---

--- task ---

Plaats het signaalblok `wissen`{:class="block3events"} net boven waar het spel een nieuwe ronde begint nadat een antwoord is gegeven.

```blocks3
when this sprite clicked
maak vlaggenlijst :: custom
if <(item (costume [nummer v]) of [vlaggen v]) = (goed antwoord: variables)> then
    say [Goed!] for (2) seconds
    change [ score v] by [1]
else
    say [Sorry, dat was niet goed] for (2) seconds
end
+ broadcast (wissen v)
broadcast (begin het spel v)
```

--- /task ---

--- task ---

Test je code opnieuw en controleer of je meerdere rondes kunt spelen, en dat je score toeneemt naarmate je de juiste antwoorden geeft.

--- /task ---

--- task ---

Zorg ervoor dat je de variabele `goed antwoord`{:class="block3variables"} verbergt, zodat de speler het niet kan zien!

--- /task ---