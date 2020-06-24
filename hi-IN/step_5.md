## सही उत्तर चुनें

अब क्योंकि आपके पास छह चुने हुए झंडों की एक सूची है, तो चुनें कि इस बार उनमें से सही उत्तर कौन सा होगा।

\--- task \---

एक नया वेरिएबल बनाएं जिसका नाम ` correct answer ` {:class = "block3variables"}।

\--- /task \---

\--- task \---

छह झंडे चुन लेने के बाद, `correct answer`{:class="block3variables"} वेरिएबल को `chosen flags`{:class="block3variables"} सूची में से एक यादृच्छिक आइटम के रूप में सेट करें।

![झंडा स्प्राइट](images/flag-sprite.png)

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