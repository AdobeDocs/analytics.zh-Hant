---
title: pageType
description: 判斷目前頁面是否為 404 錯誤。
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
source-git-commit: 8a6c639af7427a9975ccd061d059696d4611dff3
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 56%

---

# pageType

`pageType` 變數是用來標出網站上錯誤頁面 (如 404 錯誤) 的標幟。如果此變數包含字串 `errorPage`，則會填入「找不到頁面」 [維度](/help/components/dimensions/pages-not-found.md) 和 [量度](/help/components/metrics/pages-not-found.md).

>[!IMPORTANT]
>
>請勿在非錯誤頁面上設定此變數。

## 使用Web SDK的頁面類型

頁面類型為 [已對應至Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) 在XDM欄位下 `web.webPageDetails.isErrorPage`. 此XDM欄位是布林值；將其設定為 `true` 將其標幟為錯誤頁面，或 `false` 如果不是錯誤頁面。 Adobe會自動將布林值轉譯為字串值 `errorPage` 傳送至Analytics報表套裝時。

## 使用Adobe Analytics擴充功能的頁面類型

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.pageType

`s.pageType` 變數是字串，而 `errorPage` 值是唯一的有效值。在網站上的任何錯誤頁面 (如 404 頁面) 上，將此變數設為此值。

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>使用 eVar 來收集錯誤代碼，以便取得訪客在網站上遇到哪些具體錯誤的詳細資訊。
