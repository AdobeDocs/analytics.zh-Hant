---
title: 上午/下午
description: 判斷點擊發生在上午還是下午。
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
TQID: https://experienceleague.adobe.com/R1syrJ7ylIe2ywH1isX4sjR2O84-8eL-jooYhjUdKhI
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
source-wordcount: '159'
ht-degree: 33%
---
# 上午/下午

&#39;AM/PM&#39; [維度](overview.md)會提供點選發生在上午還是下午insight。 點擊的時間根據[報表套裝的時區](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)而定。

## 將資料填入此維度中

此維度衍生自每次點選的時間戳記；沒有可設定的變數。 其唯一的相依性是報表套裝的時區，時區會決定哪些時間是上午，哪些時間是下午。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（衍生自點選時間戳記） |
| **網頁SDK / XDM欄位** | 無（衍生自點選時間戳記） |
| **查詢引數** | 不適用 |
| **XML標籤** | 不適用 |
| **位元組限制** | 不適用 |
| **持續性** | 點擊 |

## 維度項目

此維度一律包含剛好兩個維度項目：`"AM"` 和 `"PM"`。 維度專案`"AM"`會套用至凌晨12:00到中午11:59的所有點選，而維度專案`"PM"`則會套用至中午12:00到晚上11:59的所有點選。
