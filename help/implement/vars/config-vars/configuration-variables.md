---
title: 設定變數
description: 使用設定變數協助判斷資料的收集方式。
feature: Variables
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 65%

---

# 設定變數概述

設定變數會控制資料在報表中擷取及處理的方式。這些變數通常不包含維度或量度值。

## 配置設定變數

在使用Web SDK擴充功能或Analytics擴充功能的實作中，通常會從擴充功能的設定中找到設定變數：

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 按一下[擴充功能]索引標籤]，然後按一下擴充功能下方的[設定]。[!UICONTROL 

在使用 `AppMeasurement.js` 的 JavaScript 實施中，通常會在 JS 檔案的頂端對配置設定變數。

>[!IMPORTANT]
>
>呼叫追蹤方法（[`t()`](../functions/t-method.md)或[`tl()`](../functions/tl-method.md)）之前，請確定所有設定變數均已設定完畢。 請避免在 [`doPlugins()`](../functions/doplugins.md) 函數中配置設定變數。
