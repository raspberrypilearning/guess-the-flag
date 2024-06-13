## Επίλεξε μια σωστή απάντηση

Τώρα που έχεις μια λίστα που περιέχει έξι επιλεγμένες σημαίες, επίλεξε ποια από αυτές θα είναι η σωστή απάντηση αυτή τη φορά.

--- task ---

Δημιούργησε μία νέα μεταβλητή με όνομα `σωστή απάντηση`{:class="block3variables"}.

--- /task ---

--- task ---

Αφού επιλεγούν οι έξι σημαίες, όρισε τη μεταβλητή `σωστή απάντηση`{:class="block3variables"} να είναι ένα τυχαίο στοιχείο από τη λίστα `επιλεγμένων σημαιών`{:class="block3variables"}.

![Αντικείμενο σημαίας](images/flag-sprite.png)

```blocks3
when green flag clicked
create flag list :: custom
delete (all v) of [chosen flags v]
repeat (6)
    choose random flag :: custom
end
+ set [σωστή απάντηση v] to (item (pick random (1) to (length of [επιλεγμένες σημαίες v])) of [επιλεγμένες σημαίες v])
```

--- /task ---