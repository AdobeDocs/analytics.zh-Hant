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


# s_objectID

此變數是應在連結的 [!UICONTROL onClick] 事件中設定的全域變數。


<!-- 

s_objectID.xml

 -->

透過為頁面上的連結或連結位置建立唯一的物件 ID，可改善訪客活動追蹤，或使用 [!UICONTROL Activity Map] 來報告連結類型或位置，而不是連結 URL。

> [!NOTE] 搭配使用s_objectID和 [Activity Map時，需要結尾分號(;)](https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/activitymap-link-tracking-use-case.html)。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 100 位元組 | OID | [!UICONTROL Activity Map], [!UICONTROL ClickMap] | 被點按連結的絕對 URL |

使用 s_objectID 有三個普遍原因。*`s_objectID`*:

* 彙總一天內經常變更的訪客活動。
* 區隔 [!UICONTROL Activity Map] 結合的連結活動。
* 改善 [!UICONTROL Activity Map] 資料報表的正確性。

**彙總高度動態連結的點按數** {#section_BA730A0393B149DDBCAA272C3C23A1C5}

如果您的網站極為動態，且某些頁面上的連結會一整天不斷變更，您可使用 *`s_objectID`* 識別頁面上的連結位置。舉例來說，如果將 *`s_objectID`* 設為「左上角 1」或「左上角 2」(這表示頁面左上角的第一個連結)，則顯示於該位置的所有連結 (或已將 *`s_objectID`* 設為同一個值的連結) 會與訪客點按對映一起回報。如果您沒有使用 *`s_objectID`*，雖可檢視特定連結的點按次數，但將無法清楚瞭解網站上的訪客對該位置上所有其他連結的使用情形。

**區隔合併的點按數** {#section_1AE91FB8A2D3423CBE064ACF02FEEA47}

如果網站上的 *`pageName`* 變數是用來顯示訪客正在檢視的區段或範本 (而不是訪客正在檢視的特定頁面)，您可能會想要使用 *`s_objectID`*，以區隔該頁面範本的多個版本上顯示的連結。例如，若您的網站上有一個適用於所有產品的範本頁面，則所有頁面上都可能會有從該範本連至首頁和搜尋方塊的連結。若您想依個別產品來檢視這些連結的使用情形 (而不依照範本)，您可以為  *`s_objectID`* 填入產品特定值，例如 "prod 123789 home page" 或 "prod 123789 search"。完成後，[!UICONTROL Activity Map] 即會根據個別產品來報告這些連結。

**改善[!UICONTROL Activity Map]正確性** {#section_08B3406821294DCCABEEB99C90CF5C52}

在某些情況下，Internet Explorer、Firefox、Netscape、Opera 與 Safari 以外的瀏覽器都不會列入報表中。儘管所占比例較小，但它確實占去了某些點按和其他度量。在連結內使用 *`s_objectID`* 明確加以識別，可解決瀏覽器報表問題。以下是如何更新連結以使用 *`s_objectID`* 的範例:

```js
<a href="/art.jsp?id=559" onClick="s_objectID='top left 1';">Article 559</a> 
<a href="/home.jsp" onClick="s_objectID='prod 123789 home page';">Home</a> 
```

**語法和可能的值** {#section_85841DF9F06A4680953D9B2A884A1A5A}

s_objectID 可包含任何文字識別碼。

```js
s_objectID="unique_id" 
```

除了標準變數限制以外，*`s_objectID`* 並無其他限制。

**範例** {#section_33F119D532CA4ACAA3426253C42030BB}

```js
s_objectID="top left 2" 
```

```js
s_objectID="prod 123789 search"
```

**組態設定** {#section_95396657D55B41ECB66B83D0534EA827}

無
