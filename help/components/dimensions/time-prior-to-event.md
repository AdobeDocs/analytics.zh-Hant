---
title: 事件之前時間
description: 量度與造訪的首次點擊之間相隔的時間量。
feature: Dimensions
exl-id: 2586673f-d908-4b69-901a-5fafe635d0d5
TQID: https://experienceleague.adobe.com/vO3S-yZwV7KSLmIzRfwNDrVaB3NzpsIocmHsAaamfj0
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
source-wordcount: '197'
ht-degree: 53%
---
# 事件之前時間

「事件之前時間」維度[維度](overview.md)會報告造訪的首次點選與所需量度之間經過的時間量。 此維度可用來判斷達成成功事件 (例如表單提交或購買) 所花費的時間量。

## 將資料填入此維度中

Adobe會從造訪的首次點選與target事件之間經過的時間來計算此維度伺服器端。 沒有可設定的變數。 雖然從技術上講，這都是現成可用的功能，但在您的網站上實作自訂和購買事件時，效果最佳。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（由Adobe計算） |
| **網頁SDK / XDM欄位** | 無（由Adobe計算） |
| **查詢引數** | 不適用 |
| **XML標籤** | 不適用 |
| **位元組限制** | 不適用 |
| **持續性** | 不適用 |

## 維度項目

維度項目包含以時間為基礎的貯體，範圍介於 `"Less than 1 minute"` 到 `"More than 15 hours"` 之間。 例如，如果某個訪客從首次點擊到購買花了 23 分鐘，則會歸類於 `"10 to 30 minutes"` 維度項目下。 無法為此量度自訂值區。
