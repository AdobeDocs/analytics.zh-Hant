---
title: linkTrackEvents
description: 決定要在連結追蹤影像要求中納入哪些事件。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkTrackEvents

有些實施不希望將所有變數納入每個連結追蹤影像要求中。請使用 [`linkTrackVars`](linktrackvars.md) 和 `linkTrackEvents` 變數，在 [`tl()`](../functions/tl-method.md) 呼叫中選擇性地納入維度和量度。

This variable is not used for page view calls ([`t()`](../functions/t-method.md) method).

## 使用 Adobe Experience Platform Launch 時連結追蹤呼叫中的事件

Launch 會自動偵測介面中定義的事件，並將其納入連結追蹤點擊中。

>[!IMPORTANT] 如果您使用自訂程式碼編輯器在 Launch 中設定事件，也必須使用自訂程式碼在 `linkTrackEvents` 中納入事件。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.linkTrackEvents

The `s.linkTrackEvents` variable is a string containing a comma-delimited list of events that you want to include in link tracking image requests (`tl()` method). 若要在連結追蹤點擊中納入量度，以下三個條件必須滿足：

* 在 [`events`](../page-vars/events/events-overview.md) 變數中設定所要的事件。例如：`s.events = "event1";`。
* 在 `linkTrackVars` 中設定 `events` 變數。例如：`s.linkTrackVars = "events";`。
* 在 `linkTrackEvents` 變數中設定所要的事件。例如：`s.linkTrackEvents = "event1";`。

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

此變數的預設值為空字串。如果此變數未定義，所有事件都會納入連結追蹤影像要求中。請注意，Launch 會根據介面中設定的事件自動填入此變數，因此在使用 Launch 的實施中一律會設定。

>[!TIP] 在此變數中指定事件時，請避免使用 Analytics 物件識別碼 (`s.`)。例如，`s.linkTrackEvents = "event1";` 正確，而 `s.linkTrackEvents = "s.event1";` 不正確。

## 範例

以下連結追蹤函數只會在傳送給 Adobe 的影像要求中納入 `event1` (不會納入 `event2`)：

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
