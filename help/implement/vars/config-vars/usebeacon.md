---
title: useBeacon
description: useBeacon 可強制 AppMeasurement 使用瀏覽器 sendBeacon API
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 90%

---

# useBeacon

大部分的現代化瀏覽器都包含原生方法 `navigator.sendBeacon()`。它能以非同步方法透過 HTTP 將少量資料傳送至網頁伺服器。如果 `useBeacon` 變數已啟用，AppMeasurement 便可使用 `navigator.sendBeacon()` 方法。對於退出連結以及其他您想在頁面取消載入之前先傳送資訊的情況，此功能十分實用。

如果 `useBeacon` 已啟用，傳送至 Adobe 的下一次點擊就會使用瀏覽器的 `navigator.sendBeacon()` 方法，而非標準 `GET` 影像要求。這個變數會同時套用至 [`s.t()`](../functions/t-method.md) 和 [`s.tl()`](../functions/tl-method.md) 影像要求。它需要 AppMeasurement 2.17.0 或更新版本。

>[!TIP]
>
> AppMeasurement 會自動啟用 `useBeacon` 來處理退出連結影像要求。

當訪客使用不支援 `useBeacon` 的瀏覽器時，`navigator.sendBeacon()` 變數會遭到忽略。使用此變數需有 AppMeasurement 2.16.0 或更新版本。

## 在Adobe Experience Platform中使用標籤使用信標

資料收集UI中沒有專用欄位可使用此變數。 依照 AppMeasurement 語法，使用自訂程式碼編輯器。

## AppMeasurement 和 自訂程式碼編輯器中的 s.useBeacon

`s.useBeacon` 變數是布林值，可決定 AppMeasurement 是否要使用瀏覽器的 `navigator.sendBeacon()` 方法。其預設值為 `false`。如果您要使用 `navigator.sendBeacon()` 的非同步性，請在呼叫追蹤函數之前將此變數設為 `true`。

```js
s.useBeacon = true;
```

>[!NOTE]
>
> 追蹤呼叫執行後，此變數會重設為 `false`。如果您的實施在相同的頁面載入中傳送多個影像要求 (如單頁應用程式)，請在每次追蹤呼叫前將此變數設定為 `true`。
