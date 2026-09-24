---
title: 小時
description: 量度發生的小時。
feature: Dimensions
exl-id: 323c46dd-87d0-487a-b954-e5ccbc1b919d
TQID: https://experienceleague.adobe.com/Gkigdxnrted-gkPoGCQMx229EvCmVvSt9Rr5QP-IfGU
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 78%
---
# 小時

「小時」[維度](overview.md)會報告指定量度發生的小時（無條件舍去）。 第一個維度項目是日期範圍中的第一小時，最後一個維度項目是日期範圍中的最後一小時。 此維度可讓您查看量度在一段時間內變化，因此對趨勢報表而言十分重要。

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

維度項目包含報表日期範圍內的指定小時和其日期。 格式為 `HH:HH YYYY-MM-DD`。

## 日光節約時間

日光節約時間慣例是在春季將時鐘往前設定一小時，並在秋季將時鐘往後設定一小時。 如果報告套裝的時區使用 DST，Adobe 會相應調整該小時的資料。

* **日光節約時間開始時**：三月時，報表通常會在日光節約時間開始的資料中顯示一個小時間隔。 該小時不存在，因此它不屬於資料彙集的一部分。 請注意，少量資料仍可能歸入這個小時中。 Adobe 資料彙集伺服器需花幾秒鐘時間 (最多一分鐘) 才能將 DST 調整納入考量。
* **日光節約時間結束時**：十一月時，報表通常會在日光節約時間結束時顯示雙重堆疊小時。 該小時發生了兩次，因此兩個小時都會在報表中彙總。
