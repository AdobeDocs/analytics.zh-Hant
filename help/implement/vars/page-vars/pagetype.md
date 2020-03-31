---
title: pageType
description: 判斷目前頁面是否為 404 錯誤。
translation-type: ht
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# pageType

`pageType` 變數是用來標出網站上錯誤頁面 (如 404 錯誤) 的標幟。如果此變數包含字串 `errorPage`，則會填入「找不到頁面」維度。

> [!IMPORTANT] 請勿在非錯誤頁面上設定此變數。

## Adobe Experience Platform Launch 中的頁面類型

Launch 中沒有使用此變數的專用欄位。依照 AppMeasurement 語法，使用自訂程式碼編輯器。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.pageType

`s.pageType` 變數是字串，而 `errorPage` 值是唯一的有效值。在網站上的任何錯誤頁面 (如 404 頁面) 上，將此變數設為此值。

```js
s.pageType = "errorPage";
```

> [!TIP] 使用 eVar 來收集錯誤代碼，以便取得訪客在網站上遇到哪些具體錯誤的詳細資訊。
