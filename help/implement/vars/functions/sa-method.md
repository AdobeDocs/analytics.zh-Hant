---
title: sa
description: 隨時在您的實作中變更報表套裝。
translation-type: tm+mt
source-git-commit: f179292abae9cf7986d61da89a86e3e88111943e

---


# sa

此方 `sa` 法可讓您隨時在頁面上動態變更報表套裝。 如果您想要在不重新載入頁面的情況下將資料傳送至不同的報表套裝，則可使用此方法。

## 使用Adobe Experience Platform Launch中的sa方法

在介面中變更報表套裝沒有彈性的方式。 設定Adobe Analytics擴充功能時，您可 [!UICONTROL 以在「資料庫管理] 」accordion下設定報表套裝。 不過，您無法使用規則變更或更新報表套裝。 如果您想在設定報表套裝值後更新這些值，請依照AppMeasurement語法使用自訂代碼編輯器。

## s.sa()在AppMeasurement和Launch自訂代碼編輯器中

呼叫方 `s.sa()` 法以變更目標報表套裝。 其唯一引數是包含報表套裝ID的字串，或多個以逗號分隔的報表套裝ID。 報表套裝ID引數為必要參數。 請勿在字串引數中使用空格。

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
