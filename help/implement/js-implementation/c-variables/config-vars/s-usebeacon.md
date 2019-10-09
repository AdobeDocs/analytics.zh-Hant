---
title: useBeacon
description: useBeacon可讓您強制AppMeasurement使用瀏覽器sendBeacon API
keywords: Analytics 實作
seo-description: useBeacon可讓您強制AppMeasurement使用瀏覽器sendBeacon API
translation-type: tm+mt
source-git-commit: f89d909e539cee2b78798c165fcb405773418056

---


# s.useBeacon

變 `s.useBeacon` 數會強制下一個請求使用瀏覽器的 [sendBeacon API](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/sendBeacon)。 使 `s.sendBeacon` 用可讓HTTP請求在頁面內容外傳送。 對於退出連結和您想在頁面解除載入之前先傳送資訊的其他情況，此功能十分實用。

設定此值僅適用於AppMeasurement觸發的下一個請求。 觸發請求後， `s.useBeacon` 重設為false。 此變數同時套用至 `s.t()` 影像 `s.tl()` 請求。

使用變 `s.useBeacon` 數需要AppMeasurement 2.17.0或更新版本。

> [!NOTE] ExitLinks [會自動使用此變數](s-linktrackvars.md) ，而不需要任何其他設定。

## 語法

```js
s.useBeacon = true;
```
