---
title: abort
description: abort 變數是布林值，可防止將點擊傳送至 Adobe 資料收集伺服器。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# abort

`abort` 變數是布林值，可防止將下個追蹤呼叫傳送至 Adobe。

## 在 Adobe Experience Platform Launch 中使用 abort 變數

Launch 中沒有使用此變數的專用欄位。依照 AppMeasurement 語法，使用自訂程式碼編輯器。

## Launch 中的 AppMeasurement 語法和自訂程式碼編輯器

`abort` 變數是布林值。其預設值為 `false`。

* 如果設為 `true`，下個追蹤呼叫 ([`t()`](../functions/t-method.md) 或 [`tl()`](../functions/tl-method.md)) 就不會將任何資料傳送至 Adobe。
* 若設為 `false` 或未定義，此變數就不會執行任何動作。

```js
s.abort = true;
```

>[!NOTE] `abort` 變數會在每個追蹤呼叫後重設為 `false`。如需中止相同頁面上的後續追蹤呼叫，請重新將 `abort` 設為 `true`。

## 範例

`abort` 變數可在 [`doPlugins()`](../functions/doplugins.md) 函數中設定，此函數是將影像要求傳送至 Adobe 之前執行的最後一個函式。

```js
s.doPlugins = function(s) {
     s.campaign = s.Util.getQueryParam("cid");
     if ((!s.campaign) && (!s.events)) {
          s.abort = true;
     }
};
```

您可以集中邏輯，用於識別不想追蹤的活動，例如自訂連結或顯示廣告中的外部連結。
