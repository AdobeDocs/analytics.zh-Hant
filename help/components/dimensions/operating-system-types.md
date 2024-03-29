---
title: 作業系統類型
description: 作業系統 (不論版本為何)。
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 55%

---

# 作業系統類型

「作業系統型別」 [維度](overview.md) 顯示訪客使用的主要作業系統（不論版本為何）。 此維度不僅有助於了解哪些特定作業系統和版本最常見，也有助於了解訪客使用哪些典型作業系統平台。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱表格。查閱值以影像要求中 `User-Agent` 的 HTTP 標題為基礎。與合作夥伴Adobe [DeviceAtlas](https://deviceatlas.com/) 維護使用者代理程式與作業系統型別之間的查閱。

* 對於AppMeasurement實作，此維度可立即運作。
* 對於Web SDK實作，啟用 [!UICONTROL 裝置查詢] 當 [設定資料串流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## 維度項目

Dimension專案包括使用的作業系統型別。 範例包括 `"Microsoft Windows"`、`"Apple Macintosh"`、`"Google Android"` 和 `"Apple iOS"`。
