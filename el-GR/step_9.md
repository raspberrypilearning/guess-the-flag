## Προσθήκη βαθμολογίας

\--- task \---

Create a new variable called `score`{:class="block3variables"} and set the score to `0`{:class="block3variables"} when the green flag is clicked.

![Flag sprite](images/flag-sprite.png)

```blocks3
Όταν στην πράσινη σημαία γίνει κλικ
+ όρισε [σκορ v] σε [0]
```

\--- /task \---

\--- task \---

Add `1`{:class="block3variables"} to the score every time the player gives a correct answer.

![Flag sprite](images/flag-sprite.png)

```blocks3
όταν γίνει κλικ σε αυτό το αντικείμενο
εάν <(ενδυμασία [name v]) = (σωστή απάντηση :: variables)> τότε 
  + άλλαξε [σκορ v] κατά [1]
  πες [Σωστά] για (2) δευτερόλεπτα
αλλιώς 
  πες [Λυπάμαι, αυτό ήταν λάθος] για (2) δευτερόλεπτα
end
```

\--- /task \---