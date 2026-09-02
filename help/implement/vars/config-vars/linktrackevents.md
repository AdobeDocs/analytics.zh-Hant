---
title: linkTrackEvents
description: 決定要在連結追蹤影像要求中納入哪些事件。
feature: Appmeasurement Implementation
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
role: Admin, Developer
TQID: https://experienceleague.adobe.com/7BKaDxchTRu39doWzm8f32DOemgpvj1s-4uzfjJkOEA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 325
ht-degree: 66%

---

# linkTrackEvents

有些實施不希望將所有變數納入每個連結追蹤影像要求中。 請使用 [`linkTrackVars`](linktrackvars.md) 和 `linkTrackEvents` 變數，在 [`tl()`](../functions/tl-method.md) 呼叫中選擇性地納入維度和量度。

此變數不適用於頁面瀏覽數呼叫 ([`t()`](../functions/t-method.md) 方法)。

## 使用網頁SDK決定要包含在XDM事件中的Analytics事件

網頁SDK不會排除連結追蹤呼叫的某些欄位。 不過，您可在將資料傳送至Adobe之前，使用`onBeforeEventSend`回呼來清除或設定所要的欄位。 如需詳細資訊，請參閱Web SDK檔案中的[全域修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=zh-Hant#modifying-events-globally)。

## 使用Adobe Analytics擴充功能的連結追蹤呼叫中的事件

如果您未使用自訂程式碼，Adobe Experience Platform 會自動將已定義的事件納入連結追蹤點擊中。

>[!IMPORTANT]
>
>如果您在Analytics擴充功能的自訂程式碼編輯器中設定事件，也必須使用自訂程式碼在`linkTrackEvents`中納入事件。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.linkTrackEvents

`s.linkTrackEvents` 變數是字串，其中包含您要納入連結追蹤影像要求 (`tl()` 方法) 中的逗號分隔事件清單。 若要在連結追蹤點擊中納入量度，以下三個條件必須滿足：

* 在 [`events`](../page-vars/events/events-overview.md) 變數中設定所要的事件。 例如，`s.events = "event1";`。
* 在 `linkTrackVars` 中設定 `events` 變數。 例如，`s.linkTrackVars = "events";`。
* 在 `linkTrackEvents` 變數中設定所要的事件。 例如，`s.linkTrackEvents = "event1";`。

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

此變數的預設值為空字串。 如果此變數未定義，所有事件都會納入連結追蹤影像要求中。 請注意，資料收集會自動根據介面中所設定的事件自動填入這個變數，所以在使用 Adobe Experience Platform 中的標記的實作中一定會設定此變數。

>[!TIP]
>
>在此變數中指定事件時，請避免使用 Analytics 物件識別碼 (`s.`)。 例如，`s.linkTrackEvents = "event1";` 正確，而 `s.linkTrackEvents = "s.event1";` 不正確。

## 範例

以下連結追蹤函數只會在傳送給 Adobe 的影像要求中納入 `event1` (不會納入 `event2`)：

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
