---
title: 搜尋引擎
description: 訪客用來存取您網站的搜尋引擎。
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 1%

---


# 搜尋引擎

「搜尋引擎」維度會報告訪客用於到達您網站的搜尋引擎。 反向連結必須符合下列兩項，才能分類為搜尋引擎：

* 反向連結網域被Adobe識別為有效的搜尋引擎；
* 反向連結URL中存在關鍵字查詢字串參數。 查詢字串參數可以是空白的（因為隱私權規範，數個搜尋引擎也是如此）。

如果您想要區分付費和免費搜尋，則需 [要「付費搜尋](/help/admin/admin/paid-search-detection/paid-search-detection.md) 」偵測。 搜尋引擎可使用多個維度：

* **搜尋引擎**: 用於存取您網站的搜尋引擎，不論是付費還是免費。
* **搜尋引擎——付費**: 用來連接您網站的搜尋引擎，與付費搜尋偵測相符。
* **搜尋引擎——免費**: 用來連接您網站的搜尋引擎，其與付費搜尋偵測不符。

## 將資料填入此維度

此維度會參照Adobe內部的多個查閱表格。 每個值都以點擊的反 [向連結](referrer.md) 為基礎，這取決於 [內部URL篩選器](/help/admin/admin/internal-url-filter-admin.md)。 請確定已正確設定反向連結維度和內部URL篩選器。

## 維度值

維度值包括用來存取您網站的搜尋引擎。 範例值 `"Google"`包括、 `"Microsoft Bing"`和 `"DuckDuckGo"`。 維 `"Unspecified"` 度值是所有非搜尋流量。
