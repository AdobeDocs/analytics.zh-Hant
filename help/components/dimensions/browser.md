---
title: 瀏覽器
description: 使用的瀏覽器名稱和版本。
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '177'
ht-degree: 100%

---

# 瀏覽器

「瀏覽器」維度會報告傳送點擊的瀏覽器名稱和版本。此維度對於了解訪客最常使用的瀏覽器很實用。測試新版網站時，您可以在此維度的前幾大瀏覽器上執行這些測試，以發揮最佳品質控制效果。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱表格。查閱值以影像要求中 `User-Agent` 的 HTTP 標題為基礎。如果您使用 AppMeasurement 程式庫 (例如，透過 Adobe Experience Platform Launch)，此維度將可立即運作。

## 維度項目

維度項目包括使用的瀏覽器名稱和版本。相同瀏覽器的不同版本是分別的維度項目。

部分維度項目包含 `"(unknown version)"`，而不是版本號碼。此維度項目會參照 Adobe 尚未新增至其查閱表格的最新瀏覽器版本。由於瀏覽器經常更新，所以特定瀏覽器的 `"(unknown version)"` 為通用且暫時。Adobe 一般會在每月維護版本更新查閱表格。
