---
title: useBeacon
description: useBeacon可強制 AppMeasurement 使用瀏覽器 sendBeacon API
keywords: Analytics Implementation
translation-type: ht
source-git-commit: 6c57780d0ecf65669c1a5306dde267f6e48f1cc4

---


# s.useBeacon

`s.useBeacon` 變數會強制下個要求使用瀏覽器的 [sendBeacon API](https://developer.mozilla.org/zh-TW/docs/Web/API/Navigator/sendBeacon)。使用 `s.sendBeacon` 可讓系統在頁面內容之外傳送 HTTP 要求。對於退出連結以及其他您想在頁面卸載之前先傳送資訊的情況，此功能十分實用。

此值的設定僅適用於 AppMeasurement 所觸發的下一個要求。觸發要求後， `s.useBeacon` 會重設為 false。這個變數會同時套用至 `s.t()` 和 `s.tl()` 影像請求。

使用 `s.useBeacon` 變數需要 AppMeasurement 2.17.0 或更新版本。

> [!NOTE] [退出連結](s-linktrackvars.md)會自動使用此變數，不需要額外設定。

## 語法

```js
s.useBeacon = true;
```
