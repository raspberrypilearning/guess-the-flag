## प्रश्न पूछें

आइए हम खिलाड़ी से किसी देश विशेष के झंडे का नाम बताने के लिए कहें।

\--- task \--- झंडा स्प्राइट में, `broadcast the message`{:class="block3events"} झंडे को क्लोन करने वाले ब्लॉक के तुरंत बाद 'देश की घोषणा करें'।

![झंडा स्प्राइट](images/flag-sprite.png)

```blocks3
when green flag clicked
create flag list :: custom
delete (all v) of [chosen flags v]
repeat (6)
    choose random flag :: custom
end
set [correct answer v] to (item (pick random (1) to (length of [chosen flags v])) of [chosen flags v])
clone flags :: custom
+ broadcast (announce country v)

```

[[[generic-scratch3-broadcast-message]]] \--- /task \---

\--- task \--- अपना प्रश्नोत्तरी मास्टर स्वयं बनने के लिए अपनी पसंद का एक नया स्प्राइट जोड़ें। इस उदाहरण में प्रश्नोत्तरी मास्टर एब्बी नामक स्प्राइट है।

![एब्बी स्प्राइट](images/bear-sprite.png)

\--- /task \---

\--- task \--- प्रश्नोत्तरी मास्टर स्प्राइट के लिए कोई कोड जोड़ें ताकि, जब स्प्राइट को `announce country`{:class="block3events" प्रसारण प्राप्त होता है, तो यह खिलाड़ी को बताता है कि उस देश के नाम पर क्लिक करें जो वेरिएबल `correct answer`{:class="block3variables"} में संगृहीत है।

![पात्र स्प्राइट](images/char-sprite.png)

\--- hints \--- \--- hint \--- `When I receive`{:class="block3events"} the broadcast, `say`{:class="block3looks"} 'click on `correct answer`{:class="block3variables"}'. \--- /hint \---

\--- hint \--- ये वे ब्लॉक हैं जिनकी आपको आवश्यकता है:

```blocks3
(join [click on] [])

(correct answer)

say [] for (2) seconds

when I receive [announce country v]
```

\--- /hint \---

\--- hint \--- यहाँ दिखाया गया है कि आपका कोड कैसा दिखना चाहिए:

```blocks3
when I receive [announce country v]
say (join [click on] (correct answer :: variables)) for (2) seconds
```

\--- /hint \---

\--- /hints \--- \--- /task \---