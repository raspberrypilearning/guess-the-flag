## Choisir une réponse correcte

Maintenant que tu as une liste contenant six drapeaux choisis, choisis lequel d'entre eux sera la bonne réponse cette fois-ci.

--- task ---

Crée une nouvelle variable appelée `réponse correcte`{:class="block3variables"}.

--- /task ---

--- task ---

Après avoir choisi les six drapeaux, définis la variable `réponse correcte`{:class="block3variables"} comme étant un élément aléatoire de la liste `drapeaux choisis`{:class="block3variables"}.

![Sprite drapeau](images/flag-sprite.png)

```blocks3
when green flag clicked
créer une liste de drapeaux :: custom
delete (all v) of [drapeaux choisis v]
repeat (6)
    choisir un drapeau aléatoire :: custom
end
+ set [réponse correcte v] to (item (pick random (1) to (length of [drapeaux choisis v]) ) of [drapeaux choisis v])
```

--- /task ---