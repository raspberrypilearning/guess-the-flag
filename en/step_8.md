## Check the answer

Your sprite asks the player to click on the flag they think is correct. Now we need to check whether the flag they clicked was the right answer.

--- task ---
Go back to the flag sprite code, and add a block to start a new section of code which will happen `when this sprite is clicked`{:class="blockevents"}.
--- /task ---

We need to check whether the costume of the sprite that has been clicked has the same name as the correct answer.

--- task ---
Add code to say 'Correct' if the costume name of this sprite is the same as the `Correct answer` variable, or to say 'Sorry, that was wrong' if it is not.

You can use this useful block here as well. This time, combine it with a `costume #` block to get the name of the current costume.

![Item from list](images/item-from-list.png)

--- hints ---
--- hint ---
`When this sprite is clicked`, `create the flags list`. `If` the `item in the Flags list` with this `costume #` equals the `correct answer`, `say` 'Correct', or `else` `say` 'Sorry, that was wrong'.
--- /hint ---

--- hint ---
Here are the code blocks you'll need:

![Check answer hint](images/check-answer-hint.png)
--- /hint ---

--- hint ---
This is what your code should look like:

![Check answer solution](images/check-answer-solution.png)
--- /hint ---

--- /hints ---
--- /task ---

--- task ---
Press the green flag and test your code by getting the answer deliberately right and wrong. Check that the right message appears depending on whether you were right or wrong.

![Click on the flag](images/click-on-flag.png)
--- /task ---

--- task ---
Use a broadcast to make the bear sprite (not the flag sprite) report whether the player was right or wrong.
--- /task ---
