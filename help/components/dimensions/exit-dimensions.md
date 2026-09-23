---
title: 退出維度
description: 列出退出維度及其使用情形。
keywords: 退出頁面、退出網站區段、退出伺服器、退出自訂洞察
feature: Dimensions
exl-id: b2b1ee88-e5c3-44b5-8159-85ec53d20258
TQID: https://experienceleague.adobe.com/YRjvhW8OzBlip9ok0-1D4rYSljkccpIAlDkqCQv7nyo
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
source-wordcount: '234'
ht-degree: 74%
---
# 退出維度

>[!BEGINSHADEBOX]

*此說明頁面說明退出作為[維度](overview.md)時的運作方式。 若要瞭解退出作為量度時的運作方式，請參閱[退出](../metrics/exits.md)量度。*

>[!ENDSHADEBOX]

退出維度會記錄最後一個維度項目，並將其回溯套用至造訪中所有的點擊。 報表套裝設定中的[流量變數](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)下方所有已啟用路徑分析的變數，都可使用退出維度。

## 將資料填入退出維度中

指定的退出維度以其相關聯的流量變數為基礎。 Adobe會從造訪期間檢視的最後一個該變數值衍生每個退出維度；沒有要設定的專用變數。 如果非退出變數有資料，則其相關聯的退出維度也會包含資料。 如果您的流量變數包含資料，即無須對退出維度進行實施變更。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（衍生自訪客的上次點選） |
| **網頁SDK / XDM欄位** | 無（衍生自訪客的上次點選） |
| **查詢引數** | 不適用 |
| **XML標籤** | 不適用 |
| **位元組限制** | 不適用 |
| **持續性** | 造訪 |

## 維度項目

由於退出變數通常以您實作中的自訂字串為基礎，因此您的組織會決定維度項目。 指定退出維度中的值會與其相關聯的非退出維度中的維度項目相符。 例如，「退出頁面」維度中的維度項目，會與「頁面」維度中的維度項目相似。
