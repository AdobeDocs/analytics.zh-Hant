---
title: usePlugins
description: 啟用或停用 doPlugins() 函數。
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 52%

---

# usePlugins

如果 `usePlugins` 已啟用，[`doPlugins()`](../functions/doplugins.md) 函數會在 AppMeasurement 編譯前執行，並將點擊傳送至 Adobe。如果您使用 `doPlugins()` 函數，請啟用此變數。

## 使用 `onBeforeEventSend` 使用Web SDK進行回呼

雖然Web SDK沒有布林值可在資料傳送至Adobe之前處理其他邏輯的執行，但您可以註冊 `onBeforeEventSend` 回呼以修改資料。 請參閱 [全域修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) 如需詳細資訊，請參閱網頁SDK檔案。

## 使用Adobe Analytics擴充功能的外掛程式

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.usePlugins

`s.usePlugins` 變數是布林值，可決定 AppMeasurement 是否要使用 `doPlugins()` 函數。其預設值為 `false`。若您在實施中使用 `true` 函數，請將此變數設定為 `doPlugins()`。

```js
s.usePlugins = true;
```
