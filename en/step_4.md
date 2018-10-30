## Choose random flags

We need to select six random flags from the flags list to be the possible choices in the game.

--- task ---
Create another list called `chosen flags`{:class="blockdata"}. This list will store the six chosen flags.
--- /task ---

--- task ---
Create a variable called `flag number`{:class="blockdata"}.
--- /task ---

--- task ---
Create a custom block and call it `choose random flag`{:class="blockmoreblocks"}.
--- /task ---

--- task ---
Add code to the custom block to set the `flag number`{:class="blockdata"} variable to a random number between 1 and the number of items in the `flags`{:class="blockdata"} list.

There is a special block in the Data tab for finding the number of items in a list.

--- hints ---
--- hint ---
Set the `flag number`{:class="blockdata"} variable to a `random number`{:class="blockoperators"} between 1 and the `length of the 'flags' list`{:class="blockdata"}.
--- /hint ---

--- hint ---
Here are the code blocks you'll need:

```blocks
(length of [flags v])

(pick random (1) to (10))

define choose random flag

set [flag number v] to []
```
--- /hint ---

--- hint ---
This is what your code should look like:

```blocks
define choose random flag
set [flag number v] to (pick random (1) to (length of [flags v]))
```
--- /hint ---

--- /hints ---
--- /task ---


This block selects an item from a list, by number:

```blocks
(item (10 v) of [flags v])
```
--- task ---
Combine this block with the `flag number`{:class="blockdata"} variable to get the text of the randomly chosen item in the `flags`{:class="blockdata"} list. Insert the item text into the `chosen flags`{:class="blockdata"} list. Add this code to your custom block.

```blocks
define choose random flag
set [flag number v] to (pick random (1) to (length of [flags v]))
+ insert (item (flag number) of [flags v]) at (last v) of [chosen flags v]
```

--- /task ---

--- task ---
Add your custom block to the code that will be run when the green flag is clicked.

```blocks
when flag clicked
create flag list
+ choose random flag
```
--- /task ---

--- task ---
Test that your code works by clicking the green flag several times and checking that different countries are added to the `chosen flags`{:class="blockdata"} list. (If you have hidden the list, tick the box next to it to make it visible.)
--- /task ---

You will notice that, if you press the green flag lots of times, your `chosen flags`{:class="blockdata"} list quickly fills up with more than six choices.

--- task ---
Add blocks to delete all of the countries from the `chosen flags`{:class="blockdata"} list before choosing six flags for the game.

```blocks
when flag clicked
create flag list
+ delete (all v) of [chosen flags v]
+ repeat (6)
    choose random flag
end
```
--- /task ---


--- task ---
Test your code by clicking the green flag and checking that the `chosen flags` list is filled with six countries each time.
--- /task ---

You might notice that sometimes the same country gets chosen more than once in the list.

![Duplicate countries](images/duplicate-countries.png)

--- task ---
Add a block to the end of your custom block code to delete the randomly chosen `Flag number` from the `Flags` list after it has been added to the `Chosen flags` list. This will stop it from being chosen more than once.

```blocks
define choose random flag
set [flag number v] to (pick random (1) to (length of [flags v]))
insert (item (flag number) of [flags v]) at (last v) of [chosen flags v]
+ delete (flag number) of [flags v]
```
--- /task ---
