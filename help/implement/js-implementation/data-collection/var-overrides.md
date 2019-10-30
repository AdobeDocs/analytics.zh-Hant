---
description: 「變數覆寫」可讓您變更單一追蹤或追蹤連結呼叫的變數值。
keywords: Analytics 實作
seo-description: 「變數覆寫」可讓您變更單一追蹤或追蹤連結呼叫的變數值。
seo-title: 變數覆寫
solution: Analytics
subtopic: 變數
title: 變數覆寫
topic: 開發人員和實作
uuid: 3ec09ae8-b9df-426f-8065-42b4518e6c5f
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 變數覆寫

「變數覆寫」可讓您變更單一追蹤或追蹤連結呼叫的變數值。

若要覆寫變數，請建立新物件、指派變數值，然後將此物件傳入做為 `s.t()` 的第一個參數，或做為 `s.tl()` 的第四個參數:

```js
s.eVar1="one"; 
s.eVar2="two"; 
s.eVar3="three"; 
  
overrides = new Object(); 
overrides.eVar1="1_one"; 
overrides.eVar2=""; 
  
s.t(overrides);  
// values passed: eVar1="1_one", eVar2="", eVar3="three"
```

```js
s.linkTrackVars="eVar1,eVar2,eVar3,events"; 
s.eVar1="one"; 
s.eVar2="two"; 
s.eVar3="three"; 
 
overrides = new Object(); 
overrides.eVar1="1_one"; 
overrides.eVar2=""; 
 
s.tl(this,'e','AnotherSite',overrides,'navigate')  
// values passed: eVar1="1_one", eVar2="", eVar3="three"
```

