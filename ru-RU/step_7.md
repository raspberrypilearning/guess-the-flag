## Задай вопрос

Давай попросим игрока назвать флаг определенной страны.

--- task ---

В спрайте флага `передайте сообщение`{:class="block3events"} 'назвать страну' сразу после блока, который клонирует флаги.

![Спрайт флага](images/flag-sprite.png)

```blocks3
when green flag clicked
создать список флагов :: custom
delete (all v) of [выбранные флаги v]
repeat (6)
    выбрать случайный флаг :: custom
end
set [правильный ответ v] to (item (pick random (1) to (length of [выбранные флаги v])) of [выбранные флаги v])
флаги-клоны :: custom
+ broadcast (назвать страну v)

```

[[[generic-scratch3-broadcast-message]]]

--- /task ---

--- task ---

Добавь новый спрайт по твоему выбору, который будет вести викторину. Ведущий викторины в примере - это спрайт по имени Эбби.

![Спрайт Эбби](images/bear-sprite.png)

--- /task ---

--- task ---

Добавь код в спрайт ведущей викторины, чтобы, когда спрайту передавалось `назвать страну`{:class="block3events"}, она говорила игроку нажать на название страны, которое хранится в переменной `правильный ответ`{:class="block3variables"}.

![Спрайт персонажа](images/char-sprite.png)

--- hints ---
 --- hint ---

`Когда я получу`{:class="block3events"} передачу, `сказать`{:class="block3looks"} 'нажать на `правильный ответ`{:class="block3variables"}'.

--- /hint ---

--- hint ---

Вот блоки кода, которые тебе нужны:

```blocks3
(join [нажать на] [])

(правильный ответ)

say [] for (2) seconds

when I receive [назвать страну v]
```

--- /hint ---

--- hint ---

Так должен выглядеть твой код:

```blocks3
when I receive [назвать страну v]
say (join [нажать на] (правильный ответ :: variables)) for (2) seconds
```

--- /hint ---

--- /hints --- --- /task ---