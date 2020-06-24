## झंडों की सूची बनाएँ

--- task ---

कोड टैब पर क्लिक करें। `flags`{:class="block3variables"} नामक एक सूची है, जिसमें आप उन देशों के नाम संगृहीत करते हैं जिनके आपके गेम के लिए झंडे के परिधान हैं।

--- /task ---

--- task ---

दो और कोड ब्लॉक जोड़ें, आपने जो दो अन्य झंडे तैयार किए हैं उन दोनों में से प्रत्येक के लिए एक, इस तरह कुल मिलाकर दस ब्लॉक हैं जो दस-के-दस देशों को `flags`{:class="block3variables"} की सूची में जोड़ते हैं।

![झंडा स्प्राइट](images/flag-sprite.png)

```blocks3
add [Country] to [flags v]
```

--- /task ---

--- task ---

--- task ---हरे झंडे पर क्लिक करें और जाँच करें कि सूची में देश दिखाई देते हैं।

--- /task ---

यदि आप हरे झंडे को एक से अधिक बार दबाते हैं, तो सूची में देश फिर से जुड़ जाते हैं, और परिणामस्वरूप 10 देशों की सूची के बजाय 20 देशों की सूची बन जाती है।

--- task ---

--- task ---देशों के नाम जोड़ने से पहले, सभी देशों के नाम हटाने के लिए कोड के आरंभ में `delete all`{:class="block3variables"} ब्लॉक जोड़ें। यह देशों को सूची में एक से अधिक बार जोड़े जाने से रोक देगा।

![झंडा स्प्राइट](images/flag-sprite.png)

```blocks3
when green flag clicked
+ delete (all v) of [flags v]
add [Japan] to [flags v]
add [Belgium] to [flags v]
add [Italy] to [flags v]
add [Turkey] to [flags v]
add [Denmark] to [flags v]
add [Chile] to [flags v]
add [Botswana] to [flags v]
add [Bangladesh] to [flags v]
add [Ghana] to [flags v]
add [Luxembourg] to [flags v]
```

--- /task ---

इसके बाद, एक कस्टम ब्लॉक बनाएँ। कस्टम ब्लॉक नाम वाला एक विशेष ब्लॉक होता है। आप जो कस्टम ब्लॉक बनाएँगे उससे आप बहुत सारे ब्लॉकों के बजाय केवल इसी एक ब्लॉक का उपयोग करके झंडों की एक सूची बना सकेंगे।

--- task ---

**मेरे ब्लॉक** पर क्लिक करें और फिर **एक ब्लॉक बनाएँ** पर। अपने कस्टम ब्लॉक को `create flag list`{:class="block3myblocks"} नाम दें।

![झंडा स्प्राइट](images/flag-sprite.png)

![एक ब्लॉक जोड़ें](images/add-block.png)

--- /task ---

--- task ---

`when flag clicked`{:class="block3events"} ब्लॉक के नीचे से सभी कोड ड्रैग करके नए `create flag list`{:class="block3myblocks"} ब्लॉक के नीचे ले जाएँ।

```blocks3
define create flag list
delete (all v) of [flags v]
add [Japan] to [flags v]
add [Belgium] to [flags v]
add [Italy] to [flags v]
add [Turkey] to [flags v]
add [Denmark] to [flags v]
add [Chile] to [flags v]
add [Botswana] to [flags v]
add [Bangladesh] to [flags v]
add [Ghana] to [flags v]
add [Luxembourg] to [flags v]
```

--- /task ---

--- task ---

`when flag clicked`{:class="block3events"} ब्लॉक के नीचे, एक नया ब्लॉक `create flag list`{:class="block3myblocks"} जोड़ें।

![झंडा स्प्राइट](images/flag-sprite.png)

```blocks3
when green flag clicked
create flag list :: custom
```

--- /task ---