---
title: 設定變數
description: 使用設定變數協助判斷資料的收集方式。
translation-type: tm+mt
source-git-commit: e9a876a1f562333056387d63de46a9cfe3fb3939

---


# 設定變數概觀

設定變數會控制資料在報表中擷取及處理的方式。它們通常不包含維度或量度值。

## 設定組態變數

在使用的JavaScript實 `AppMeasurement.js`作中，組態變數通常會設定在JS檔案的頂端。

在使用Adobe Experience Platform Launch的實作中，組態變數通常可透過設定Adobe Analytics擴充功能找到：

1. 使用您的 Adobe ID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下您要編輯的屬性。
3. Click the [!UICONTROL Extensions] tab, then Click [!UICONTROL Configure] under Adobe Analytics.

> [!IMPORTANT] 在呼叫track函式（或）之前，請確定已設定所有`t()` 組態 `tl()`變數。 請避免在函式中設定設定 `doPlugins()` 變數。
