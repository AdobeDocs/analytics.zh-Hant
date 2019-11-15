---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.linkTrackVars

 變數是以逗號分隔，隨自訂、退出和下載連結而傳送的變數清單。

The [`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) parameter should include each variable that you want to track with every file download, exit link, and custom link.

The settings for `linkTrackVars` and `linkTrackEvents` within the JS file affect every file download, exit link, and custom link. 若將變數 (或事件) 套用至現行頁面，而不是特定的檔案下載、退出連結或自訂連結，每個變數和事件的例項數可能會不實膨脹。

為確保以自訂連結代碼設定正確的變數，Adobe建議 `linkTrackVars` 在自 `linkTrackEvents` 訂連結代碼內設定，如下所示：

```js
<a href="index.html" onClick=" 
var s=s_gi('rsid'); 
s.linkTrackVars='prop1,prop2,eVar1,eVar2,events'; 
s.linkTrackEvents='event1'; 
s.prop1='Custom Property of Link'; 
s.events='event1'; 
s.tl(this,'o','Link Name'); 
">My Page 
```

在上述範例中，prop1的值是在自訂連結程式碼本身內設定。 prop2 的值則來自變數的現行值，如頁面上所設定。

The values of `linkTrackVars` and `linkTrackEvents` override the settings in the JS file and ensure only the variables and events specified in the custom link code are set for the specific link.

*注意：如果`linkTrackVars`(或`linkTrackEvents`)為null（或空字串，例如""），則會追蹤為目前頁面定義的所有Analytics變數（或事件）。 換言之，所有具有值的變數都會隨連結資料傳送。 這很可能會誇大每個變數的例項。 為避免與其他變數相關聯的例項或頁面檢視膨脹，Adobe 建議在用於連結追蹤之連結的`linkTrackVars`onClick`linkTrackEvents`事件中填入[!UICONTROL 和]。*

所有應隨連結資料 (自訂、退出和下載連結) 傳送的變數，都應列在 `linkTrackVars` 中。若已使用 `linkTrackEvents`，則 `linkTrackVars` 應包含「事件」。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 任何 | "無" |

When populating `linkTrackVars`, do not use the 's.' prefix for variables. 例如，您應以「prop1」填入 `linkTrackVars`，而不是以「s.prop1」填入。以下範例說明應如何使用 `linkTrackVars`。

```js
s.linkTrackVars="eVar1,events" 
s.linkTrackEvents="event1" 
s.events="event1" 
s.eVar1="value A" 
s.eVar2="value B" 
s.t() // eVar1, event1 and event2 are recorded 
<a href="https://google.com">event1 and eVar1 are recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.eVar1='value C';s.events='';s.tl(this,'o')">eVar1 is recorded</a> 
```

由於 google.com 的連結是退出連結 (除非您正在使用 Google)，event1 和 eVar1 會隨退出連結資料傳送，而增加與 eVar1 相關聯的例項數和 event1 的引發次數。在 [!DNL test.php] 的連結中，[!UICONTROL eVar1] 會以「值 C」的值傳送，因為這是 eVar1 在呼叫 `tl()` 時目前的值。

## 語法和可能的值

`linkTrackVars` 變數是區分大小寫、以逗號分隔的變數名稱清單 (沒有物件名稱前置詞)。請使用 'eVar1'，而非 's.eVar1'。

```
s.linkTrackVars="variable_name[,variable_name[...]]"
```

此 `linkTrackVars` variable may contain only variables that are sent to [!DNL Analytics], namely: `events`, `campaign`, `purchaseID`, `products`, `eVar1-75`, `prop1-75`, `hier1-5`, `channel`, `server`, `state`, `zip`, and `pageType`.

## 範例

```
s.linkTrackVars="events,prop1,eVar49"
```

```
s.linkTrackVars="products"
```

## 組態設定

無

## 缺陷、問題和提示

* 如果 `linkTrackVars` 為空白，則所有含有值的變數將會隨所有伺服器呼叫受到追蹤。
* 列於 `linkTrackVars` 中的任何變數只要在任何下載、退出或自訂連結執行時含有值，就會受到追蹤。
* 若已使用 `linkTrackEvents`，則 `linkTrackVars` 必須包含「事件」。

* 變數請勿使用 "s." 或 "s_objectname."前置詞。
