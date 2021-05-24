## Choisir une réponse correcte

Maintenant que tu as une liste contenant six drapeaux choisis, choisis lequel d'entre eux sera la bonne réponse cette fois-ci.

\--- task \---

Crée une nouvelle variable appelée `réponse correcte`{:class="block3variables"}.

\--- /task \---

\--- task \---

Après avoir choisi les six drapeaux, définis la variable `réponse correcte`{:class="block3variables"} comme étant un élément aléatoire de la liste `drapeaux choisis`{:class="block3variables"}.

![Sprite drapeau](images/flag-sprite.png)

```blocks3
when green flag clicked
create flag list :: custom
delete (all v) of [chosen flags v]
repeat (6)
    choose random flag :: custom
end
+ set [correct answer v] to (item (pick random (1) to (length of [chosen flags v]) ) of [chosen flags v])
```

\--- /task \---