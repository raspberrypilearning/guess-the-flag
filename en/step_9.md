## Add a score

--- task ---
Create a new variable called `score`{:class="block3variables"} and set the score to `0`{:class="block3variables"} when the green flag is clicked.

![Flag sprite](images/flag-sprite.png)

```blocks3
when green flag clicked
set [score v] to [0]
```
--- /task ---

--- task ---
Add `1`{:class="block3variables"} to the score every time the player gives a correct answer.

![Flag sprite](images/flag-sprite.png)

```blocks3
when this sprite clicked
create flag list :: custom
if <(item (costume #) of [flags v]) = (correct answer)> then
    say [Correct] for (2) secs
    + change [score v] by [1]
else
    say [Sorry, that was wrong] for (2) secs
end
```

--- /task ---
