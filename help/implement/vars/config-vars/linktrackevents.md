---
title: linkTrackEvents
description: 決定要在連結追蹤影像要求中納入哪些事件。
feature: Variables
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 100%

---

# 連結跟蹤事件

有些實施不希望將所有變數納入每個連結追蹤影像要求中。請使用 [`linkTrackVars`](linktrackvars.md) 和 `linkTrackEvents` 變數，在 [`tl()`](../functions/tl-method.md) 呼叫中選擇性地納入維度和量度。

此變數不適用於頁面瀏覽數呼叫 ([`t()`](../functions/t-method.md) 方法)。

## 使用 Adobe Experience Platform 中的標記的連結追蹤呼叫中的事件

如果您未使用自訂程式碼，Adobe Experience Platform 會自動將已定義的事件納入連結追蹤點擊中。

>[!IMPORTANT]
>
>如果您使用自訂程式碼編輯器在資料收集 UI 中設定變數，您也必須使用自訂程式碼將此事件納入 `linkTrackEvents`。

## AppMeasurement 和自訂程式碼編輯器中的 s.linkTrackEvents

`s.linkTrackEvents` 變數是字串，其中包含您要納入連結追蹤影像要求 (`tl()` 方法) 中的逗號分隔事件清單。若要在連結追蹤點擊中納入量度，以下三個條件必須滿足：

* 在 [`events`](../page-vars/events/events-overview.md) 變數中設定所要的事件。例如：`s.events = "event1";`。
* 在 `linkTrackVars` 中設定 `events` 變數。例如：`s.linkTrackVars = "events";`。
* 在 `linkTrackEvents` 變數中設定所要的事件。例如：`s.linkTrackEvents = "event1";`。

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

此變數的預設值為空字串。如果此變數未定義，所有事件都會納入連結追蹤影像要求中。請注意，資料收集會自動根據介面中所設定的事件自動填入這個變數，所以在使用 Adobe Experience Platform 中的標記的實作中一定會設定此變數。

>[!TIP]
>
>在此變數中指定事件時，請避免使用 Analytics 物件識別碼 (`s.`)。例如，`s.linkTrackEvents = "event1";` 正確，而 `s.linkTrackEvents = "s.event1";` 不正確。

## 範例

以下連結追蹤函數只會在傳送給 Adobe 的影像要求中納入 `event1` (不會納入 `event2`)：

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
