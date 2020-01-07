---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: ht
source-git-commit: ca0797a353661a72d4064aa5aa84c3d9b7eb38a5

---


# s.linkTrackEvents

此變數是以逗號分隔，隨自訂、退出或下載連結而傳送的事件清單。`linkTrackEvents` 參數必須包含您要在每個檔案下載、退出連結及自訂連結中追蹤的每個事件。當其中一種連結類型發生時，即會追蹤每個指定變數的現行值。只有在 [`linkTrackVars`](https://docs.adobe.com/content/help/zh-Hant/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) 包含「事件」時，才會考量此變數。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 轉換 | "無" |

不在 `linkTrackEvents` 中的事件不會傳送至 Analytics，即使此事件已填入連結的 `onClick` 事件中亦然，如下列範例所示:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

[`linkTrackVars`](https://docs.adobe.com/content/help/zh-Hant/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) 和 `linkTrackEvents` 的值會覆寫 JS 檔案中的設定，並確保針對特定連結所設定的只有在自訂連結程式碼中指定的變數和事件。這兩項設定都會影響每個檔案下載、退出連結和自訂連結。若將變數 (或事件) 套用至現行頁面，而不是特定的檔案下載、退出連結或自訂連結，每個變數和事件的例項數可能會不實膨脹。

為確保能為自訂連結程式碼設定正確的變數，Adobe 建議您在自訂連結程式碼內設定  自訂連結程式碼中的 *`linkTrackVars`* 和 *`linkTrackEvents`*，如下所示:

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

在上述範例中，`prop1` 的值設定於自訂連結程式碼本身當中。`prop2` 的值則來自現有的變數值，如頁面上所設定。

*注意: 如果`linkTrackVars`(或`linkTrackEvents`) 為 Null (或空字串)，系統就會追蹤所有針對現有頁面所定義的 Analytics 變數 (或事件)。換言之，所有具有值的變數都會隨連結資料而傳送。這樣很可能會導致每個變數的例項都經過膨脹。為避免與其他變數相關聯的例項或頁面檢視膨脹，Adobe 建議在用於連結追蹤之連結的`linkTrackVars`事件中填入`linkTrackEvents`和`onClick`。*

所有應隨連結資料 (自訂、退出和下載連結) 傳送的變數，都應列在 `linkTrackVars` 中。若已使用 `linkTrackEvents`，則 `linkTrackVars` 應包含「事件」。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 任何 | "無" |

填入 `linkTrackEvents` 時，請勿在變數中使用「s.」首碼。舉例來說，您應填入「event1」填入 ，而非「s.event1」。以下範例說明該值的使用方式。

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

在第一個連結中，請注意事件變數仍保有連結獲得點擊之前所設定的值。這樣一來，`event1` 就可隨自訂連結而傳送。在第二個範例中，系統並未記錄 `event2` 的連結，因為它並未列於 `linkTrackEvents` 中。

為避免造成混淆或可能的問題，Adobe 建議在用於連結追蹤之連結的 [ 事件中填入 `linkTrackVars`](https://docs.adobe.com/content/help/zh-Hant/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html)`linkTrackEvents` 和 `onClick`。

## 語法和可能的值

*`linkTrackEvents`* 變數是以逗號分隔的事件清單 (不含空格)。

```
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

`linkTrackEvents` 中只允許使用事件名稱。這些事件會列於[事件](https://docs.adobe.com/content/help/zh-Hant/analytics/implementation/analytics-basics/ref-events.html)中。若事件名稱之前或之後出現空格，該事件即無法隨任何連結的影像要求而傳送。

## 範例

若要追蹤每個檔案下載、退出連結及自訂連結中的 `prop1`、`eVar1` 及 `event1`，請在全域 JS 檔案內使用下列設定:

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

* 請小心是否在頁面上引發了事件，且該事件列於 `linkTrackEvents` 中。該事件會隨任何退出、下載或自訂連結而再次記錄，除非事件變數在該事件前重設 (在連結的 `onClick` 中，或在呼叫 `t()` 函數後)。

* 如果 `linkTrackEvents` 在事件名稱之間含有空格，則不會記錄這些事件。
