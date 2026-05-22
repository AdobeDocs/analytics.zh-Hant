---
title: pageType
description: 判斷目前頁面是否為 404 錯誤。
feature: Appmeasurement Implementation
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/SD-hwWJmZby-y99FIZHrnevSBsVqD6T5gwovn5tJfxo'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 202
ht-degree: 75%

---

# pageType

`pageType` 變數是用來標出網站上錯誤頁面 (如 404 錯誤) 的標幟。 如果此變數包含字串 `errorPage`，則會填入「找不到頁面」[維度](/help/components/dimensions/pages-not-found.md)和[量度](/help/components/metrics/pages-not-found.md)。

>[!IMPORTANT]
>
>請勿在非錯誤頁面上設定此變數。

## 使用 Web SDK 的頁面類型

管道已對應至下列變數：

* [XDM物件](/help/implement/aep-edge/xdm-var-mapping.md)： `xdm.web.webPageDetails.isErrorPage` — 此XDM欄位是布林值；將其設為`true`以將其標幟為錯誤頁面，或若不是錯誤頁面則設為`false`。
* [資料物件](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.pageType` — 此資料物件欄位是字串；請將其設定為`"errorPage"`以標示其為字串。

## 使用 Adobe Analytics 擴充功能的頁面類型

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement 和 Analytics 擴充功能自訂程式碼編輯器中的 s.pageType

`s.pageType` 變數是字串，而 `errorPage` 值是唯一的有效值。 在網站上的任何錯誤頁面 (如 404 頁面) 上，將此變數設為此值。

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>使用 eVar 來收集錯誤代碼，以便取得訪客在網站上遇到哪些具體錯誤的詳細資訊。
