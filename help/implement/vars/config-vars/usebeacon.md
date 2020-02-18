---
title: useBeacon
description: useBeacon可強制 AppMeasurement 使用瀏覽器 sendBeacon API
translation-type: tm+mt
source-git-commit: 58513f012bdbd1143601221985a399ed46916664

---


# useBeacon

大部份的現代瀏覽器都包含原生方法 `navigator.sendBeacon()`。 它透過HTTP將少量資料非同步傳送至網頁伺服器。 如果變數已啟用， `navigator.sendBeacon()` AppMeasurement可 `useBeacon` 以使用方法。 對於退出連結和您想在頁面解除載入之前傳送資訊的其他情況，此功能十分有用。

如果 `useBeacon` 已啟用，傳送至Adobe的下一次點擊會使用瀏覽器的方 `navigator.sendBeacon()` 法，而非標準 `GET` 影像要求。 這個變數會同時套用至 `s.t()` 和 `s.tl()` 影像請求。它需要AppMeasurement 2.17.0或更新版本。

> [!TIP] AppMeasurement會自動啟 `useBeacon` 用退出連結影像要求。

當訪 `useBeacon` 客使用不支援的瀏覽器時，會忽略變數 `navigator.sendBeacon()`。 使用此變數需要AppMeasurement 2.16.0或更新版本。

## 在Adobe Experience Platform Launch中使用Beacon

Launch中沒有專用欄位可使用此變數。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## AppMeasurement和Launch自訂代碼編輯器中的s.useBeacon

變 `s.useBeacon` 數是布林值，可判斷AppMeasurement是否使用瀏覽器的方 `navigator.sendBeacon()` 法。 Its default value is `false`. 如果您要使用 `true` 的非同步性，請在呼叫追蹤函式之前，將此變數設為 `navigator.sendBeacon()`。

```js
s.useBeacon = true;
```

> [!NOTE] 追蹤呼叫執行後，此變數會重設為 `false`。 如果您的實作在相同的頁面載入中傳送多個影像要求（例如單頁應用程式），請在每次追蹤呼叫前將此變 `true` 數設定為。
