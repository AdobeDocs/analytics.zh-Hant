---
title: usePlugins
description: 啟用或停用doPlugins()函式。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# usePlugins

如果 `usePlugins` 已啟用，此函 [`doPlugins()`](../functions/doplugins.md) 數會在AppMeasurement編譯前執行，並傳送點擊至Adobe。 如果您使用函式，請啟用此 `doPlugins()` 變數。

## 使用Adobe Experience Platform Launch的增效模組

Launch中沒有專用欄位可使用此變數。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## AppMeasurement和Launch自訂代碼編輯器中的s.usePlugins

變 `s.usePlugins` 數是布林值，可判斷AppMeasurement是否呼叫 `doPlugins()` 函式。 Its default value is `false`. 若您在實作中 `true` 使用函式，請 `doPlugins()` 將此變數設定為。

```js
s.usePlugins = true;
```
