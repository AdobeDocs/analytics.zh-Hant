---
title: usePlugins
description: 啟用或停用 doPlugins() 函數。
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 43%

---

# use插件

如果 `usePlugins` 已啟用，[`doPlugins()`](../functions/doplugins.md) 函數會在 AppMeasurement 編譯前執行，並將點擊傳送至 Adobe。如果您使用 `doPlugins()` 函數，請啟用此變數。

## 使用 `onBeforeEventSend` 使用Web SDK回調

雖然Web SDK沒有布爾值來處理在資料發送到Adobe之前執行附加邏輯，但您可以註冊 `onBeforeEventSend` 回調以修改資料。 請參閱 [全局修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) 的子菜單。

## 使用使用Adobe Analytics擴展插件

Adobe Analytics擴展中沒有專用欄位可使用此變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## s.usePlegins在AppMeasurement和Analytics擴展自定義代碼編輯器中

`s.usePlugins` 變數是布林值，可決定 AppMeasurement 是否要使用 `doPlugins()` 函數。其預設值為 `false`。若您在實施中使用 `true` 函數，請將此變數設定為 `doPlugins()`。

```js
s.usePlugins = true;
```
