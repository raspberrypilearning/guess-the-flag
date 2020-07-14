## Zeige die Flaggen

Die Person, die am Quiz teilnimmt, muss die Bilder der Flaggen in der `ausgewählte Flaggen`{:class="block3variables"} Liste sehen.

--- task ---

Erstelle einen weiteren neuen Block und nenne diesen `Flaggen klonen`{:class="block3myblocks"}.

![Flaggenfigur](images/flag-sprite.png)

```blocks3
define Flaggen klonen
```

--- /task ---

Dieser neue Block klont die Flaggenform sechs Mal, einmal für jede Flagge, die angezeigt werden soll.

Die erste Flagge sollte in der oberen linken Ecke des Bereiches angezeigt werden.

--- task ---

Als Teil der Anweisungen für deinen `Flaggen klonen`{:class="block3myblocks"} Block, mache die Flaggenfigur sichtbar und füge einen `gehe zu`{:class="block3motion"} Block hinzu, um der Figur anzuweisen, an den Koordinaten `-170`{:class="block3motion"}, `120`{:class="block3motion"} in der oberen linken Ecke des Bereiches angezeigt zu werden.

![Flaggenfigur](images/flag-sprite.png)

```blocks3
define Flaggen klonen
show
go to x: (-170) y: (120)
```

--- /task ---

--- task ---

Füge unter diesem Code eine Schleife hinzu, die sich sechsmal wiederholt.

![Flaggenfigur](images/flag-sprite.png)

Füge innerhalb der Schleife Codeblöcke hinzu, um das Figurenkostüm auf die erste Flagge in der `ausgewählte Flaggen`{:class="block3variables"} Liste zu setzen und klone dann die Figur. Füge dann Code-Blöcke hinzu, um die erste Flagge aus der Liste zu löschen und füge `110`{:class="block3motion"} zur `x`{:class="block3motion"} Koordinate hinzu, um die Figur zur Position der zweiten Flagge zu bewegen.

--- hints ---
 --- hint ---

`Wiederhole`{:class="block3control"} sechs Mal: `Kostüm wechseln`{:class="block3looks"} zum `ersten Element in ausgewählte Flagge`{:class="block3variables"}. `Klone die Figur`{:class="block3control"}. `Lösche`{:class="block3variables"} das `erste Element in ausgewählte Flaggen`{:class="block3variables"}. `Nach rechts bewegen 110`{:class="block3motion"}.

--- /hint ---

--- hint ---

Hier sind die Codeblöcke, die du brauchst:

```blocks3
(item (1) of [ausgewählte Flaggen v])

change x by (110)

create clone of (myself v)

switch costume to ( v)

delete (1) of [ausgewählte Flaggen v]

repeat (6)
end
```

--- /hint ---

--- hint ---

So sollte dein Code aussehen:

```blocks3
define Flaggen klonen
show
go to x: (-170) y: (120)
+ repeat (6)
    switch costume to (item (1) of [ausgewählte Flaggen v])
    create clone of (myself v)
    delete (1) of [ausgewählte Flaggen v]
    change x by (110)
end
```

--- /hint ---

--- /hints --- --- /task ---

--- task ---

Füge deinen `Flaggen klonen`{:class="block3myblocks"} Block an das Ende des Codes, der ausgeführt wird, wenn die grüne Fahne angeklickt wird.

![Flaggenfigur](images/flag-sprite.png)

```blocks3
when green flag clicked
erstelle Flaggen-Liste :: custom
delete (all v) of [ausgewählte Flaggen v]
repeat (6)
  wähle zufällige Flagge :: custom
end
+ Flaggen klonen :: custom
```

--- /task ---

--- task ---

Führen deinen Code aus. Du siehst, dass die verschiedenen Flags angezeigt werden, einige jedoch am Rand des Bereiches abgeschnitten sind.

![Flaggen verschwinden vom Bildschirm](images/flags-off-the-screen.png)

--- /task ---

Anstatt alle sechs Flaggen in eine Reihe zu setzen, mache zwei Reihen mit drei Flaggen.

--- task ---

Füge ein bisschen Code in die `wiederhole`{:class="block3control"} Schleife des `Flaggen klonen`{:class="block3myblocks"} Blocks, um die Flagge um eine Reihe nach unten zu verschieben, wenn in der `ausgewählte Flaggen`{:class="block3variables"} Liste noch drei Flaggen vorhanden sind.

![Flaggenfigur](images/flag-sprite.png)

Du kannst die Figur mit einem anderen `gehe zu`{:class="block3motion"} Baustein nach unten bewegen indem du die `x`{:class="block3motion"} Koordinate gleich lässt, aber die `y`{:class="block3motion"} Koordinate verringerst.

```blocks3
define Flaggen klonen
show
go to x: (-170) y: (120)
repeat (6)
    switch costume to (item (1) of [ausgewählte Flaggen v])
    create clone of (myself v)
    delete (1) of [ausgewählte Flaggen v]
    change x by (110)
+   if <(length of [ausgewählte Flaggen v]) = [3]> then
        go to x: (-170) y: (50)
    end
end
```

--- /task ---

--- task ---

Klicke auf die grüne Flagge und überprüfe, ob die Flaggen in zwei Reihen angezeigt werden.

--- /task ---

Es sieht so aus, als sei die letzte Flagge zweimal angezeigt. Das liegt daran, dass die ursprüngliche Flaggenfigur am Ende noch sichtbar ist.

--- task ---

Fügen einen `verbergen`{:class="block3looks"} Block am Ende des Codes innerhalb des `Flaggen klonen`{:class="block3myblocks"} Blocks hinzu, um die ursprüngliche Figur auszublenden.

![Flaggenfigur](images/flag-sprite.png)

--- /task ---

Wenn du möchtest, kannst du versuchen, die Flaggenfiguren einzeln erscheinen zu lassen oder einen Ton abzuspielen (z.B . ein Pop) jedes Mal, wenn eine Flagge erscheint.