## Poser la question

Demandons au joueur de nommer le drapeau pour un pays particulier.

--- task ---

Dans le sprite de drapeau, `envoyer à tous`{:class="block3events"} « dire le pays » immédiatement après le bloc qui clone les drapeaux.

![Sprite drapeau](images/flag-sprite.png)

```blocks3
when green flag clicked
créer une liste de drapeaux :: custom
delete (all v) of [drapeaux choisis v]
repeat (6)
    choisir un drapeau aléatoire :: custom
end
set [réponse correcte v] to (item (pick random (1) to (length of [drapeaux choisis v])) of [drapeaux choisis v])
cloner les drapeaux :: custom
+ broadcast (dire le pays v)

```

[[[generic-scratch3-broadcast-message]]]

--- /task ---

--- task ---

Ajoute un nouveau sprite de ton choix pour être ton maître de quiz. Le maître de quiz dans l'exemple est le sprite appelé Abby.

![Sprite Abby](images/bear-sprite.png)

--- /task ---

--- task ---

Ajoute du code au sprite principal du quiz pour que, quand le sprite reçoit le message `dire le pays`{:class="block3events"}, elle dit au joueur de cliquer sur le nom du pays qui est stocké dans la variable `réponse correcte`{:class="block3variables"}.

![Sprite personnage](images/char-sprite.png)

--- hints ---
 --- hint ---

`Quand je reçois`{:class="block3events"} le message, `dire`{:class="block3looks"} « clique sur `réponse correcte` »{:class="block3variables"}'.

--- /hint ---

--- hint ---

Voici les blocs dont tu as besoin :

```blocks3
(join [clique sur] [])

(réponse correcte)

say [] for (2) seconds

when I receive [dire le pays v]
```

--- /hint ---

--- hint ---

Voici à quoi ton code devrait ressembler :

```blocks3
when I receive [dire le pays v]
say (join [clique sur] (réponse correcte :: variables)) for (2) seconds
```

--- /hint ---

--- /hints --- --- /task ---