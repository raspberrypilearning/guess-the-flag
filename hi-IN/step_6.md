## झंडे दिखाएँ

प्रश्नोत्तरी में भाग लेने वाले व्यक्ति को `chosen flags`{:class="block3variables"} सूची में झंडों के चित्रों को देखने की जरूरत होती है।

--- task ---

एक और कस्टम ब्लॉक बनाएँ, और उसका नाम `clone flags`{:class="block3myblocks"} रखें।

![झंडा स्प्राइट](images/flag-sprite.png)

```blocks3
define clone flags
```

--- /task ---

यह कस्टम ब्लॉक झंडा स्प्राइट को छह बार क्लोन करेगा, प्रदर्शित किए जाने वाले हर झंडे के लिए एक बार।

पहला झंडा स्टेज के ऊपरी बाएँ कोने में प्रदर्शित होना चाहिए।

--- task ---

आपके `clone flags`{:class="block3myblocks"} ब्लॉक के लिए निर्देशों के एक हिस्से के रूप में, झंडा स्प्राइट को दृश्यमान बनाएँ और स्प्राइट को यह बताने के लिए `go to`{:class="block3motion"} ब्लॉक जोड़ें कि स्टेज के ऊपरी बाएँ कोने में निर्देशांक `-170`{:class="block3motion"}, `120`{:class="block3motion"} पर दिखाएँ।

![झंडा स्प्राइट](images/flag-sprite.png)

```blocks3
define clone flags
show
go to x: (-170) y: (120)
```

--- /task ---

--- task ---

उस कोड के नीचे, एक लूप जोड़ें जो छह बार दोहराता है।

![झंडा स्प्राइट](images/flag-sprite.png)

लूप के अंदर, स्प्राइट के परिधान को `chosen flags`{:class="block3variables"} सूची में पहले झंडे में बदलने के लिए, और स्प्राइट को क्लोन करने के लिए कोड ब्लॉक जोड़ें। फिर, सूची में से पहले झंडे को हटाने के लिए, और स्प्राइट को दूसरे झंडे की स्थिति में ले जाने के लिए `x`{:class="block3motion"} निर्देशांक में `110`{:class="block3motion"} जोड़ने के लिए कोड ब्लॉक जोड़ें।

--- hints ---
 --- hint ---

`Repeat`{:class="block3control"} का छह बार उपयोग करें: `Switch costume`{:class="block3looks"} का `first item in chosen flags`{:class="block3variables"} में। `Clone the sprite`{:class="block3control"}। `first item in chosen flags`{:class="block3variables"} के लिए `Delete`{:class="block3variables"} का उपयोग करें। `Move right 110`{:class="block3motion"}.

--- /hint ---

--- hint ---

आपको इस कोड ब्लॉक की ज़रुरत पड़ेगी:

```blocks3
(item (1) of [chosen flags v])

change x by (110)

create clone of (myself v)

switch costume to ( v)

delete (1) of [chosen flags v]

repeat (6)
end
```

--- /hint ---

--- hint ---

आपका कोड ऐसा दिखना चाहिए:

```blocks3
define clone flags
show
go to x: (-170) y: (120)
+ repeat (6)
    switch costume to (item (1) of [chosen flags v])
    create clone of (myself v)
    delete (1) of [chosen flags v]
    change x by (110)
end
```

--- /hint ---

--- /hints --- --- /task ---

--- task ---

अपने `clone flags`{:class="block3myblocks"} ब्लॉक को उस कोड के अंत में जोड़ें जो हरे झंडे को क्लिक करने के बाद चलता है।

![झंडा स्प्राइट](images/flag-sprite.png)

```blocks3
when green flag clicked
create flag list :: custom
delete (all v) of [chose flags v]
repeat (6)
  choose random flag :: custom
end
+ clone flags :: custom
```

--- /task ---

--- task ---

अपना कोड चलाएँ। ध्यान दें कि अलग-अलग झंडे दिखाई देते हैं, लेकिन कुछ स्टेज के किनारे से कटे हुए हैं।

![झंडे स्क्रीन से बाहर चले जाते हैं](images/flags-off-the-screen.png)

--- /task ---

पूरे छह झंडे एक पंक्ति में लगाने के बजाय, तीन-तीन झंडों की दो पंक्तियाँ बनाएँ।

--- task ---

--- task ---यदि `chosen flags`{:class="block3variables"} सूची में तीन झंडे बच जाते है तो झंडा स्प्राइट (sprite) को एक पंक्ति नीचे ले जाने के लिए `clone flags`{:class="block3myblocks"} ब्लॉक के `repeat`{:class="block3control"} लूप के भीतर कोई कोड जोड़ें।

![झंडा स्प्राइट](images/flag-sprite.png)

आप एक अन्य `go to`{:class="block3motion"} ब्लॉक का उपयोग करके और `x`{:class="block3motion"} निर्देशांक को स्टार्टिंग प्वाइंट के समान रखकर स्प्राइट को एक पंक्ति नीचे ले जा सकते हैं, लेकिन इसे नीचे की ओर ले जाने के लिए `y`{:class="block3motion"} निर्देशांक को कम करना होगा।

```blocks3
define clone flags
show
go to x: (-170) y: (120)
repeat (6)
    switch costume to (item (1) of [chosen flags v])
    create clone of (myself v)
    delete (1) of [chosen flags v]
    change x by (110)
+   if <(length of [chosen flags v]) = [3]> then
        go to x: (-170) y: (50)
    end
end
```

--- /task ---

--- task ---

हरे झंडे पर क्लिक करें और जांचें कि झंडे दो पंक्तियों में प्रदर्शित होते हैं।

--- /task ---

ऐसा लगता है कि अंतिम झंडा दो बार प्रदर्शित किया गया है। ऐसा इसलिए है क्योंकि मूल झंडा स्प्राइट अभी भी अंत में दिखाई दे रहा है।

--- task ---

मूल स्प्राइट (sprite) को छिपाने के लिए `clone flags`{:class="block3myblocks"} ब्लॉक के भीतर कोड के अंत में एक `hide`{:class="block3looks"} ब्लॉक जोड़ें।

![झंडा स्प्राइट](images/flag-sprite.png)

--- /task ---

यदि आप चाहते हैं, तो आप कोशिश कर सकते हैं कि झंडा स्प्राइट एक-एक करके दिखाई दे या हर बार जब झंडा दिखाई दे तो कोई ध्वनि (उदाहरण के लिए, पॉप) बजाई जाए।