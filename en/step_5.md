## Choose a correct answer

Now that you have a list containing six chosen flags, choose which of them will be the correct answer this time.

--- task ---
Create a new variable called `correct answer`{:class="blockdata"}.
--- /task ---

--- task ---
After the six flags are chosen, set the `correct answer`{:class="blockdata"} variable to be a random item from the `chosen flags`{:class="blockdata"} list.

![Flag sprite](images/flag-sprite.png)

```blocks
when green flag clicked
create flag list :: custom
delete (all v) of [chosen flags v]
repeat (6)
    choose random flag :: custom
end
+ set [correct answer v] to (item (random v) of [chosen flags v])
```
--- /task ---
