---
title: 付費搜尋
description: 區分付費和免費搜尋的量度。
feature: Dimensions
exl-id: b12665a3-e92f-4fc1-acd3-ea17a316e5e5
TQID: https://experienceleague.adobe.com/s9jhjGeXaOCo-Wz-Jyof951NZdRWfz-9tjrVrjHvTS0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 59%
---
# 付費搜尋

「付費搜尋」[維度](overview.md)可讓您檢視任何量度，並在付費搜尋和免費搜尋之間比較。 這會忽略搜尋引擎外的所有其他點擊次數。 此維度有助於了解您付費搜尋與有機搜尋的比較結果。

## 將資料填入此維度中

Adobe透過付費搜尋偵測衍生此維度，這會將搜尋引擎流量分類為付費或免費。 沒有可設定的變數。 唯一的要求是在報表套裝設定中正確設定[付費搜尋偵測](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md)。 如果正確設定付費搜尋偵測且報表套裝有資料，此維度會保持運作。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（由付費搜尋偵測衍生） |
| **網頁SDK / XDM欄位** | 無（由付費搜尋偵測衍生） |
| **查詢引數** | 不適用 |
| **XML標籤** | 不適用 |
| **位元組限制** | 不適用 |
| **持續性** | 不適用 |

## 維度項目

維度項目包含兩個靜態值：`"Natural"` 和 `"Paid"`。 如果造訪符合搜尋引擎的條件，也符合付費搜尋偵測，就屬於 `"Paid"` 維度項目。 如果造訪符合搜尋引擎的條件，但&#x200B;*不*&#x200B;符合付費搜尋偵測，則屬於 `"Natural"` 維度項目。
