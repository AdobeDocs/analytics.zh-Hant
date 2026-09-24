---
title: 月
description: 量度發生的月份。
feature: Dimensions
exl-id: 77f7aa91-ea2e-482f-9a29-35912efb967a
TQID: https://experienceleague.adobe.com/wLCMW-pAsREGJV84IBPuae75Rwz6dWhL8TyxedyeH-U
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
source-wordcount: '138'
ht-degree: 56%
---
# 月

「月」[維度](overview.md)會報告指定量度發生的月份。 第一個維度項目是日期範圍中的第一個月，最後一個維度項目是日期範圍中的最後一個月。 此維度可讓您查看量度在一段時間內變化，因此對趨勢報表而言十分重要。

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

維度項目包含指定日期的月份和年份。
