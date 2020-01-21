## Ξεκίνησε έναν νέο γύρο

Προς το παρόν υπάρχει μόνο ένας γύρος στο κουίζ, έτσι το κουίζ δεν διαρκεί πολύ. Πρόκειται να δημιουργήσεις πολλαπλούς γύρους.

\--- task \---

Create a new `broadcast`{:class="block3events"} that sends the message 'Start the round'.

![Flag sprite](images/flag-sprite.png)

```blocks3
μετάδωσε (έναρξη γύρου v)
```

\--- /task \---

\--- task \---

Add a `when I receive 'Start the round'`{:class="block3events"} block, and then move all of the code from below the `when green flag clicked`{:class="block3events"} block to below this new block.

![Flag sprite](images/flag-sprite.png)

```blocks3
+ όταν λάβω [έναρξη γύρου v]
όρισε [σκορ v] σε [0]
create flag list :: custom
διάγραψε (all v) από λίστα [επιλεγμένες σημαίες v]
επανάλαβε (6) 
  choose random flag :: custom
end
όρισε [σωστή απάντηση v] σε (στοιχείο (επίλεξε τυχαίο (1) εώς (μήκος λίστας [chosen flags v])) λίστας [chosen flags v])
clone flags :: custom
+ μετάδωσε (αναγγελία χώρας v)
```

\--- /task \---

\--- task \---

Remove the `set score to 0`{:class="block3variables"} block and place it back below the `when green flag clicked`{:class="block3control"} block. Then add the new `broadcast`{:class="block3events"} block below both of them.

![Αντικείμενο σημαίας](images/flag-sprite.png)

```blocks3
Όταν στην πράσινη σημαία γίνει κλικ
όρισε [σκορ v] σε [0]
μετάδωσε (έναρξη γύρου v)
```

\--- /task \---

\--- task \---

After the code that checks whether the answer is correct, add another `broadcast`{:class="block3events"} block so that a new round can start once a question is answered.

![Flag sprite](images/flag-sprite.png)

```blocks3
όταν γίνει κλικ σε αυτό το αντικείμενο
εάν <(ενδυμασία [όνομα v]) = (σωστή απάντηση :: variables)> τότε 
  άλλαξε [σκορ v] κατά [1]
  πες [Σωστά] για (2) δευτερόλεπτα
αλλιώς 
  πες [Λυπάμαι, αυτό ήταν λάθος] για (2) δευτερόλεπτα
end
+ μετάδωσε (έναρξη γύρου v)
```

\--- /task \---

\--- task \---

Click the green flag to test your code. Click on one of the flags to play a round. Do you notice that the next round does not get set up properly?

![Next round does not work](images/next-round-does-not-work.png)

\--- /task \---

This is because before the game starts another round, the game needs to first clear up the cloned flags.

\--- task \---

Create another new `broadcast`{:class="block3events"} called 'clean up'.

![Flag sprite](images/flag-sprite.png)

```blocks3
μετάδωσε (εκκαθάριση v)
```

\--- /task \---

\--- task \---

Set the Flag sprite to `delete this clone`{:class="block3control"} when it receives the `clean up`{:class="block3events"} broadcast.

![Flag sprite](images/flag-sprite.png)

```blocks3
όταν λάβω [εκκαθάριση v]
διάγραψε αυτόν τον κλώνο
```

\--- /task \---

\--- task \---

Place the `clean up`{:class="block3events"} broadcast block just above where the game starts a new round after an answer has been given.

```blocks3
όταν γίνει κλικ σε αυτό το αντικείμενο
create flags list :: custom
εάν <(στοιχείο (ενδυμασία [number v]) λίστας [flags v]) = (σωστή απάντηση :: variables)> τότε 
  πες [Σωστά] για (2) δευτερόλεπτα
  άλλαξε [σκορ v] κατά [1]
αλλιώς 
  πες [Λυπάμαι, αυτό ήταν λάθος] για (2) δευτερόλεπτα
end
+ μετάδωσε (εκκαθάριση v)
μετάδωσε (έναρξη γύρου v)
```

\--- /task \---

\--- task \---

Test your code again and check that you can play multiple rounds, and that your score increases as you get answers correct.

\--- /task \---

\--- task \---

Make sure you hide the `correct answer`{:class="block3variables"} variable so the player can't see it!

\--- /task \---