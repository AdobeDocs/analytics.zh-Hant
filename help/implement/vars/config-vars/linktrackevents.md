---
title: linkTrackEvents
description: 決定要在連結追蹤影像要求中納入哪些事件。
feature: Variables
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 67%

---

# 連結跟蹤事件

有些實施不希望將所有變數納入每個連結追蹤影像要求中。請使用 [`linkTrackVars`](linktrackvars.md) 和 `linkTrackEvents` 變數，在 [`tl()`](../functions/tl-method.md) 呼叫中選擇性地納入維度和量度。

此變數不適用於頁面瀏覽數呼叫 ([`t()`](../functions/t-method.md) 方法)。

## 使用Web SDK確定要在XDM事件中包括的分析事件

Web SDK不排除某些用於連結跟蹤調用的欄位。 但是，您可以使用 `onBeforeEventSend` 回調以在資料發送到Adobe之前清除或設定所需欄位。 請參閱 [全局修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) 的子菜單。

## 使用Adobe Analytics分機的鏈路跟蹤呼叫中的事件

如果您未使用自訂程式碼，Adobe Experience Platform 會自動將已定義的事件納入連結追蹤點擊中。

>[!IMPORTANT]
>
>如果在分析擴展的自定義代碼編輯器中設定了事件，則必須將該事件包括在 `linkTrackEvents` 也使用自定義代碼。

## AppMeasurement中的s.linkTrackEvents和Analytics擴展自定義代碼編輯器

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
