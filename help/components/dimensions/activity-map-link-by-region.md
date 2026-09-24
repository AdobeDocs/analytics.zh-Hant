---
title: Activity Map 連結 (依地區)
description: 連結和區域的串連值。
feature: Dimensions
role: User, Admin
exl-id: 33014dc1-da4e-47b7-b73c-3e89e04f3ed6
TQID: https://experienceleague.adobe.com/xvYVA064hA0rsBdnLpxXllq3PD0zYAikFRjc6xNErvg
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
source-wordcount: '188'
ht-degree: 13%
---
# Activity Map 連結 (依地區)

「依地區的Activity Map連結」 [維度](overview.md)顯示[Activity Map連結](activity-map-link.md)和[Activity Map地區](activity-map-link-by-region.md)的串連。 如果您的連結名稱類似，但位於網站的不同區域，此維度就十分實用。 例如，如果您有多個首頁的連結全部標示為「首頁」，您可以使用此維度來區分每個網站區域中的這些連結。

## 將資料填入此維度中

此維度會從[內容資料變數](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link`和`c.a.activitymap.region`擷取資料。 這兩個值會串連並以縱線符號(`|`)分隔。 如果您的實作使用[Activity Map](/help/analyze/activity-map/overview.md)，這些內容資料變數會在點按連結時自動收集資料。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（由[Activity Map](/help/analyze/activity-map/overview.md)模組收集） |
| **網頁SDK / XDM欄位** | 無（由[Activity Map](/help/analyze/activity-map/overview.md)模組收集） |
| **查詢引數** | 不適用 |
| **XML標籤** | 不適用 |
| **位元組限制** | 255位元組 |
| **持續性** | 不適用 |

## 維度項目

Dimension專案包含來自[Activity Map連結](activity-map-link.md)和[Activity Map地區](activity-map-link-by-region.md)的值。 您組織的網站結構和實作會決定收集的確切值。
