---
title: 已識別狀態
description: 由設備圖確定識別的標誌。
translation-type: tm+mt
source-git-commit: 60fe85adaebee8ca390e59727dda949c12c1ee26
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 4%

---


# 已識別狀態

「已識別狀態」維度是跨裝置 [Analytics虛擬報表套裝](../cda/overview.md) 的專屬維度。 它會報告在執行報表時，裝置圖表是否識別Experience Cloud ID。 此維度有助於瞭解CDA銜接或「壓縮」資料的程度。

## 將資料填入此維度中

只要您已為虛擬 [報表套裝設定跨裝置Analytics](../cda/overview.md) ，此維度就可立即運作。

## 維度項目

維度項目包 `"Identified"` 括和 `"Unidentified"`。

* **`"Identified"`**:裝置圖表會辨識系結至點擊的Experience Cloud ID。
* **`"Unidentified"`**:裝置圖表無法辨識Experience Cloud ID，或點擊沒有Experience Cloud ID。
