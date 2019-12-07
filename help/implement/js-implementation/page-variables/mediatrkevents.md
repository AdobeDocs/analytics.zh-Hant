---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# media.trackEvents

 變數可識別哪些事件應隨媒體點擊而傳送。


<!-- 

media_trackEvents.xml

 -->

此變數僅適用於 JavaScript 和 [!UICONTROL ActionSource]。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | s.Media.trackEvents="None" |

**語法和可能的值** {#section_66A978EF56914BEAAE73359A268A1B4A}

事件名稱，例如 event1 或 purchase。

**範例** {#section_140A55D80EA24011954F9383CF312237}

```js
s.Media.trackEvents="event1,purchase"
```

**缺陷、問題和提示** {#section_030B11C64EE84D46A85CA550DB732D28}

請確實在每次填入此變數時，為 [!UICONTROL trackVars] 填入「事件」。
