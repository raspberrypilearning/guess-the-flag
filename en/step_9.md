## Add a score

--- task ---
Create a new variable called `score`{:class="blockdata"} and set the score to `0`{:class="blockdata"} when the green flag is clicked.

![Flag sprite](images/flag-sprite.png)

```blocks
when flag clicked
set [score v] to [0]
```
--- /task ---

--- task ---
Add `1`{:class="blockdata"} to the score every time the player gets a correct answer.

![Flag sprite](images/flag-sprite.png)

```blocks
when this sprite clicked
create flags list
if <(item (costume #) of [flags v]) = (correct answer)> then
    say [Correct] for (2) secs
    + change [score v] by [1]
else
    say [Sorry, that was wrong] for (2) secs
end
```

--- /task ---
