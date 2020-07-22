---
title: 瀏覽器
description: 使用的瀏覽器名稱和版本。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 1%

---


# 瀏覽器

「瀏覽器」維度會報告傳送點擊之瀏覽器的名稱和版本。 此維度對於瞭解訪客最常使用的瀏覽器非常有用。 在測試新版網站時，您可以在此維度的主要瀏覽器上執行這些測試，以發揮最佳品質控制效果。

## 將資料填入此維度

此維度會參照Adobe內部的查閱表格。 查閱值是以影像請求中 `User-Agent` 的HTTP標題為基礎。 如果您使用AppMeasurement程式庫（例如透過Adobe Experience Platform Launch），此維度就可立即運作。

## 維度項目

維度項目包括使用的瀏覽器名稱和版本。 相同瀏覽器的不同版本是個別的維度項目。

有些維度項目包 `"(unknown version)"` 含的不是版本號碼。 此維度項目會參照Adobe尚未新增至其查閱表格的最新瀏覽器版本。 由於瀏覽器經常更新， `"(unknown version)"` 所以特定瀏覽器的更新是常見和暫時的。 Adobe通常會在每月維護髮行期間更新查閱表格。
