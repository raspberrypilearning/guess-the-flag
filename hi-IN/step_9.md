## स्कोर जोड़ें

--- task ---

`score`{:class="block3variables"} नामक एक नया वेरिएबल बनाएँ और जब हरे झंडे को क्लिक किया जाए तो स्कोर को `0`{:class="block3variables"} पर सेट करें।

![झंडा स्प्राइट](images/flag-sprite.png)

```blocks3
when green flag clicked
+ set [score v] to [0]
```

--- /task ---

--- task ---

हर बार जब खिलाड़ी सही उत्तर देता है तो स्कोर में `1`{:class="block3variables"} जोड़ें।

![झंडा स्प्राइट](images/flag-sprite.png)

```blocks3
when this sprite clicked
if <(costume [name v]) = (correct answer :: variables)> then
+ change [score v] by [1]
    say [Correct] for (2) seconds
else
    say [Sorry, that was wrong] for (2) seconds
end
```

--- /task ---