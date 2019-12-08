---
description: 在下一個頁面檢視上擷取 Analytics 變數的值。例如，您可以使用外掛程式，將上一個頁面檢視中的 s.pageName 值擷取到自訂流量變數中。您也可以選擇僅在指定的成功事件設定時才擷取先前值。
keywords: Analytics Implementation
subtopic: Plug-ins
title: getPreviousValue
topic: Developer and implementation
uuid: 20da7b4a-9820-4690-a1cc-d10b6dd627a7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getPreviousValue

在下一個頁面檢視上擷取 Analytics 變數的值。例如，您可以使用外掛程式，將上一個頁面檢視中的 s.pageName 值擷取到自訂流量變數中。您也可以選擇僅在指定的成功事件設定時才擷取先前值。

> [!NOTE]下列指示會要求您變更網站上的資料收集程式碼。此動作可能會影響到您網站上的資料收集，因此應由懂得使用及實施 [!DNL Analytics] 的開發人員執行。

## 外掛程式的程式碼與實施 {#section_92E94A96A4764113B5588F1B83E3DE2C}

**設定區段**: 此區段無需變更。

**外掛程式設定**

將下列程式碼放入 *`s_doPlugins()`* 函數中；此函數位於 *`s_code.js`檔案中標示為* Plugin Config *的區域中。*&#x200B;選擇一個自訂流量 (s.prop) 變數或一個自訂轉換 (s.eVar) 變數，用於持續值資料的擷取。此變數應為已使用管理控制台加以啟用，但目前未做任何其他用途的變數。您可以使用下列範例，並根據您的需求加以更新。

`s.prop1=s.getPreviousValue(s.pageName,'gpv_pn','event1');`

*`s.getPreviousValue`* 有三個引數:

1. 要從上一頁擷取的變數 (以上的 *`s.pageName`*)。
1. 用以儲存要擷取之值的 Cookie 名稱 (以上的 *`gpv_pn`*)。
1. 為了要觸發先前值的擷取而必須在頁面檢視上設定的事件 (以上的 *`event1`*)。若保留為空白或省略，外掛程式則會擷取所有頁面檢視上的先前值。

**外掛程式區段**: 將下列程式碼新增至 [!DNL s_code.js] 檔案中標示為 PLUGINS SECTION 的區域中。請勿對此部分的外掛程式程式碼進行任何變更。

```js
/* 
 * Plugin: getPreviousValue_v1.0 - return previous value of designated 
 * variable (requires split utility) 
 */ 
s.getPreviousValue=new Function("v","c","el","" 
+"var s=this,t=new Date,i,j,r='';t.setTime(t.getTime()+1800000);if(el" 
+"){if(s.events){i=s.split(el,',');j=s.split(s.events,',');for(x in i" 
+"){for(y in j){if(i[x]==j[y]){if(s.c_r(c)) r=s.c_r(c);v?s.c_w(c,v,t)" 
+":s.c_w(c,'no value',t);return r}}}}}else{if(s.c_r(c)) r=s.c_r(c);v?" 
+"s.c_w(c,v,t):s.c_w(c,'no value',t);return r}"); 
/* 
 * Utility Function: split v1.5 - split a string (JS 1.0 compatible) 
 */ 
s.split=new Function("l","d","" 
+"var i,x=0,a=new Array;while(l){i=l.indexOf(d);i=i>-1?i:l.length;a[x" 
+"++]=l.substring(0,i);l=l.substring(i+d.length);}return a"); 
```

**附註**

* 在部署至生產環境前，請務必對外掛程式安裝進行全面性的測試，以確保資料收集可如預期運作。
* 若任何指定的頁面上都沒有適用於所選變數的值存在，Cookie 中將會設定&#x200B;*no value*(沒有值)文字。
* 目前已為每個 Cookie 設定 30 分鐘的固定過期時間，且會在每次載入頁面時重新整理。外掛程式會在單次瀏覽期間運作。
* 由於在執行程式碼的外掛程式區段時必須呼叫函數，因此每當呼叫&#x200B;*`s.t()`* 或 *`s.tl()`* 時，就會執行程式碼。

* 選擇的變數應在呼叫 *`s.getPreviousValue`*.由於 *`s_doPlugins()`* 函數會在頁面上的變數填入後才執行，因此這個問題很少發生。只有在與此外掛程式搭配使用的變數在 *`s_doPlugins()`* 函數內填入時且在呼叫 *`s.getPreviousValue`* 後，才需要擔心這個問題。

