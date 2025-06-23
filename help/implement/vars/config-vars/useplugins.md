---
title: usePlugins
description: 啟用或停用 doPlugins() 函數。
feature: Appmeasurement Implementation
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 34%

---

# usePlugins

如果 `usePlugins` 已啟用，[`doPlugins()`](../functions/doplugins.md) 函數會在 AppMeasurement 編譯前執行，並將點擊傳送至 Adobe。如果您使用 `doPlugins()` 函數，請啟用此變數。

## 使用Web SDK使用`onBeforeEventSend`回呼

雖然網頁SDK沒有布林值可在將資料傳送至Adobe之前處理其他邏輯的執行，但您可以註冊`onBeforeEventSend`回呼以修改資料。 如需詳細資訊，請參閱Web SDK檔案中的[全域修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally)。

## 使用Adobe Analytics擴充功能的外掛程式

Adobe提供標示為「常用Analytics外掛程式」的擴充功能，可讓您呼叫大部分的[外掛程式](../plugins/impl-plugins.md)。 安裝擴充功能，並在規則中呼叫所需的外掛程式。

如果Adobe擴充功能中未包含所需的外掛程式，請依照AppMeasurement語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.usePlugins

`s.usePlugins` 變數是布林值，可決定 AppMeasurement 是否要使用 `doPlugins()` 函數。其預設值為 `false`。若您在實施中使用 `true` 函數，請將此變數設定為 `doPlugins()`。

```js
s.usePlugins = true;
```
