---
title: 搜尋關鍵字
description: 訪客用來存取您網站的搜尋關鍵字。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---


# 搜尋關鍵字

「搜尋關鍵字」維度會報告訪客用於進入您網站的搜尋關鍵字。

>[!IMPORTANT]
>
>由於隱私權實務的增加，大部分搜尋引擎不再傳遞搜尋關鍵字。 Adobe識別搜尋引擎但維度項目下遺失關鍵字群組的點擊 `"Keyword unavailable"`。

反向連結必須符合下列兩項，才能分類為搜尋關鍵字：

* 反向連結網域被Adobe識別為有效的 [搜尋引擎](search-engine.md);
* 反向連結URL中存在關鍵字查詢字串參數。 如果關鍵字查詢字串存在但不包含值，則會在維度項目下分組 `"Keyword unavailable"`。

如果您想要區分付費和免費搜尋，則需 [要「付費搜尋](/help/admin/admin/paid-search-detection/paid-search-detection.md) 」偵測。 搜尋關鍵字可使用多個維度：

* **搜尋關鍵字**: 用來存取您網站的搜尋關鍵字，不論是付費還是免費。
* **搜尋關鍵字——付費**: 用來連接您網站的搜尋關鍵字，與付費搜尋偵測相符。
* **搜尋關鍵字——免費**: 用來存取您網站的搜尋關鍵字，其與付費搜尋偵測不符。

## 將資料填入此維度

此維度會參照Adobe內部的多個查閱表格。 每個值都以點擊的反 [向連結](referrer.md) 為基礎，這取決於 [內部URL篩選器](/help/admin/admin/internal-url-filter-admin.md)。 請確定已正確設定反向連結維度和內部URL篩選器。

## 維度項目

維度項目包括用來存取您網站的搜尋關鍵字。 維 `"Unspecified"` 度項目是所有非搜尋流量。
