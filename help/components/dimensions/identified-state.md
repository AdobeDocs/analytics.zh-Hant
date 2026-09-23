---
title: 已識別的狀態
description: 決定拼接識別的旗標。
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
TQID: https://experienceleague.adobe.com/JUBtgXBDboIgX0xbvuflF5q-oEwqHx4vKvJd0Y5XMLY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
source-wordcount: '175'
ht-degree: 46%
---
# 已識別的狀態

「識別的狀態」[維度](overview.md)是[跨裝置分析](../cda/overview.md)虛擬報表套裝的專屬維度。 它會報告在執行報告時系統是否識別 (拼接) 點擊。 此維度有助於了解 CDA 拚接或「壓縮」資料的程度。

## 將資料填入此維度中

此維度是由執行報告時的[跨裝置分析](../cda/overview.md)根據每次點選是否與個人連結而計算。 只要為虛擬報表套裝設定跨裝置分析，就能立即運作；沒有變數可供設定。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（由Cross-Device Analytics計算） |
| **網頁SDK / XDM欄位** | 無（由Cross-Device Analytics計算） |
| **查詢引數** | 不適用 |
| **XML標籤** | 不適用 |
| **位元組限制** | 不適用 |
| **持續性** | 不適用 |

## 維度項目

維度項目包含 `"Identified"` 和 `"Unidentified"`

* **`"Identified"`**：點擊會對應至使用者。
* **`"Unidentified"`**：點擊未對應至使用者，也無法透過任何歸因方法進行對應。
