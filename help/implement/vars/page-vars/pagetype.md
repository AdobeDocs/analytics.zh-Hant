---
title: pageType
description: 判斷目前頁面是否為404錯誤。
translation-type: tm+mt
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# pageType

變 `pageType` 數是用來指定網站上錯誤頁面（例如404個錯誤）的旗標。 如果此變數包含字串 `errorPage`，則會填入「找不到頁面」維度。

> [!IMPORTANT] 請勿在非錯誤頁面上設定此變數。

## Adobe Experience Platform Launch中的頁面類型

Launch中沒有專用欄位可使用此變數。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## s.pageType（在AppMeasurement和Launch自訂代碼編輯器中）

變 `s.pageType` 數是字串，其中值是 `errorPage` 其唯一有效值。 在您網站上的任何錯誤頁面上（例如404頁），將此變數設為此值。

```js
s.pageType = "errorPage";
```

> [!TIP] 使用eVar來收集錯誤代碼，以便您取得訪客在您網站上遇到哪些特定錯誤的詳細資訊。
