## Ρώτα την ερώτηση

Ας ζητήσουμε από τον παίκτη να επιλέξει τη σημαία μιας συγκεκριμένης χώρας.

\--- task \---

In the flag sprite, `broadcast the message`{:class="block3events"} 'announce country' immediately after the block that clones the flags.

![Flag sprite](images/flag-sprite.png)

```blocks3
όταν γίνει κλικ σε αυτό το αντικείμενο
εάν <(ενδυμασία [όνομα v]) = (σωστή απάντηση :: variables)> τότε 
  πες [Σωστά] για (2) δευτερόλεπτα
αλλιώς 
  πες [Λυπάμαι, αυτό ήταν λάθος] για (2) δευτερόλεπτα
end
όρισε [σωστή απάντηση v] σε (στοιχείο (επίλεξε τυχαίο (1) εώς (μήκος λίστας [επιλεγμένες σημαίες v])) λίστας [επιλεγμένες σημαίες v])
clone flags :: custom
+μετάδωσε (αναγγελία χώρας v)

```

[[[generic-scratch3-broadcast-message]]]

\--- /task \---

\--- task \---

Add a new sprite of your choice to be your quiz master. The quiz master in the example is the sprite called Abby.

![Abby sprite](images/bear-sprite.png)

\--- /task \---

\--- task \---

Add some code to the quiz master sprite so that, when the sprite receives the `announce country`{:class="block3events"} broadcast, it tells the player to click on the country name that is stored in the variable `correct answer`{:class="block3variables"}.

![Character sprite](images/char-sprite.png)

\--- hints \--- \--- hint \---

`When I receive`{:class="block3events"} the broadcast, `say`{:class="block3looks"} 'click on `correct answer`{:class="block3variables"}'.

\--- /hint \---

\--- hint \---

Here are the code blocks you need:

```blocks3
(ένωσε [click on] [])

(σωστή απάντηση)

πες [] για (2) δευτερόλεπτα

όταν λάβω [αναγγελία χώρας v]
```

\--- /hint \---

\--- hint \---

This is what your code should look like:

```blocks3
when I receive [announce country v]
say (join [click on] (correct answer :: variables)) for (2) seconds
```

\--- /hint \---

\--- /hints \--- \--- /task \---