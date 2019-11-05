---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# s.linkTrackVars

 變數是以逗號分隔，隨自訂、退出和下載連結而傳送的變數清單。

如果將 *`linkTrackVars`* 設為 「」，則所有擁有值的變數都會隨連結資料傳送。為避免與其他變數相關聯的例項或頁面檢視膨脹，Adobe 建議在用於連結追蹤之連結的 [!UICONTROL onClick] 事件中填入 *`linkTrackVars`* 和 *`linkTrackEvents`*。

所有應隨連結資料 (自訂、退出和下載連結) 傳送的變數，都應列在 *`linkTrackVars`* 中。若已使用 *`linkTrackEvents`*，則 *`linkTrackVars`* 應包含「事件」。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 任何 | "無" |

When populating *`linkTrackVars`*, do not use the 's.' prefix for variables. 例如，您應以「prop1」填入 *`linkTrackVars`*，而不是以「s.prop1」填入。以下範例說明應如何使用 *`linkTrackVars`*。

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

由於 google.com 的連結是退出連結 (除非您正在使用 Google)，event1 和 eVar1 會隨退出連結資料傳送，而增加與 eVar1 相關聯的例項數和 event1 的引發次數。在 [!DNL test.php] 的連結中，[!UICONTROL eVar1] 會以「值 C」的值傳送，因為這是 [!UICONTROL eVar1] 在呼叫 *`tl()`* 時目前的值。

## 語法和可能的值

*`linkTrackVars`* 變數是區分大小寫、以逗號分隔的變數名稱清單 (沒有物件名稱前置詞)。請使用 'eVar1'，而非 's.eVar1'。

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

此&#x200B;*`linkTrackVars`* 變數僅可包含傳送至 [!DNL Analytics] 的變數，亦即: *`events`*、*`campaign`*、*`purchaseID`*、*`products`*、[!UICONTROL eVar1-75]、[!UICONTROL prop1-75]、[!UICONTROL hier1-5]、*`channel`*、*`server`*、*`state`*、*`zip`* 和 *`pageType`*。

## 範例

```js
s.linkTrackVars="events,prop1,eVar49"
```

```js
s.linkTrackVars="products"
```

## 組態設定

無

## 缺陷、問題和提示

* 如果 *`linkTrackVars`* 為空白，則所有含有值的變數將會隨所有伺服器呼叫受到追蹤。
* 列於 *`linkTrackVars`* 中的任何變數只要在任何下載、退出或自訂連結執行時含有值，就會受到追蹤。
* 若已使用 *`linkTrackEvents`*，則 *`linkTrackVars`* 必須包含「事件」。

* 變數請勿使用 "s." 或 "s_objectname."前置詞。
