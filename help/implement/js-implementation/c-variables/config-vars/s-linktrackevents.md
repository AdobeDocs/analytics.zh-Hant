---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: 82060388a9a2122b66c57725cafa0eb4ce54e147

---


# s.linkTrackEvents

此變數是以逗號分隔，隨自訂、退出或下載連結而傳送的事件清單。The `linkTrackEvents` parameter should include each event you want to track with every file download, exit link, and custom link. 當其中一種連結類型發生時，即會追蹤每個指定變數的現行值。只有在 `linkTrackVars` 包含「事件」時，才會考量此變數。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 轉換 | "無" |

If an event is not in `linkTrackEvents`, it is not sent to Analytics, even if it is populated in the `onClick` event of a link, as shown in the following example:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

The values of [`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) and `linkTrackEvents` override the settings in the JS file and ensure only the variables and events specified in the custom link code are set for the specific link. 這兩項設定都會影響每個檔案下載、退出連結和自訂連結。 當變數（或事件）套用至目前頁面，但特定檔案下載、退出連結或自訂連結時，每個變數和事件的例項可能會誇大。

為確保以自訂連結代碼設定正確的變數，Adobe建議 *`linkTrackVars`* 在自 *`linkTrackEvents`* 訂連結代碼內設定，如下所示：

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

*注意：如果`linkTrackVars`(或`linkTrackEvents`)為null（或空字串，例如""），則會追蹤為目前頁面定義的所有Analytics變數（或事件）。 換言之，所有具有值的變數都會隨連結資料傳送。 這很可能會誇大每個變數的例項。 為避免與其他變數相關聯的例項或頁面檢視膨脹，Adobe 建議在用於連結追蹤之連結的`linkTrackVars`onClick`linkTrackEvents`事件中填入[!UICONTROL 和]。*

所有應隨連結資料 (自訂、退出和下載連結) 傳送的變數，都應列在 `linkTrackVars` 中。若已使用 `linkTrackEvents`，則 `linkTrackVars` 應包含「事件」。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 任何 | "無" |

When populating `linkTrackEvents`, do not use the 's.' prefix for variables. 例如，您不應將其填入"s.event1"，而應將其填入"event1"。 下列範例說明如何使用它。

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

在第一個連結中，請注意事件變數會保留在點按連結之前所設定的值。 這讓 event1 可隨自訂連結傳送。In the second example, the link to event2 is not recorded because it is not listed in `linkTrackEvents`.

為避免造成混淆或可能的問題，Adobe 建議在用於連結追蹤之連結的 [ 事件中填入 `linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html)`linkTrackEvents` 和 `onClick`。

## 語法和可能的值

*`linkTrackEvents`* 變數是以逗號分隔的事件清單 (不含空格)。

```
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

`linkTrackEvents` 中只允許使用事件名稱。這些事件會列於[事件](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html)中。如果事件名稱前後出現空格，則無法隨任何連結影像要求傳送事件。

## 範例

To track `prop1`, `eVar1`, and `event1` with every file download, exit link, and custom link, use the following settings within the global JS file:

```
s.linkTrackVars="prop1,eVar1,events"
```

```
s.linkTrackEvents="event1"
```

**更多範例**

```
s.linkTrackEvents="purchase,event1"
```

```
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

## 組態設定

無

## 缺陷、問題和提示

* 只有在 `linkTrackEvents` 包含「events」變數的情況下，JavaScript 檔案才會使用 `linkTrackVars`。只有在已定義 `linkTrackVars` 的情況下，`linkTrackEvents` 中才應包含「events」。

* 請小心是否在頁面上引發了事件，且該事件列於 `linkTrackEvents` 中。該事件會隨任何[!UICONTROL 退出]、[!UICONTROL 下載]或[!UICONTROL 自訂]連結而再次記錄，除非事件變數在該事件前重設 (在連結的 [!UICONTROL onClick] 中，或在呼叫 `t()` 函數後)。

* 如果 `linkTrackEvents` 在事件名稱之間含有空格，則不會記錄這些事件。
