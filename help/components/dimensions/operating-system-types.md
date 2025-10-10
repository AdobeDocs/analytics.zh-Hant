---
title: 作業系統類型
description: 作業系統 (不論版本為何)。
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 53%

---

# 作業系統類型

「作業系統型別」[維度](overview.md)會顯示訪客使用的總體作業系統（不論特定版本為何）。 此維度不僅有助於了解哪些特定作業系統和版本最常見，也有助於了解訪客使用哪些典型作業系統平台。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱表格。查閱值以影像要求中 `User-Agent` 的 HTTP 標題為基礎。Adobe與[DeviceAtlas](https://deviceatlas.com/)合作，共同維護使用者代理程式與作業系統型別之間的查閱。

* 對於AppMeasurement實作，此維度可直接運作。
* 針對Web SDK實作，請在[!UICONTROL 設定資料流]時啟用[裝置查詢](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hant)。

## 維度項目

Dimension專案包含所使用的作業系統型別。 範例包括 `"Microsoft Windows"`、`"Apple Macintosh"`、`"Google Android"` 和 `"Apple iOS"`。
