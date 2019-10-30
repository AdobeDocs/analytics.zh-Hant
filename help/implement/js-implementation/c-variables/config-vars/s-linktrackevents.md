---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.linkTrackEvents

此變數是以逗號分隔，隨[!UICONTROL 自訂]、[!UICONTROL 退出]或[!UICONTROL 下載]連結而傳送的事件清單。

若為不在 *`linkTrackEvents`* 中的事件，則不會傳送至 [!DNL Analytics]，即使此事件填入連結的 [!UICONTROL onClick] 事件中亦然，如下列範例所示:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

在 [!DNL help.php] 的第一個連結中，請留意到事件變數保有連結被點按之前所設定的值。這讓 event1 可隨自訂連結傳送。在第二個範例中，並未記錄 [!DNL test.php] 的連結 (event2)，因為它並未列於 *`linkTrackEvents`* 中。

為避免造成混淆或可能的問題，Adobe 建議在用於連結追蹤之連結的 [!UICONTROL onClick] 事件中填入 *`linkTrackVars`* 和 *`linkTrackEvents`*。

*`linkTrackEvents`* 變數包含應隨[!UICONTROL 自訂]、[!UICONTROL 下載]和[!UICONTROL 退出]連結而傳送的事件。只有在 *`linkTrackVars`* 包含「事件」時，才會考量此變數。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 轉換 | "無" |

## 語法和可能的值

*`linkTrackEvents`* 變數是以逗號分隔的事件清單 (不含空格)。

```js
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

*`linkTrackEvents`* 中只允許使用事件名稱。這些事件會列於[事件](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html)中。若事件名稱之前或之後出現空格，該事件即無法隨任何連結影像要求傳送。

## 範例

```js
s.linkTrackEvents="purchase,event1"
```

```js
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

## 組態設定

無

## 缺陷、問題和提示

* 只有在 *`linkTrackVars`* 包含「events」變數的情況下，JavaScript 檔案才會使用 *`linkTrackEvents`*。只有在已定義 *`linkTrackEvents`* 的情況下，*`linkTrackVars`* 中才應包含「events」。

* 請小心是否在頁面上引發了事件，且該事件列於 *`linkTrackEvents`* 中。該事件會隨任何[!UICONTROL 退出]、[!UICONTROL 下載]或[!UICONTROL 自訂]連結而再次記錄，除非事件變數在該事件前重設 (在連結的 [!UICONTROL onClick] 中，或在呼叫 *`t()`* 函數後)。

* 如果 *`linkTrackEvents`* 在事件名稱之間含有空格，則不會記錄這些事件。
