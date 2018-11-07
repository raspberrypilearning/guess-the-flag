## Start a new round

At the moment we only have one round to play, so the game doesn't last long. Let's set up multiple rounds.

--- task ---
Create a new broadcast called 'Start the round'.

![Flag sprite](images/flag-sprite.png)

```blocks
broadcast [start the round v]
```

--- /task ---

--- task ---
Move all of the code which previously ran after the green flag was clicked, so that it runs `when I receive 'Start the round'`{:class="blockevents"}.

![Flag sprite](images/flag-sprite.png)


```blocks
+ when I receive [start the round v]
set [score v] to [0]
create flag list
...
```

--- /task ---

--- task ---
Remove the `set score to 0`{:class="blockdata"} block and place it back with the `when flag clicked`{:class="blockcontrol"} block, followed by the new broadcast block you just created.

![Flag sprite](images/flag-sprite.png)

```blocks
when flag clicked
set [score v] to [0]
broadcast [start the round v]
...
```
--- /task ---

--- task ---
After the code where you check the answer, add another copy of the broadcast block to start a new round after an answer has been given.

![Flag sprite](images/flag-sprite.png)

```blocks
when this sprite clicked
create flags list
if <(item (costume #) of [flags v]) = (correct answer)> then
    say [Correct] for (2) secs
    change [score v] by [1]
else
    say [Sorry, that was wrong] for (2) secs
end
+ broadcast [start the round v]
```

--- /task ---

--- task ---
Click the green flag to test your code. Click on a flag to play a round. You will notice that the next round does not get set up properly.

![Next round does not work](images/next-round-does-not-work.png)
--- /task ---

This is because we need to clear up the cloned flags we created before beginning another round.

--- task ---
Create another new `broadcast`{:class="blockevents"} called 'clean up'.

![Flag sprite](images/flag-sprite.png)

```blocks
broadcast [clean up v]
```
--- /task ---

--- task ---
Set the flag sprite to `delete this clone`{:class="blockcontrol"} when it receives the 'clean up' broadcast.

![Flag sprite](images/flag-sprite.png)

```blocks
when I receive [clean up v]
delete this clone
```
--- /task ---

--- task ---
Place the block that `broadcasts`{:class="blockevents"} 'clean up' just before you begin a new round after an answer has been given.

```blocks
when this sprite clicked
create flags list
if <(item (costume #) of [flags v]) = (correct answer)> then
    say [Correct] for (2) secs
    change [score v] by [1]
else
    say [Sorry, that was wrong] for (2) secs
end
+ broadcast [clean up v]
broadcast [start the round v]
```
--- /task ---

--- task ---
Test your code again and check that you can play multiple rounds successfully, and that your score continues to increase as you get answers correct.
--- /task ---

--- task ---
Make sure you right click and hide the `correct answer`{:class="blockdata"} variable so the player can't see it!
--- /task ---
