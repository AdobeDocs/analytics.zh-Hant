---
title: sa
description: 隨時在您的實施中變更報表套裝。
translation-type: ht
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# sa

`sa` 方法可讓您隨時在頁面上動態變更報表套裝。如果您想要在不重新載入頁面的情況下，將資料傳送至不同的報表套裝，可以使用此方法。

## 使用 Adobe Experience Platform Launch 中的 sa 方法

在介面中變更報表套裝沒有彈性的方式。設定 Adobe Analytics 擴充功能時，您可以在[!UICONTROL 「程式庫管理」]設定追蹤器下方設定報表套裝。不過，您無法使用規則變更或更新報表套裝。如果您想要在設定報表套裝值後更新這些值，請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.sa()

呼叫 `s.sa()` 方法變更目的地報表套裝。其唯一引數是包含報表套裝 ID 的字串，或是多個以逗號分隔的報表套裝 ID。報表套裝 ID 引數為必要項目。請勿在字串引數中使用空格。

```js
s.sa("examplersid");
```

## 範例

如果使用者在您的網站上採取特定動作，您可以變更報表套裝。

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
