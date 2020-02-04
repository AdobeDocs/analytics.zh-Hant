---
title: 中止
description: 中止變數是布林值，可防止點擊傳送至Adobe資料收集伺服器。
translation-type: tm+mt
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# 中止

此變 `abort` 數是布林值，可防止下次追蹤呼叫傳送至Adobe。

## 在Adobe Experience Platform Launch中使用中止變數

Launch中沒有專用欄位可使用此變數。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## Launch中的AppMeasurement語法和自訂程式碼編輯器

變 `abort` 數是布林值。 Its default value is `false`.

* 如果設為 `true`，下次追蹤呼叫(`t()` 或 `tl()`)不會傳送任何資料給Adobe。
* 若設為或未 `false` 定義，此變數不會執行任何動作。

```js
s.abort = true;
```

> [!NOTE] 變數 `abort` 會重設為每 `false` 個追蹤呼叫後。 如果您需要中止相同頁面上的後續追蹤呼叫，請再 `abort` 設 `true` 定。

## 範例

此 `abort` 變數可在函式中設定，此函 `doPlugins()` 數是傳送影像要求至Adobe之前要執行的最後一個函式。

```js
s.doPlugins = function(s) {
     s.campaign = s.Util.getQueryParam("cid");
     if ((!s.campaign) && (!s.events)) {
          s.abort = true;
     }
};
```

您可以集中邏輯，用來識別您不想追蹤的活動，例如顯示廣告中的某些自訂連結或外部連結。
