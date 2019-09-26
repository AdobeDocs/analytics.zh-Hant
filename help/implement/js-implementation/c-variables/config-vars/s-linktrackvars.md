---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.linkTrackVars

 變數是以逗號分隔，隨自訂、退出和下載連結而傳送的變數清單。

If *`linkTrackVars`* is set to "", all variables that have values are sent with link data. To avoid inflation of instances or page views associated with other variables, Adobe recommends populating  and  in the onClick event of a link that is used for link tracking.*`linkTrackVars`**`linkTrackEvents`*

All variables that should be sent with link data (custom, exit, and download links) should be listed in *`linkTrackVars`*. If  is used,  should contain "events."*`linkTrackEvents`**`linkTrackVars`*

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 任何 | "無" |

在填入  *`linkTrackVars`*, do not use the 's.' prefix for variables. For example, instead of populating  with "s.prop1," you should populate it with "prop1." *`linkTrackVars`* The following example illustrates how  should be used.*`linkTrackVars`*

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

由於 google.com 的連結是退出連結 (除非您正在使用 Google)，event1 和 eVar1 會隨退出連結資料傳送，而增加與 eVar1 相關聯的例項數和 event1 的引發次數。In the link to [!DNL test.php], [!UICONTROL eVar1] is sent with a value of 'value C' because that is the current value of [!UICONTROL eVar1] at the time that *`tl()`* is called.

## 語法和可能的值

The *`linkTrackVars`* variable is a case-sensitive, comma-separated list of variable names, without the object name prefix. 請使用 'eVar1'，而非 's.eVar1'。

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

此  variable may contain only variables that are sent to , namely: , , , , eVar1-75, prop1-75, hier1-5, , , , , and .*`linkTrackVars`*[!DNL Analytics]*`events`**`campaign`**`purchaseID`**`products`**`channel`**`server`**`state`**`zip`**`pageType`*

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

* If *`linkTrackVars`* is blank, all variables that have values are tracked with all server calls.
* Any variable listed in *`linkTrackVars`* that has a value at the time of any download, exit, or custom link, are tracked.
* If  is used,  must contain "events."*`linkTrackEvents`**`linkTrackVars`*

* 變數請勿使用 "s." 或 "s_objectname."前置詞。