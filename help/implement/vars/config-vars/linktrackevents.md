---
title: linkTrackEvents
description: 決定要在連結追蹤影像要求中包含哪些事件。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# linkTrackEvents

有些實作不想將所有變數納入所有連結追蹤影像要求。 使用和 `linkTrackVars` 變數 `linkTrackEvents` ，在呼叫中選擇性地包含維度和 `tl()` 量度。

此變數不用於頁面檢視呼叫(`t()` 函式)。

## 使用Adobe Experience Platform Launch的連結追蹤呼叫中的事件

Launch會自動偵測介面中定義的事件，並將其納入連結追蹤點擊中。

> [!IMPORTANT] 如果您使用自訂代碼編輯器在啟動中設定事件，則也必須在使用自訂代碼 `linkTrackEvents` 時加入事件。

## AppMeasurement和Launch自訂代碼編輯器中的s.linkTrackEvents

變 `s.linkTrackEvents` 數是一個字串，包含您要納入連結追蹤影像請求（函式）中的逗號分隔事件`tl()` 清單。 必須符合下列三個條件，才能在連結追蹤點擊中包含量度：

* 在變數中設定所要的 `events` 事件。 例如, `s.events = "event1";`.
* Set the `events` variable in `linkTrackVars`. 例如, `s.linkTrackVars = "events";`.
* 在變數中設定所要的 `linkTrackEvents` 事件。 例如, `s.linkTrackEvents = "event1";`.

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

此變數的預設值為空字串。 如果未定義此變數，所有事件都會納入連結追蹤影像請求中。 請注意，Launch會根據介面中設定的事件自動填入此變數，因此一律會在使用Launch的實施中設定。

> [!TIP] 在此變數中指定事件時，請`s.`避免使用Analytics物件識別碼()。 例如， `s.linkTrackEvents = "event1";` 正確，但 `s.linkTrackEvents = "s.event1";` 不正確。

## 範例

下列連結追蹤功能僅包含 `event1` (非 `event2`)傳送至Adobe的影像要求：

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
