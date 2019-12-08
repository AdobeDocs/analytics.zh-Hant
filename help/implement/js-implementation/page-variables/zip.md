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


# zip

此 zip 和 state 變數均為轉換變數。


<!-- 

zip.xml

 -->

它們與 eVar 的相同之處是都會擷取事件，但不像 eVar 一樣具有永久性。此&#x200B;*`zip`* 和 *`state`* 變數的行為類似於會立即過期的 eVar。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 50 位元組 | zip | 轉換 &gt; 訪客資料 &gt; 郵遞區號 | "" |

Since the *`state`* and *`zip`* variables expire immediately, the only events associated with them are events fired on the same page that are populated. 舉例來說，如果您使用 *`zip`* 來比較依據郵遞區號的轉換率，則應將 *`zip`* 填入至結帳過程的每個頁面上。Adobe 建議您以帳單地址作為郵遞區號的來源。您也可選擇使用交貨地址 (假設該訂單只有一個交貨地址)。媒體網站可選擇使用  *`zip`* 和 *`state`* 進行註冊，或使用廣告點進追蹤。

**語法和可能的值** {#section_5EDCFCAC8FC241D1B4CC777996858CD7}

```js
s.zip="zip_code"
```

*`zip`* 變數並沒有任何值或格式的限制。除了標準變數限制以外，*`zip`* 並無其他限制。

**範例** {#section_F25C0D0CC3C04B81892A662CD605C593}

```js
s.zip="92806"
```

```js
s.zip="92806-4115"
```

**組態設定** {#section_7987084EECC34DD38B643B94F82385CA}

無

**缺陷、問題和提示** {#section_E86774D5CE8B40EFA36353CDEE3A84D0}

* 請將[!UICONTROL 郵遞區號]填入至有相關事件引發的每個頁面上 (如結帳程序的每個頁面)。
* *`zip`* 和 *`state`* 變數的作用與 eVar 相似，會在頁面檢視時過期。

