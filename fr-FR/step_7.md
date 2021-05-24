## Poser la question

Demandons au joueur de nommer le drapeau pour un pays particulier.

\--- task \---

Dans le sprite de drapeau, `envoyer à tous`{:class="block3events"} « dire le pays » immédiatement après le bloc qui clone les drapeaux.

![Sprite drapeau](images/flag-sprite.png)

```blocks3
when green flag clicked
create flag list :: custom
delete (all v) of [chosen flags v]
repeat (6)
    choose random flag :: custom
end
set [correct answer v] to (item (pick random (1) to (length of [chosen flags v])) of [chosen flags v])
clone flags :: custom
+ broadcast (announce country v)

```

[[[generic-scratch3-broadcast-message]]]

\--- /task \---

\--- task \---

Ajoute un nouveau sprite de ton choix pour être ton maître de quiz. Le maître de quiz dans l'exemple est le sprite appelé Abby.

![Sprite Abby](images/bear-sprite.png)

\--- /task \---

\--- task \---

Ajoute du code au sprite principal du quiz pour que, quand le sprite reçoit le message `dire le pays`{:class="block3events"}, elle dit au joueur de cliquer sur le nom du pays qui est stocké dans la variable `réponse correcte`{:class="block3variables"}.

![Sprite personnage](images/char-sprite.png)

\--- hints \--- \--- hint \---

`Quand je reçois`{:class="block3events"} le message, `dire`{:class="block3looks"} « clique sur `réponse correcte` »{:class="block3variables"}'.

\--- /hint \---

\--- hint \---

Voici les blocs dont tu as besoin :

```blocks3
(join [click on] [])

(correct answer)

say [] for (2) seconds

when I receive [announce country v]
```

\--- /hint \---

\--- hint \---

Voici à quoi ton code devrait ressembler :

```blocks3
when I receive [announce country v]
say (join [click on] (correct answer :: variables)) for (2) seconds
```

\--- /hint \---

\--- /hints \--- \--- /task \---