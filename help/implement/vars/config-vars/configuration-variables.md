---
title: 設定變數
description: 使用設定變數協助判斷資料的收集方式。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 設定變數概述

設定變數會控制資料在報表中擷取及處理的方式。這些變數通常不包含維度或量度值。

## 配置設定變數

在使用 `AppMeasurement.js` 的 JavaScript 實施中，通常會在 JS 檔案的頂端對配置設定變數。

在使用 Adobe Experience Platform Launch 的實施中，設定變數通常可透過設定 Adobe Analytics 擴充功能找到：

1. 使用您的 Adobe ID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下您要編輯的屬性。
3. Click the [!UICONTROL Extensions] tab, then Click [!UICONTROL Configure] under Adobe Analytics.

>[!IMPORTANT] 在呼叫追蹤方法（或）之前，請確定已設定所有[`t()`](../functions/t-method.md) 組態 [`tl()`](../functions/tl-method.md)變數。 請避免在 [`doPlugins()`](../functions/doplugins.md) 函數中配置設定變數。
