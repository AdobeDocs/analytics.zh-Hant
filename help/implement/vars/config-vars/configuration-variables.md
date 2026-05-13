---
title: 設定變數
description: 使用設定變數協助判斷資料的收集方式。
feature: Appmeasurement Implementation
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
role: Admin, Developer
TQID: https://experienceleague.adobe.com/amtLWIgyADqWBOv38xdJ6AF4IjhJ0aGVrvYqXLckfkI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 126
ht-degree: 65%

---

# 設定變數概觀

設定變數會控制資料在報表中擷取及處理的方式。 這些變數通常不包含維度或量度值。

## 配置設定變數

在使用Web SDK擴充功能或Analytics擴充功能的實作中，通常會從擴充功能的設定中找到設定變數：

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 按一下[擴充功能]索引標籤]，然後按一下擴充功能下方的[設定]。[!UICONTROL 

在使用 `AppMeasurement.js` 的 JavaScript 實施中，通常會在 JS 檔案的頂端對配置設定變數。

>[!IMPORTANT]
>
>呼叫追蹤方法（[`t()`](../functions/t-method.md)或[`tl()`](../functions/tl-method.md)）之前，請確定所有設定變數均已設定完畢。 請避免在 [`doPlugins()`](../functions/doplugins.md) 函數中配置設定變數。
