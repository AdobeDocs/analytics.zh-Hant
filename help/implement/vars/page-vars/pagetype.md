---
title: pageType
description: 判斷目前頁面是否為 404 錯誤。
feature: Appmeasurement Implementation
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 75%

---

# pageType

`pageType` 變數是用來標出網站上錯誤頁面 (如 404 錯誤) 的標幟。如果此變數包含字串 `errorPage`，則會填入「找不到頁面」[維度](/help/components/dimensions/pages-not-found.md)和[量度](/help/components/metrics/pages-not-found.md)。

>[!IMPORTANT]
>
>請勿在非錯誤頁面上設定此變數。

## 使用 Web SDK 的頁面類型

管道已對應至下列變數：

* [XDM物件](/help/implement/aep-edge/xdm-var-mapping.md)： `xdm.web.webPageDetails.isErrorPage` — 此XDM欄位是布林值；將其設為`true`以將其標幟為錯誤頁面，或若不是錯誤頁面則設為`false`。
* [資料物件](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.pageType` — 此資料物件欄位是字串；請將其設定為`"errorPage"`以標示其為字串。

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
