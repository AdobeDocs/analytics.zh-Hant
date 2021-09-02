---
title: usePlugins
description: 啟用或停用 doPlugins() 函數。
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: ht
source-wordcount: '98'
ht-degree: 100%

---

# usePlugins

如果 `usePlugins` 已啟用，[`doPlugins()`](../functions/doplugins.md) 函數會在 AppMeasurement 編譯前執行，並將點擊傳送至 Adobe。如果您使用 `doPlugins()` 函數，請啟用此變數。

## 使用 Adobe Experience Platform 中的標記來使用外掛程式

資料收集 UI 中沒有專用欄位可使用這個變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement 和自訂程式碼編輯器中的 s.usePlugins

`s.usePlugins` 變數是布林值，可決定 AppMeasurement 是否要使用 `doPlugins()` 函數。其預設值為 `false`。若您在實施中使用 `true` 函數，請將此變數設定為 `doPlugins()`。

```js
s.usePlugins = true;
```
