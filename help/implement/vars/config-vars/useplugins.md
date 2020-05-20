---
title: usePlugins
description: 啟用或停用 doPlugins() 函數。
translation-type: ht
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# usePlugins

如果 `usePlugins` 已啟用，[`doPlugins()`](../functions/doplugins.md) 函數會在 AppMeasurement 編譯前執行，並將點擊傳送至 Adobe。如果您使用 `doPlugins()` 函數，請啟用此變數。

## 使用 Adobe Experience Platform Launch 中的外掛程式

Launch 中沒有使用此變數的專用欄位。依照 AppMeasurement 語法，使用自訂程式碼編輯器。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.usePlugins

`s.usePlugins` 變數是布林值，可決定 AppMeasurement 是否要使用 `doPlugins()` 函數。其預設值為 `false`。若您在實施中使用 `true` 函數，請將此變數設定為 `doPlugins()`。

```js
s.usePlugins = true;
```
