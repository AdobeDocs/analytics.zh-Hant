---
title: 月份
description: 一年中的數值月份，無論是哪一年。
feature: Dimensions
exl-id: ed2887f2-46e7-48a4-b337-f59177c7558c
TQID: https://experienceleague.adobe.com/W62Cro1mGRZnEY-v1ilx9Dw1Xu0qR4t-KSVkOpG8RGY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
source-wordcount: '171'
ht-degree: 61%
---
# 月份

「月份」[維度](overview.md)會將任何指定年份的月份報告為維度專案。 如果您想要依月份劃分報表，但不要以靜態日期作為維度項目，此報表就十分實用。 您可以依月份彙總逐年比較報表，藉以在相同的維度項目中彙總今年 1 月的資料與去年 1 月的資料。

## 將資料填入此維度中

此維度衍生自每次點選的時間戳記。 沒有變數可供設定；其可直接用於任何實施作業。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（衍生自點選時間戳記） |
| **網頁SDK / XDM欄位** | 無（衍生自點選時間戳記） |
| **查詢引數** | 不適用 |
| **XML標籤** | 不適用 |
| **位元組限制** | 不適用 |
| **持續性** | 點擊 |

## 維度項目

維度項目包含月份 (`January` 至 `December`)，代表點擊發生的月份。
