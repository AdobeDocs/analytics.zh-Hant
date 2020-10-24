---
title: 付費搜尋
description: 區分付費和免費搜尋的量度。
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '148'
ht-degree: 100%

---


# 付費搜尋

「付費搜尋」維度可讓您查看任何量度，並在付費搜尋和免費搜尋之間比較。這會忽略搜尋引擎外的所有其他點擊次數。此維度有助於了解您付費搜尋與有機搜尋的比較結果。

## 將資料填入此維度中

此維度正常運作唯一的要求是在報表套裝設定中正確設定[「付費搜尋偵測」](/help/admin/admin/paid-search-detection/paid-search-detection.md)。如果正確設定付費搜尋偵測且報表套裝有資料，此維度會保持運作。

## 維度項目

維度項目包含兩個靜態值：`"Natural"` 和 `"Paid"`。如果造訪符合搜尋引擎的條件，也符合付費搜尋偵測，就屬於 `"Paid"` 維度項目。如果造訪符合搜尋引擎的條件，但&#x200B;*不*&#x200B;符合付費搜尋偵測，則屬於 `"Natural"` 維度項目。
