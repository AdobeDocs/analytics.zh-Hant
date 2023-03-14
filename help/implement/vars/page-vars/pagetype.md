---
title: pageType
description: 判斷目前頁面是否為 404 錯誤。
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
source-git-commit: 8a6c639af7427a9975ccd061d059696d4611dff3
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 100%

---

# pageType

`pageType` 變數是用來標出網站上錯誤頁面 (如 404 錯誤) 的標幟。如果此變數包含字串 `errorPage`，則會填入「找不到頁面」[維度](/help/components/dimensions/pages-not-found.md)和[量度](/help/components/metrics/pages-not-found.md)。

>[!IMPORTANT]
>
>請勿在非錯誤頁面上設定此變數。

## 使用 Web SDK 的頁面類型

頁面類型會在 XDM 欄位 `web.webPageDetails.isErrorPage` 底下，[為 Adobe Analytics 進行對應](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=zh-Hant)。此 XDM 欄位是一個布林值；可將其設定為 `true` 以將它標記為錯誤頁面，如果它不是錯誤頁面，則將其設定為 `false`。將布林值發送到 Analytics 報表套裝時，Adobe 會自動將其轉換為字串值 `errorPage`。

## 使用 Adobe Analytics 擴充功能的頁面類型

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement 和 Analytics 擴充功能自訂程式碼編輯器中的 s.pageType

`s.pageType` 變數是字串，而 `errorPage` 值是唯一的有效值。在網站上的任何錯誤頁面 (如 404 頁面) 上，將此變數設為此值。

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>使用 eVar 來收集錯誤代碼，以便取得訪客在網站上遇到哪些具體錯誤的詳細資訊。
