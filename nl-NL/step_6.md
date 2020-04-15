## Toon de vlaggen

De persoon die de quiz maakt, moet de afbeeldingen van de vlaggen in de `gekozen vlaggen`{:class="block3variables"} lijst zien.

--- task ---

Maak nog een aangepast blok en noem dit `kloon vlaggen`{:class="block3myblocks"}.

![Vlag sprite](images/flag-sprite.png)

```blocks3
define kloon vlaggen
```

--- /task ---

Dit aangepaste blok zal de vlag sprite zes keer klonen, eenmaal voor elke vlag die moet worden weergegeven.

De eerste vlag moet linksboven in het werkgebied worden weergegeven.

--- task ---

Als onderdeel van de instructies voor je `kloon vlaggen`{:class="block3myblocks"}, maak je de vlag sprite zichtbaar en voeg je een `ga naar`{:class="block3motion"} blok toe om de sprite te vertellen dat deze moet worden weergegeven op de coördinaten `-170`{:class="block3motion"}, `120`{:class="block3motion"} in de linkerbovenhoek van het speelveld.

![Vlag sprite](images/flag-sprite.png)

```blocks3
define kloon vlaggen
verschijn
ga naar x: (-170) y: (120)
```

--- /task ---

--- task ---

Voeg onder die code een lus toe die zes keer wordt herhaald.

![Vlag sprite](images/flag-sprite.png)

Voeg binnen de lus codeblokken toe om het uiterlijk van de sprite naar de eerste vlag in de `gekozen vlaggen`{:class="block3variables"} lijst te schakelen en de sprite te klonen. Voeg vervolgens codeblokken toe om de eerste vlag uit de lijst te verwijderen en om `110`{:class="block3motion"} op te tellen bij de `x`{:class="block3motion"} -coördinaat om de sprite naar de positie van de tweede vlag te verplaatsen.

--- hints ---
 --- hint ---

`herhaal`{:class="block3control"} zes keer: `verander uiterlijk`{:class="block3looks"} naar het eerste `item in gekozen vlaggen`{:class="block3variables"}. `Maak een kloon van mijzelf`{:class="block3control"}. `Verwijder`{:class="block3variables"} het `eerste item in gekozen vlaggen`{:class="block3variables"}. `Neem 110 stappen`{:class="block3motion"}.

--- /hint ---

--- hint ---

Hier zijn de codeblokken die je moet toevoegen:

```blocks3
(item (1) van [gekozen vlaggen v])

verander x met (110)

maak een kloon van (mijzelf v)

verander uiterlijk naar ( v)

verwijder (1) van [gekozen vlaggen v]

herhaal (6)
einde
```

--- /hint ---

--- hint ---

Dit is hoe je code eruit zou moeten zien:

```blocks3
define kloon vlaggen
verschijn
ga naar x: (-170) y: (120)
+ herhaal (6)
    verander uiterlijk naar (item (1) van [gekozen vlaggen v])
    maak een kloon van (mijzelf v)
    verwijder (1) van [gekozen vlaggen v]
    verander x met (110)
einde
```

--- /hint ---

--- /hints --- --- /task ---

--- task ---

Voeg `kloon vlaggen`{:class="block3myblocks"} toe aan het einde van de code die wordt uitgevoerd wanneer op de groene vlag wordt geklikt.

![Vlag sprite](images/flag-sprite.png)

```blocks3
when flag clicked
maak vlaggenlijst :: custom
verwijder (alle v) van [gekozen vlaggen v]
herhaal (6)
  kies willekeurige vlag :: custom
einde
+ kloon vlaggen :: custom
```

--- /task ---

--- task ---

Voer je code uit. Merk op dat de verschillende vlaggen verschijnen, maar sommige worden afgesneden aan de rand van het werkgebied.

![Vlaggen verdwijnen van het scherm](images/flags-off-the-screen.png)

--- /task ---

In plaats van alle zes vlaggen op één rij te plaatsen, maak je twee rijen van drie vlaggen.

--- task ---

Voeg code toe binnen de `herhaal`{:class="block3control"} lus van het `kloon vlaggen`{:class="block3myblocks"} blok om de vlag sprite een rij naar beneden te verplaatsen als er drie vlaggen over zijn in de `gekozen vlaggen`{:class="block3variables"} lijst.

![Vlag sprite](images/flag-sprite.png)

Je kunt de sprite een rij naar beneden verplaatsen door nog een `ga naar`{:class="block3motion"} blok te gebruiken met dezelfde `x`{:class="block3motion"} coördinaat als het startpunt, maar verander de `y`{:class="block3motion"} coördinaat om naar beneden te gaan.

```blocks3
define kloon vlaggen
verschijn
ga naar x: (-170) y: (120)
herhaal (6)
    verander uiterlijk naar (item (1) van [gekozen vlaggen v])
    maak een kloon van (mijzelf v)
    verwijder (1) van [gekozen vlaggen v]
    verander x met (110)
+ als <(lengte van [gekozen vlaggen v]) = [3]> dan
        ga naar x: (-170) y: (50)
    einde
einde
```

--- /task ---

--- task ---

Klik op de groene vlag en controleer of de vlaggen in twee rijen worden weergegeven.

--- /task ---

Het lijkt erop dat de laatste vlag twee keer wordt weergegeven. Dit komt omdat de originele vlag sprite aan het einde nog steeds zichtbaar is.

--- task ---

Voeg een `verdwijn`{:class="block3looks"} blok toe aan het einde van de code binnen het `kloon vlaggen`{:class="block3myblocks"} blok om de originele sprite te verbergen.

![Vlag sprite](images/flag-sprite.png)

--- /task ---

Als je wilt, kun je proberen de vlag sprites één voor één te laten verschijnen of een geluid (bijvoorbeeld een plop) af te spelen telkens wanneer een vlag verschijnt.