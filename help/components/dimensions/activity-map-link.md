---
description: 被點按的連結名稱。
title: Activity Map 連結
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Dimensions
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
TQID: https://experienceleague.adobe.com/A5HaPb0TghRKVykJ9V2UMJ0mlsYElLkCyBwxzTd6VII
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
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 11%
---
# Activity Map 連結

「Activity Map連結」[維度](overview.md)會顯示最常被點按的連結。 您可以使用此維度來比較網站上最常使用哪些連結，無論連結的點按位置為何。

## 將資料填入此維度中

此維度會從[內容資料變數](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link`擷取資料。 如果您的實作使用[Activity Map](/help/analyze/activity-map/overview.md)，此內容資料變數會在點按連結時自動收集資料。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（由[Activity Map](/help/analyze/activity-map/overview.md)模組收集） |
| **網頁SDK / XDM欄位** | 無（由[Activity Map](/help/analyze/activity-map/overview.md)模組收集） |
| **查詢引數** | 不適用 |
| **XML標籤** | 不適用 |
| **位元組限制** | 255位元組 |
| **持續性** | 不適用 |

對於點按的指定連結，Activity Map會依序搜尋下列專案：

1. `s_objectID`變數
1. 連結的內部文字
1. 影像的`alt`屬性
1. `title`屬性
1. 影像的`src`屬性
1. 表單的`action`屬性

如果點按的元素不含上述任何條件，Activity Map就不會收集該點按的資料。

## 維度項目

Dimension專案包含連結文字或訪客點按的其他連結屬性。 您組織的網站結構和實作會決定收集的確切值。
