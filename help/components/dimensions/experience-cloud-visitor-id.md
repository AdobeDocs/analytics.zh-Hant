---
title: Experience Cloud 訪客 ID
description: 訪客的Experience Cloud ID (ECID)，可在Data Warehouse中使用。
feature: Dimensions
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
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 18%
---
# Experience Cloud 訪客 ID

「Experience Cloud訪客ID」[維度](overview.md)會提供每個訪客的ECID。 這是一個128位元的數字，由兩個串連的64位元數字組成，兩個數字加到19位數。

>[!IMPORTANT]
>
>此維度僅在 Data Warehouse 中可用。

## 將資料填入此維度中

此維度需要實作，才能使用訪客ID服務(VisitorAPI)或Experience Platform Identity服務。 它對應至資料摘要中的`mcvisid`欄。 如需詳細資訊，請參閱[資料行參考](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md)。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（由Experience Cloud訪客ID服務設定） |
| **網頁SDK / XDM欄位** | 無（由Experience Cloud Identity Service設定） |
| **查詢引數** | [`mid`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML標籤** | [`<marketingCloudVisitorId>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **位元組限制** | 不適用 |
| **持續性** | 不適用 |

## 維度項目

Dimension專案包含每個訪客的Experience Cloud ID。
