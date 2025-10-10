---
title: 瀏覽器
description: 使用的瀏覽器名稱和版本。
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
source-git-commit: 206df584deab5f6f9b8eeb09d9c8ad4983424eea
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 58%

---

# 瀏覽器

&#39;[!UICONTROL 瀏覽器]&#39; [維度](overview.md)會報告傳送點選的瀏覽器名稱和版本。 如果您想要測量訪客最常使用的瀏覽器，此維度就十分實用。 測試新版網站時，您可以在此維度的前幾大瀏覽器上執行這些測試，以發揮最佳品質控制效果。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱表格。查閱值以影像要求中 `User-Agent` 的 HTTP 標題為基礎。Adobe與[DeviceAtlas](https://deviceatlas.com/)合作，共同維護使用者代理程式與瀏覽器之間的查閱。

* 對於AppMeasurement實作，此維度可直接運作。
* 針對Web SDK實作，請在[!UICONTROL 設定資料流]時啟用[裝置查詢](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html)。

## 維度項目

維度項目包括使用的瀏覽器名稱和版本。相同瀏覽器的不同版本是分別的維度項目。

部分維度項目包含 `"(unknown version)"`，而不是版本號碼。此維度專案會參考Adobe尚未新增至其查閱表格的最新瀏覽器版本。 由於瀏覽器經常更新，所以特定瀏覽器的 `"(unknown version)"` 為通用且暫時。Adobe 一般會在每月維護版本更新查閱表格。