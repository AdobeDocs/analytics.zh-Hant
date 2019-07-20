---
description: 取得十分之一秒的頁面載入時間，並允許您將值儲存至 prop、eVar 及/或數值事件。
keywords: Analytics 實施
seo-description: 取得十分之一秒的頁面載入時間，並允許您將值儲存至 prop、eVar 及/或數值事件。
seo-title: getLoadTime
solution: Analytics
title: getLoadTime
topic: 開發人員和實施
uuid: 5d26a69b-cbde-4be1-bac1-5ee8 a4 e55 ca3
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getLoadTime

取得十分之一秒的頁面載入時間，並允許您將值儲存至 prop、eVar 及/或數值事件。

若要使用此外掛程式，需先插入函數程式碼，然後在 [!DNL s_code.js] 檔案中呼叫函數兩次。一次在檔案開頭，另一次在 `doPlugins` 區段中。此外掛程式是特意不定義為 s 物件的方法。這麼做會增加計算的頁面載入時間。

>[!NOTE]
>
>下列指示要求您變更網站上的資料收集代碼。此動作可能會影響到您網站上的資料收集，因此應由懂得使用及實施 [!DNL Analytics] 的開發人員執行。

## 外掛程式的程式碼與實施 {#section_968AC379C3004C359A85AFED5A48D5AE}

**新增函數**

將下列 `s_getLoadTime` 函數的定義新增至 [!DNL s_code.js] 中，"DO NOT ALTER ANYTHING BELOW THIS LINE" 區段前的任意位置:

```js
function s_getLoadTime(){if(!window.s_loadT){var b=new Date().getTime(),o=window.performance?performance.timing:0,a=o?o.requestStart:window.inHeadTS||0;s_loadT=a?Math.round((b-a)/100):''}return s_loadT}
```

**進行初始函數呼叫**

Add a call to `s_getLoadTime()` near the beginning of [!DNL s_code.js], outside of any function.

**進行最終函數呼叫**

Add another call to `s_getLoadTime()` in the `s_doPlugins()` function, saving the returned value in a prop, eVar, and/or a numeric event.

用法範例 1 - 將頁面載入時間儲存至 prop10 和 eVar20:

```js
s.eVar20=s.prop10=s_getLoadTime();
```

用法範例 2 - 將頁面載入時間儲存至 numeric event99:

```js
if(s_getLoadTime())s.events=s.apl(s.events,'event90='+s_getLoadTime(),',',1);
```

**(選用) 新增舊版瀏覽器的支援**

若要支援不提供 [window.performance.timing](https://www.html5rocks.com/en/tutorials/webperformance/basics/) 屬性之舊版瀏覽器的支援，請在頁面 HTML 的開頭處、於叫用 .js、.css 或其他檔案之前的 HEAD 區段中，加入下列行:

```
<script type="text/javascript">var inHeadTS=(new Date()).getTime();</script>
```

