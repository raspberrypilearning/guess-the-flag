## Create a list of flags

--- task ---
Click on the Scripts tab. Create a list called `Flags`{:class="blockdata"}. This will be where we store the names of all of the countries whose flags we have included in the game.

![Flag sprite](images/flag-sprite.png)

[[[generic-scratch-make-list]]]
--- /task ---

--- task ---
Add some code to add Japan to the `Flags`{:class="blockdata"} list.

![Flag sprite](images/flag-sprite.png)

```blocks
when flag clicked
add [Japan] to [Flags v]
```
--- /task ---

--- task ---
Add one block for each of the other countries, so you end up with a total of ten blocks adding all ten countries to your `Flags`{:class="blockdata"} list
--- /task ---

--- task ---
Click the green flag and check that the countries appear in the list.
--- /task ---

If you press the green flag more than once, you will see that the countries are added to the list again, so you end up with a list of 20 countries and not 10.

--- task ---
Add a block to the start of the code which will `delete all`{:class="blockdata"} of the countries in the list before adding them. This will stop the countries from being added to the list more than once.

![Flag sprite](images/flag-sprite.png)

```blocks
when flag clicked
+ delete (all v) of [Flags v]
add [Japan] to [Flags v]
add [Belgium] to [Flags v]
add [Italy] to [Flags v]
...
```

--- /task ---

Let's make a custom block. This is a special block with a name, and we will be able to create a list of flags using only this one block, instead of having to use lots of blocks.

--- task ---
Click on 'More Blocks' and then 'Make a Block'. Call your custom block `create flags list`{:class="blockmoreblocks"}

![Add a block](images/add-block.png)
--- /task ---

--- task ---
Drag all of the code so that it is underneath the new block instead of the  `when flag clicked`{:class="blockcontrol"} block.
--- /task ---

--- task ---
Underneath the `when flag clicked`{:class="blockcontrol"} block, add the new block.

![Flag sprite](images/flag-sprite.png)

```blocks
when flag clicked
create flag list
...
```

--- /task ---  
