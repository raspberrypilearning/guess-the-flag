## Προσθήκη βαθμολογίας

--- task ---

Δημιούργησε μια νέα μεταβλητή με το όνομα `σκορ`{:class="block3variables"} και όρισε το σκορ στο `0`{:class="block3variables"} όταν κάνεις κλικ στην πράσινη σημαία.

![Αντικείμενο σημαίας](images/flag-sprite.png)

```blocks3
when green flag clicked
+ set [σκορ v] to [0]
```

--- /task ---

--- task ---

Πρόσθεσε `1`{:class="block3variables"} στο σκορ κάθε φορά που ο παίκτης δίνει μία σωστή απάντηση.

![Αντικείμενο σημαίας](images/flag-sprite.png)

```blocks3
when this sprite clicked
if <(costume [name v]) = (σωστή απάντηση :: variables)> then 
+ change [σκορ v] by [1]
  say [Σωστά] for (2) seconds
else 
  say [Λυπάμαι, αυτό ήταν λάθος] for (2) seconds
end
```

--- /task ---