---
title: 設定變數
description: 使用設定變數協助判斷資料的收集方式。
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 68%

---

# 設定變數概述

設定變數會控制資料在報表中擷取及處理的方式。這些變數通常不包含維度或量度值。

## 配置設定變數

在使用 `AppMeasurement.js` 的 JavaScript 實施中，通常會在 JS 檔案的頂端對配置設定變數。

在使用Adobe Experience Platform標籤的實作中，設定變數通常可透過設定Adobe Analytics擴充功能找到：

1. 使用您的AdobeID憑證登入[資料收集UI](https://experience.adobe.com/data-collection)。
1. 按一下您要編輯的屬性。
1. 按一下[!UICONTROL 「擴充功能」]標籤，然後按一下 Adobe Analytics 下方的[!UICONTROL 「設定」]。

>[!IMPORTANT]
>
>呼叫追蹤方法 ([`t()`](../functions/t-method.md) 或 [`tl()`](../functions/tl-method.md)) 之前，請確定所有設定變數均已設定完畢。請避免在 [`doPlugins()`](../functions/doplugins.md) 函數中配置設定變數。
