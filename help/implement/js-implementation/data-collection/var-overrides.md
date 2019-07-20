---
description: 「變數覆寫」可讓您變更單一追蹤或追蹤連結呼叫的變數值。
keywords: Analytics 實施
seo-description: 「變數覆寫」可讓您變更單一追蹤或追蹤連結呼叫的變數值。
seo-title: 變數覆寫
solution: Analytics
subtopic: 變數
title: 變數覆寫
topic: 開發人員和實施
uuid: ec09ae8-b9-b9 df-426f-8065-42b4518 e6 f5 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 變數覆寫

「變數覆寫」可讓您變更單一追蹤或追蹤連結呼叫的變數值。

To override variables, create a new object, assign variable values, and pass this object as the first parameter to `s.t()`, or as the fourth parameter to `s.tl()`:

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

