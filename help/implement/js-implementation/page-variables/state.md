---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# state

此 zip 和 state 變數均為轉換變數。


<!-- 

state.xml

 -->

它們與 eVar 的相同之處是都會擷取事件，但不像 eVar 一樣具有永久性。此&#x200B;*`zip`* 和 *`state`* 變數的行為類似於會立即過期的 eVar。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 50 位元組 | state | 轉換 &gt; 訪客資料 &gt; 訪客狀態 | "" |

由於 *`state`* 和 *`zip`* 變數會立即過期，因此與其相關聯的事件，將只有在其填入所在的相同頁面上引發的事件。例如，如果您使用 *`state`* 來比較依據州的轉換率，您應將 *`state`* 變數填充到結帳過程的每個頁面。針對轉換網站，Adobe 建議您以帳單地址作為郵遞區號的來源，但您也可選擇使用交貨地址 (假設該訂單只有一個交貨地址)。媒體網站可選擇使用  *`zip`* 和 *`state`* 進行註冊，或使用廣告點進追蹤。

**語法和可能的值** {#section_EDD1F5F9EDBC457898E61695F08C1744}

```js
s.state="state"
```

*`state`* 變數並沒有任何特殊值或格式的限制。除了標準變數限制以外，*`state`* 並無其他限制。

**範例** {#section_D181B163F79A41D199CA4C70765E583F}

```js
s.state="california" 
```

```js
s.state="prince edward island"
```

**組態設定** {#section_DB0D6DC3F4764AC59C11B10D27D2806C}

無

**缺陷、問題和提示** {#section_02F1620D0BB14AA6A838966FDB9A234F}

* 將 *`state`* 填入至有相關事件引發的每個頁面上 (如結帳程序的每個頁面)。
* *`zip`* 和 *`state`* 變數的作用與 eVar 相似，會在頁面檢視時過期。
