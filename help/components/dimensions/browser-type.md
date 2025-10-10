---
title: 瀏覽器類型
description: 製作瀏覽器的組織。
feature: Dimensions
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 67%

---

# 瀏覽器類型

「瀏覽器型別」[維度](overview.md)會列出製作訪客所使用瀏覽器的組織。 若想查看訪客使用的主要瀏覽器，此維度相當實用。它提供「瀏覽器」維度的值，不會將相同瀏覽器的不同版本列為單獨的維度項目。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱表格。查閱值以影像要求中 `User-Agent` 的 HTTP 標題為基礎。Adobe與[DeviceAtlas](https://deviceatlas.com/)合作，共同維護使用者代理程式與瀏覽器之間的查閱。

* 對於AppMeasurement實作，此維度可直接運作。
* 針對Web SDK實作，請在[!UICONTROL 設定資料流]時啟用[裝置查詢](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hant)。

## 維度項目

維度項目包括製作瀏覽器的組織。常見維度項目包含 `"Google"` ([!DNL Chrome] 的製作者)、`"Apple"` ([!DNL Safari] 的製作者)、`"Microsoft"` ([!DNL Edge] 的製作者) 和 `"Mozilla"` ([!DNL Firefox] 的製作者)。
