---
title: 付費搜尋
description: 區分量度與付費和免費搜尋。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---


# 付費搜尋

「付費搜尋」維度可讓您查看任何量度，並比較付費搜尋和免費搜尋之間的量度。 會忽略搜尋引擎以外的所有其他點擊。 此維度有助於瞭解您的付費搜尋工作與有機搜尋的比較。

## 將資料填入此維度

此維度要正常運作，唯一的要求是在報表套裝設定中 [正確設定付費搜尋偵測](/help/admin/admin/paid-search-detection/paid-search-detection.md) 。 如果付費搜尋偵測已正確設定且報表套裝有資料，此維度一律有效。

## 維度項目

維度項目包含兩個靜態值： `"Natural"` 和 `"Paid"`。 如果瀏覽符合搜尋引擎的標準，也符合付費搜尋偵測，則屬於維 `"Paid"` 度項目。 如果瀏覽符合搜尋引擎的條件，但 *不符合* 「付費搜尋偵測」，則屬於維 `"Natural"` 度項目。
