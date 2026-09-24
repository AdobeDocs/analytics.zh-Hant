---
title: 訪客 ID
description: 訪客的唯一識別碼，可在Data Warehouse中使用。
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
source-wordcount: '133'
ht-degree: 18%
---
# 訪客 ID

「訪客識別碼」[維度](overview.md)提供每個訪客的唯一識別碼。

>[!IMPORTANT]
>
>此維度僅在 Data Warehouse 中可用。

## 將資料填入此維度中

Adobe會自動為每個訪客產生訪客ID。 這個值與資料摘要中`visid_high`與`visid_low`欄的串連值相同。 您可以使用`visitorID`變數覆寫自動產生的值。 如需詳細資訊，請參閱[資料行參考](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md)。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | [`visitorID`](/help/implement/vars/config-vars/visitorid.md) |
| **網頁SDK / XDM欄位** | 無 |
| **查詢引數** | [`vid`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML標籤** | [`<visitorId>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **位元組限制** | 255位元組 |
| **持續性** | 不適用 |

## 維度項目

Dimension專案包含每個訪客的唯一識別碼。
