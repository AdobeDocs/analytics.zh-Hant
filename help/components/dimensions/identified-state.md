---
title: 識別的狀態
description: 裝置圖表判斷旗標的辨識。
translation-type: ht
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: ht
source-wordcount: '120'
ht-degree: 100%

---


# 識別的狀態

「識別的狀態」是[跨裝置分析](../cda/overview.md)虛擬報表套裝的專屬維度。此維度會回報在執行報表時，裝置圖表是否識別 Experience Cloud ID。此維度有助於了解 CDA 彙整或「壓縮」資料的程度。

## 將資料填入此維度中

只需為虛擬報表套裝設定[跨裝置分析](../cda/overview.md)，此維度就可立即運作。

## 維度項目

維度項目包含 `"Identified"` 和 `"Unidentified"`

* **`"Identified"`**：裝置圖表會辨識與點擊連結的 Experience Cloud ID。
* **`"Unidentified"`**：裝置圖表無法辨識 Experience Cloud ID，或是點擊沒有連結 Experience Cloud ID。
