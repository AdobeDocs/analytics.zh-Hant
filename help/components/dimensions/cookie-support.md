---
title: Cookie支援
description: 判斷瀏覽器是否支援Cookie。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 1%

---


# Cookie 支援

「Cookie支援」維度會報告瀏覽器是否支援指定點擊的Cookie。 這可用來判斷使用支援Cookie的瀏覽器的訪客與有意停用Cookie的訪客比例。

## 將資料填入此維度

此維度會從影像請求中 [`k` 的查詢字串](/help/implement/validate/query-parameters.md) 收集資料。 AppMeasurement會嘗試設定名為的Cookie `s_cc`，然後偵測Cookie是否存在。 結果是查詢字串參數值(如 `Y` 果瀏覽器支援並啟用Cookie)或 `N` （如果瀏覽器停用Cookie）。 如果您使用AppMeasurement（例如透過Adobe Experience Platform Launch），此維度將立即可用。 如果您在AppMeasurement以外使用資料收集方法（例如透過API），請務必在每個點擊上加入查詢字串參數，並附帶值 `k` 或 `Y``N`。

## 維度項目

維度項目 `Enabled`包括、 `Disabled`和 `Unknown`。

* **`Enabled`**: 瀏覽器支援Cookie，並啟用它們。
* **`Disabled`**: 瀏覽器不支援Cookie，或訪客已停用它們。
* **`Unknown`**: AppMeasurement無法決定Cookie支援。 查 `k` 詢字串不存在於影像要求中。
