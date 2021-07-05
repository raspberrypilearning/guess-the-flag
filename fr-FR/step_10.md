## Commencer une nouvelle partie

Pour le moment, il n'y a qu'une seule partie dans le quiz, donc le quiz ne dure pas longtemps. Tu vas mettre en place plusieurs parties.

--- task ---

Crée un nouveau `envoyer à tous`{:class="block3events"} qui envoie le message « Commencer la partie ».

![Sprite drapeau](images/flag-sprite.png)

```blocks3
broadcast (commencer la partie v)
```

--- /task ---

--- task ---

Ajoute un bloc `quand je reçois le bloc « Commencer la partie »'`{:class="block3events"}, puis déplace tout le code qui se trouve sous le bloc `quand le drapeau vert est cliqué`{:class="block3events"} en dessous de ce nouveau bloc.

![Sprite drapeau](images/flag-sprite.png)

```blocks3
+ when I receive [commencer la partie v]
set [score v] to [0]
créer une liste de drapeaux :: custom
delete (all v) of [drapeaux choisis v]
repeat (6)
    choisir un drapeau aléatoire :: custom
end
set [réponse correcte v] to (item (pick random (1) to (length of [drapeaux choisis v])) of [drapeaux choisis v])
cloner les drapeaux :: custom
+ broadcast (dire le pays v)
```

--- /task ---

--- task ---

Supprime le bloc `mettre le score à 0`{:class="block3variables"} et place-le en dessous du bloc `quand le drapeau vert est cliqué`{:class="block3control"}. Ajoute ensuite le nouveau bloc `envoyer à tous`{:class="block3events"} sous chacun d'eux.

![Sprite drapeau](images/flag-sprite.png)

```blocks3
when green flag clicked
set [score v] to [0]
broadcast (commencer la partie v)
```

--- /task ---

--- task ---

Après le code vérifiant si la réponse est correcte, ajoute un autre bloc `envoyer à tous`{:class="block3events"} pour qu'une nouvelle partie puisse commencer après qu'une question soit répondue.

![Sprite drapeau](images/flag-sprite.png)

```blocks3
when this sprite clicked
if <(costume [name v]) = (réponse correcte :: variables)> then
    change [score v] by [1]
    say [Correct] for (2) seconds
else
    say [Désolé, ce n'est pas correct] for (2) seconds
end
+ broadcast (commencer la partie v)
```

--- /task ---

--- task ---

Clique sur le drapeau vert pour tester ton code. Clique sur l'un des drapeaux pour jouer une partie. As-tu remarqué que la partie suivante ne se met pas en place correctement ?

![La partie suivante ne fonctionne pas](images/next-round-does-not-work.png)

--- /task ---

C'est parce qu'avant de commencer une nouvelle partie, le jeu doit d'abord effacer les drapeaux clonés.

--- task ---

Crée un nouveau `envoyer à tous`{:class="block3events"} appelé « effacer ».

![Sprite drapeau](images/flag-sprite.png)

```blocks3
broadcast (effacer v)
```

--- /task ---

--- task ---

Définit le sprite Drapeau sur `supprimer ce clone`{:class="block3control"} quand il reçoit le message `effacer`{:class="block3events"}.

![Sprite drapeau](images/flag-sprite.png)

```blocks3
when I receive [effacer v]
delete this clone
```

--- /task ---

--- task ---

Place le bloc de diffusion `effacer`{:class="block3events"} juste au-dessus de l'endroit où le jeu commence une nouvelle partie après qu'une réponse ait été donnée.

```blocks3
when this sprite clicked
créer une liste de drapeaux  :: custom
if <(item (costume [number v]) of [drapeaux v]) = (réponse correcte :: variables)> then
    say [Correct] for (2) seconds
    change [score v] by [1]
else
    say [Désolé, ce n'est pas correct] for (2) seconds
end
+ broadcast (effacer v)
broadcast (commencer la partie v)
```

--- /task ---

--- task ---

Teste à nouveau ton code et vérifie que tu peux jouer plusieurs parties, et que ton score augmente lorsque la réponse est correcte.

--- /task ---

--- task ---

Assure-toi de cacher la variable `réponse correcte`{:class="block3variables"} pour que le joueur ne puisse pas la voir !

--- /task ---