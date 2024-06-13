## Ρώτα την ερώτηση

Ας ζητήσουμε από τον παίκτη να επιλέξει τη σημαία μιας συγκεκριμένης χώρας.

--- task ---

Στο αντικείμενο σημαίας, `μετάδωσε το μήνυμα`{:class="block3events"} 'αναγγελία χώρας' αμέσως μετά το μπλοκ που κλωνοποιεί τις σημαίες.

![Αντικείμενο σημαίας](images/flag-sprite.png)

```blocks3
when green flag clicked
create flag list :: custom
delete (all v) of [επιλεγμένες σημαίες v]
repeat (6)
    choose random flag :: custom
end
set [σωστή απάντηση v] to (item (pick random (1) to (length of [επιλεγμένες σημαίες v])) of [επιλεγμένες σημαίες v])
clone flags :: custom
+broadcast (αναγγελία χώρας v)
```

[[[generic-scratch3-broadcast-message]]]

--- /task ---

--- task ---

Πρόσθεσε ένα νέο χαρακτήρα της επιλογής σου για να είναι αυτός που θα κάνει τις ερωτήσεις. Αυτός ο χαρακτήρας στο παράδειγμα είναι ο χαρακτήρας που ονομάζεται Abby.

![Χαρακτήρας Abby](images/bear-sprite.png)

--- /task ---

--- task ---

Πρόσθεσε κώδικα στο χαρακτήρα, έτσι ώστε, όταν ο χαρακτήρας λάβει την εκπομπή `αναγγελία χώρας`{:class="block3events"}, ενημερώνει τον παίκτη να κάνει κλικ στο όνομα της χώρας που είναι αποθηκευμένη στη μεταβλητή `σωστή απάντηση`{:class="block3variables"}.

![Χαρακτήρας](images/char-sprite.png)

--- hints ---
--- hint ---

 `Όταν λάβεις`{:class="block3events"} την εκπομπή, `πες`{:class="block3looks"} 'κανε κλικ στη`σωστή απάντηση`{:class="block3variables"}'.
--- /hint ---

--- hint ---

Εδώ είναι τα μπλοκ κωδικα που χρειάζεσαι:

```blocks3
(join [click on] [])

(σωστή απάντηση)

say [] for (2) seconds

when I receive [αναγγελία χώρας v]
```

--- /hint ---

--- hint ---

Αυτός είναι ο κώδικας με τον οποίον θα πρέπει να μοιάζει ο δικός σου:

```blocks3
when I receive [announce country v]
say (join [click on] (correct answer :: variables)) for (2) seconds
```

--- /hint ---

--- /hints ---

--- /task ---