---
title: 已識別的狀態
description: 決定拼接識別的旗標。
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
source-git-commit: f75a1f6d9f08f422595c24760796abf0f8332ddb
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 83%

---

# 已識別的狀態

「識別的狀態」[維度](overview.md)是[跨裝置分析](../cda/overview.md)虛擬報表套裝的專屬維度。 它會報告在執行報告時系統是否識別 (拼接) 點擊。此維度有助於了解 CDA 拚接或「壓縮」資料的程度。

## 將資料填入此維度中

只需為虛擬報表套裝設定[跨裝置分析](../cda/overview.md)，此維度就可立即運作。

## 維度項目

維度項目包含 `"Identified"` 和 `"Unidentified"`

* **`"Identified"`**：點擊會對應至使用者。
* **`"Unidentified"`**：點擊未對應至使用者，也無法透過任何歸因方法進行對應。
