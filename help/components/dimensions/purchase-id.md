---
title: 購買 ID
description: 適用於購買的唯一識別碼，可在Data Warehouse中使用。
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
source-wordcount: '124'
ht-degree: 18%
---
# 購買 ID

「購買識別碼」[維度](overview.md)提供購買的唯一識別碼。

>[!IMPORTANT]
>
>此維度僅在 Data Warehouse 中可用。

## 將資料填入此維度中

此維度是使用[`purchaseID`](/help/implement/vars/page-vars/purchaseid.md)變數設定的。 它對應至資料摘要中的`purchaseid`欄。 如需詳細資訊，請參閱[資料行參考](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md)。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) |
| **網頁SDK / XDM欄位** | [`commerce.order.purchaseID`](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/field-groups/event/commerce-details) |
| **查詢引數** | [`purchaseID`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML標籤** | [`<purchaseId>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **位元組限制** | 20位元組 |
| **持續性** | 點擊 |

## 維度項目

Dimension專案包含在您的網站上收集的購買ID。
