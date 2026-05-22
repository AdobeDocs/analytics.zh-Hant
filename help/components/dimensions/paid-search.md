---
title: 付費搜尋
description: 區分付費和免費搜尋的量度。
feature: Dimensions
exl-id: b12665a3-e92f-4fc1-acd3-ea17a316e5e5
TQID: https://experienceleague.adobe.com/s9jhjGeXaOCo-Wz-Jyof951NZdRWfz-9tjrVrjHvTS0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 148
ht-degree: 87%

---

# 付費搜尋

「付費搜尋」[維度](overview.md)可讓您檢視任何量度，並在付費搜尋和免費搜尋之間比較。 這會忽略搜尋引擎外的所有其他點擊次數。 此維度有助於了解您付費搜尋與有機搜尋的比較結果。

## 將資料填入此維度中

此維度正常運作唯一的要求是在報表套裝設定中正確設定[「付費搜尋偵測」](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md)。 如果正確設定付費搜尋偵測且報表套裝有資料，此維度會保持運作。

## 維度項目

維度項目包含兩個靜態值：`"Natural"` 和 `"Paid"`。 如果造訪符合搜尋引擎的條件，也符合付費搜尋偵測，就屬於 `"Paid"` 維度項目。 如果造訪符合搜尋引擎的條件，但&#x200B;*不*&#x200B;符合付費搜尋偵測，則屬於 `"Natural"` 維度項目。
