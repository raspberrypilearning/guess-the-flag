## एक नया राउंड शुरू करें

फिलहाल प्रश्नोत्तरी में केवल एक राउंड है, इसलिए प्रश्नोत्तरी लंबे समय तक नहीं चलती है। आप कई राउंड सेट करने जा रहे हैं।

--- task ---

एक नया `broadcast`{:class="block3events"} जो संदेश भेजता है 'राउंड शुरू करें'।

![झंडा स्प्राइट](images/flag-sprite.png)

```blocks3
broadcast (start the round v)
```

--- /task ---

--- task ---

जब मुझे 'राउंड प्रारंभ' प्राप्त होता है, तो `when I receive 'Start the round'`{:class="block3events"} ब्लॉक करें, और फिर हरे रंग के झंडे पर क्लिक करने पर `when green flag clicked`{:class = "block3events"} इस नए ब्लॉक के नीचे ब्लॉक करें।

![झंडा स्प्राइट](images/flag-sprite.png)

```blocks3
+ when I receive [start the round v]
set [score v] to [0]
create flag list :: custom
delete (all v) of [chosen flags v]
repeat (6)
    choose random flag :: custom
end
set [correct answer v] to (item (pick random (1) to (length of [chosen flags v])) of [chosen flags v])
clone flags :: custom
+ broadcast (announce country v)
```

--- /task ---

--- task ---

`set score to 0`{:class="block3variables"} ब्लॉक को निकालें और इसे वापस `when green flag clicked`{:class="block3control"} ब्लॉक के नीचे रखें। और फिर नए `broadcast`{:class="block3events"} ब्लॉक को उन दोनों के नीचे रखें।

![झंडा स्प्राइट](images/flag-sprite.png)

```blocks3
when green flag clicked
set [score v] to [0]
broadcast (start the round v)
```

--- /task ---

--- task ---

उत्तर सही है या नहीं की जाँच करने वाले कोड के बाद, एक और `broadcast`{:class="block3events"} ब्लॉक जोड़ें ताकि एक बार प्रश्न का उत्तर दे दिए जाने के बाद एक नया राउंड शुरू हो सके।

![झंडा स्प्राइट](images/flag-sprite.png)

```blocks3
when this sprite clicked
if <(costume [name v]) = (correct answer :: variables)> then
    change [score v] by [1]
    say [Correct] for (2) seconds
else
    say [Sorry, that was wrong] for (2) seconds
end
+ broadcast (start the round v)
```

--- /task ---

--- task ---

अपने खेल का परीक्षण करने के लिए हरे झंडे पर क्लिक करें। कोई राउंड खेलने के लिए किसी एक झंडे पर क्लिक करें। क्या आप यह देखते हैं कि अगला राउंड ठीक से सेट अप नहीं होता है?

![अगला राउंड काम नहीं करता](images/next-round-does-not-work.png)

--- /task ---

ऐसा इसलिए है क्योंकि गेम का दूसरा राउंड शुरू करने से पहले, गेम को पहले क्लोन किए गए झंडों को साफ करने की ज़रूरत होती है।

--- task ---

'साफ करें' नामक एक और नया `broadcast`{:class="block3events"} बनाएँ।

![झंडा स्प्राइट](images/flag-sprite.png)

```blocks3
broadcast (clean up v)
```

--- /task ---

--- task ---

फ्लैग स्प्राइट को सेट करें `delete this clone`{:class="block3control"} जब यह `clean up`{:class="block3events"} प्रसारण प्राप्त हो।

![झंडा स्प्राइट](images/flag-sprite.png)

```blocks3
when I receive [clean up v]
delete this clone
```

--- /task ---

--- task ---

`clean up`{:class="block3events"} प्रसारण ब्लॉक को ठीक ऊपर जहां खेल एक उत्तर देने के बाद एक नया दौर शुरू करता है वहां रखना है।

```blocks3
when this sprite clicked
create flags list  :: custom
if <(item (costume [number v]) of [flags v]) = (correct answer :: variables)> then
    say [Correct] for (2) seconds
    change [score v] by [1]
else
    say [Sorry, that was wrong] for (2) seconds
end
+ broadcast (clean up v)
broadcast (start the round v)
```

--- /task ---

--- task ---

अपने कोड का फिर से परीक्षण करें और जाँच करें कि आप कई राउंड खेल सकते हैं, और उत्तर सही होने पर आपका स्कोर बढ़ जाता है।

--- /task ---

--- task ---

सुनिश्चित करें कि आप `correct answer`{:class="block3variables"} वेरिएबल को छिपा देते हैं ताकि खिलाड़ी उसे न देख सके!

--- /task ---