---
title: pageType
description: 判斷目前頁面是否為 404 錯誤。
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 77%

---

# pageType

`pageType` 變數是用來標出網站上錯誤頁面 (如 404 錯誤) 的標幟。如果此變數包含字串 `errorPage`，則會填入「找不到頁面」維度。

>[!IMPORTANT]
>
>請勿在非錯誤頁面上設定此變數。

## 使用Adobe Analytics副檔名的頁面類型

Adobe Analytics擴展中沒有專用欄位可使用此變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴展自定義代碼編輯器中的s.pageType

`s.pageType` 變數是字串，而 `errorPage` 值是唯一的有效值。在網站上的任何錯誤頁面 (如 404 頁面) 上，將此變數設為此值。

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>使用 eVar 來收集錯誤代碼，以便取得訪客在網站上遇到哪些具體錯誤的詳細資訊。
