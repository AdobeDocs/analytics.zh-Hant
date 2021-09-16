---
title: 識別的狀態
description: 裝置圖表判斷旗標的辨識。
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
source-git-commit: 1a58c3e87f5918c91b891faa6027f5ad8b6024b9
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 61%

---

# 識別的狀態

「識別的狀態」是[跨裝置分析](../cda/overview.md)虛擬報表套裝的專屬維度。它會報告執行報表時的系統是否識別（匯整）點擊。 此維度有助於了解 CDA 彙整或「壓縮」資料的程度。

## 將資料填入此維度中

只需為虛擬報表套裝設定[跨裝置分析](../cda/overview.md)，此維度就可立即運作。

## 維度項目

維度項目包含 `"Identified"` 和 `"Unidentified"`

* **`"Identified"`**:點擊會對應至人員。
* **`"Unidentified"`**:點擊未對應至人員，且無法透過任何歸因方法對應。
