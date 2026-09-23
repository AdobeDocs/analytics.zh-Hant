---
title: 平日/週末
description: 判斷點擊是發生在工作日還是週末。
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
TQID: https://experienceleague.adobe.com/9TJv-49ub1zHsgEGtBeoJVoHhsBktlOr7QhmgLdLRSo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
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
source-wordcount: '155'
ht-degree: 49%
---
# 平日/週末

「工作日/週末」[維度](overview.md)會針對點選是發生在工作日（星期一至星期五）還是週末（星期六至星期日）提供insight。 點擊的時間根據[報表套裝的時區](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)而定。

## 將資料填入此維度中

此維度衍生自每次點選的時間戳記；沒有可設定的變數。 其唯一的相依性是報表套裝的時區，時區會決定每個點選一週中的第幾天。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（衍生自點選時間戳記） |
| **網頁SDK / XDM欄位** | 無（衍生自點選時間戳記） |
| **查詢引數** | 不適用 |
| **XML標籤** | 不適用 |
| **位元組限制** | 不適用 |
| **持續性** | 點擊 |

## 維度項目

此維度一律包含剛好兩個維度項目：`"Weekday"` 和 `"Weekend"`。 維度項目 `"Weekday"` 會套用至星期一到星期五的所有點擊，而維度項目 `"Weekend"` 則套用至星期六和星期日的所有點擊。
