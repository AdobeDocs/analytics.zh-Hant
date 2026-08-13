---
title: 已識別的狀態
description: 決定拼接識別的旗標。
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
TQID: https://experienceleague.adobe.com/JUBtgXBDboIgX0xbvuflF5q-oEwqHx4vKvJd0Y5XMLY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 111
ht-degree: 82%

---

# 已識別的狀態

「識別的狀態」[維度](overview.md)是[跨裝置分析](../cda/overview.md)虛擬報表套裝的專屬維度。 它會報告在執行報告時系統是否識別 (拼接) 點擊。 此維度有助於了解 CDA 拚接或「壓縮」資料的程度。

## 將資料填入此維度中

只需為虛擬報表套裝設定[跨裝置分析](../cda/overview.md)，此維度就可立即運作。

## 維度項目

維度項目包含 `"Identified"` 和 `"Unidentified"`

* **`"Identified"`**：點擊會對應至使用者。
* **`"Unidentified"`**：點擊未對應至使用者，也無法透過任何歸因方法進行對應。
