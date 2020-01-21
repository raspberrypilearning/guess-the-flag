## सही उत्तर चुनें

अब क्योंकि आपके पास छह चुने हुए झंडों की एक सूची है, तो चुनें कि इस बार उनमें से सही उत्तर कौन सा होगा।

\--- task \---

Create a new variable called `correct answer`{:class="block3variables"}.

\--- /task \---

\--- task \---

After the six flags are chosen, set the `correct answer`{:class="block3variables"} variable to be a random item from the `chosen flags`{:class="block3variables"} list.

![Flag sprite](images/flag-sprite.png)

```blocks3
when green flag clicked
create flag list :: custom
delete (all v) of [chosen flags v]
repeat (6)
    choose random flag :: custom
end
+ set [correct answer v] to (item (pick random (1) to (length of [chosen flags v]) ) of [chosen flags v])
```

\--- /task \---