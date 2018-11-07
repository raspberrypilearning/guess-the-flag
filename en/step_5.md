## Choose a correct answer

Now that we have a list containing six chosen flags, let's choose which of them will be the correct answer this time.

--- task ---
Create a new variable called `correct answer`{:class="blockdata"}.
--- /task ---

--- task ---
After you have chosen the six flags, set the `correct answer`{:class="blockdata"} variable to be a random item from the `chosen flags`{:class="blockdata"} list.

![Flag sprite](images/flag-sprite.png)

```blocks
when flag clicked
create flag list
delete (all v) of [chosen flags v]
repeat (6)
    choose random flag
end
+ set [correct answer v] to (item (random v) of [chosen flags v])
```
--- /task ---
