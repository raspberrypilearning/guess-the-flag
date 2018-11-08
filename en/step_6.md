## Show the flags

The player needs to be able to see the pictures of the flags in the `chosen flags`{:class="blockdata"} list to be able to play.

--- task ---
Create another custom block, this time called `clone flags`{:class="blockmoreblocks"}.

![Flag sprite](images/flag-sprite.png)

```blocks
define [clone flags]
```

--- /task ---

We will clone the Flag sprite six times, once for each flag that will be displayed. We would like the first flag to be displayed in the top left-hand corner of the page.

--- task ---
Move your mouse to a point near the top left-hand corner of the stage. This will be where the centre of your first flag sprite appears, so don't go too close to the edge. Note down the coordinates of the point you chose.

[[[generic-scratch-coordinates]]]
--- /task ---

--- task ---
As part of the instructions for your `clone flags`{:class="blockmoreblocks"} block, make the sprite visible, and add a `go to`{:class="blockmotion"} block to tell the flag sprite to display at the coordinates you noted down.

![Flag sprite](images/flag-sprite.png)

```blocks
define [clone flags]
show
go to x: (-170) y: (120)
```
--- /task ---

--- task ---
Underneath that code, add a loop that repeats six times.

![Flag sprite](images/flag-sprite.png)

Inside the loop, add code to switch the costume to the last flag in the `chosen flags`{:class="blockdata"} list and to clone the sprite. Then, delete the last flag from the list and add `110`{:class="blockmotion"} to the `x`{:class="blockmotion"} coordinate to move along ready to place the next flag.

--- hints ---
--- hint ---
`Repeat`{:class="blockcontrol"} six times:
`Switch costume`{:class="blocklooks"} to the `last item in chosen flags`{:class="blockdata"}.
`Clone the sprite`{:class="blockcontrol"}.
`Delete`{:class="blockdata"} the last item in chosen flags.
`Move right 110`{:class="blockmotion"}.
--- /hint ---

--- hint ---
Here are the code blocks you'll need to add:

```blocks
(item (last v) of [chosen flags v])

change x by (110)

create clone of [myself v]

switch costume to [ v]

delete (last v) of [chosen flags v]

repeat (6)
end
```
--- /hint ---

--- hint ---
This is what your code should look like:

```blocks
define [clone flags]
show
go to x: (-170) y: (120)
+ repeat (6)
    + switch costume to (item (last v) of [chosen flags v])
    + create clone of [myself v]
    + delete (last v) of [chosen flags v]
    + change x by (110)
end
```
--- /hint ---

--- /hints ---
--- /task ---

--- task ---
Add your `clone flags`{:class="blockmoreblocks"} block to the end of the code that happens when the green flag is clicked.

![Flag sprite](images/flag-sprite.png)

```blocks
when green flag clicked
create flag list :: custom
delete (all v) of [chose flags v]
repeat (6) 
  choose random flag :: custom
end
+ clone flags :: custom
```

--- /task ---

--- task ---
Run your code by pressing the green flag. You will notice that the different flags do appear, but they go off the end of the stage.

![Flags go off the screen](images/flags-off-the-screen.png)

--- /task ---

Let's make two rows of three flags.

--- task ---
Add some code inside the loop to move down a row if there are three flags left in the `chosen flags`{:class="blockdata"} list.

![Flag sprite](images/flag-sprite.png)

You can move down a row by using another `go to`{:class="blockmotion"} block and keeping the `x`{:class="blockmotion"} coordinate the same as the starting point, but decreasing the `y`{:class="blockmotion"} coordinate to move downwards.

```blocks
define [clone flags]
show
go to x: (-170) y: (120)
repeat (6)
    switch costume to [(item (last v) of [chosen flags v])]
    create clone of [myself v]
    delete (last v) of [chosen flags v]
    change x by (110)
    + if <(length of [chosen flags v]) = [3]> then
        + go to x: (-170) y: (50)
    + end
end
```
--- /task ---

--- task ---
Press the green flag and check that the flags display in two rows.
--- /task ---

It looks like the last flag is displaying twice. In actual fact what is happening is that the original flag sprite is still visible at the end.

--- task ---
Add a `hide`{:class="blocklooks"}  block at the end of your custom block's code to hide the original sprite.

![Flag sprite](images/flag-sprite.png)

--- /task ---

If you want to, you could try making the flag sprites appear one by one or making each flag make a sound (a pop, for example) when it appears?
