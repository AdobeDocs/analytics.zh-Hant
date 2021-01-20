---
title: 已識別狀態
description: 由設備圖確定識別的標誌。
translation-type: tm+mt
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 9%

---


# 已識別狀態

「已識別狀態」維度是[跨裝置分析](../cda/overview.md)虛擬報表套裝的專屬維度。 它會報告在執行報表時，裝置圖表是否識別Experience Cloud ID。 此維度有助於瞭解CDA銜接或「壓縮」資料的程度。

## 將資料填入此維度中

只要您已為虛擬報表套裝設定[跨裝置分析](../cda/overview.md)，此維度就可立即運作。

## 維度項目

維度項目包含 `"Identified"` 和 `"Unidentified"`

* **`"Identified"`**:裝置圖表會辨識系結至點擊的Experience Cloud ID。
* **`"Unidentified"`**:裝置圖表無法辨識Experience Cloud ID，或點擊沒有Experience Cloud ID。
