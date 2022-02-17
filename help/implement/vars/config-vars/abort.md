---
title: abort
description: abort 變數是布林值，可防止將點擊傳送至 Adobe 資料收集伺服器。
feature: Variables
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 100%

---

# 中止

`abort` 變數是布林值，可防止將下個追蹤呼叫傳送至 Adobe。

## 使用 Adobe Experience Platform 中資料收集 UI 內的 abort 變數

資料收集 UI 中沒有專用欄位可使用這個變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## 資料收集 UI 中的 AppMeasurement 語法和自訂程式碼編輯器

`abort` 變數是布林值。其預設值為 `false`。

* 如果設為 `true`，下個追蹤呼叫 ([`t()`](../functions/t-method.md) 或 [`tl()`](../functions/tl-method.md)) 就不會將任何資料傳送至 Adobe。
* 若設為 `false` 或未定義，此變數就不會執行任何動作。

```js
s.abort = true;
```

>[!NOTE]
>
>`abort` 變數會在每個追蹤呼叫後重設為 `false`。如需中止相同頁面上的後續追蹤呼叫，請重新將 `abort` 設為 `true`。

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
