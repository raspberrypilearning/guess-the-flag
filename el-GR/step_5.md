## Επίλεξε μια σωστή απάντηση

Τώρα που έχεις μια λίστα που περιέχει έξι επιλεγμένες σημαίες, επίλεξε ποια από αυτές θα είναι η σωστή απάντηση αυτή τη φορά.

\--- task \---

Create a new variable called `correct answer`{:class="block3variables"}.

\--- /task \---

\--- task \---

After the six flags are chosen, set the `correct answer`{:class="block3variables"} variable to be a random item from the `chosen flags`{:class="block3variables"} list.

![Flag sprite](images/flag-sprite.png)

```blocks3
Όταν στην πράσινη σημαία γίνει κλικ
create flag list :: custom
διάγραψε (all v) από λίστα [chosen flags v]
επανάλαβε (6) 
  choose random flag :: custom
end
+ όρισε [σωστή απάντηση v] σε (στοιχείο (επίλεξε τυχαίο (1) εώς (μήκος λίστας [επιλεγμένες σημαίες v])) λίστας [επιλεγμένες σημαίες v])
```

\--- /task \---