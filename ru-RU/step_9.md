## Добавить счет

--- task ---

Создай новую переменную с именем `счет`{:class="block3variables"} и установи счет `0`{:class="block3variables"} при нажатии зеленого флажка.

![Спрайт флага](images/flag-sprite.png)

```blocks3
when green flag clicked
задать [счет v] значение [0]
```

--- /task ---

--- task ---

Добавляй `1`{:class="block3variables"} к счету каждый раз, когда игрок дает правильный ответ.

![Спрайт флага](images/flag-sprite.png)

```blocks3
когда спрайт нажат
если <(костюм [имя v]) = (правильный ответ :: variables)> , то 
+ изменить [счет v] на [1]
  say [Правильно] for (2) secs
иначе 
  say [К сожалению, неправильно] for (2) secs
конец
```

--- /task ---