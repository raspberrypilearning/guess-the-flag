## Create a list of flags

+ Click on the Scripts tab, and then on the flag sprite.

+ Create a list called `Flags`. This will be where we store the names of all of the countries whose flags we have included in the game.

[[[generic-scratch-make-list]]]

+ Drag some blocks into the scripts area to add all of the countries to the `Flags` list. You can start off like this:

![Add flags to list](images/add-to-list.png)

+ Check that, when you press the green flag, the countries appear in the list.

If you press the green flag more than once, you will see that the countries are added to the list again, so you end up with a list of 20 countries and not 10.

+ Add a block to, before adding the countries, `delete all` of the countries in the list. This will stop the countries from being added to the list more than once.

Let's make a custom block. This is a special block with a name, and we will be able to create a list of flags using only this one block, instead of having to use lots of blocks.

+ Call your costum block `Create flags list`, and drag all of the code (except the `When flag clicked` block) to become part of this new block.

[[[generic-scratch-make-block]]]

Your code for when the green flag is clicked should now look similar to this:

![Create flags list](images/create-flags-list.png)
