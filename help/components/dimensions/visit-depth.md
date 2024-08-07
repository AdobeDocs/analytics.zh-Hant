---
title: 造訪深度
description: 報告造訪深度的造訪相關維度。
feature: Dimensions
exl-id: 3e9aca08-2255-46ca-9949-77334ee7120e
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 89%

---

# 造訪深度

「造訪深度」 [維度](overview.md)會報告訪客在整個造訪中檢視的頁面檢視次數。 只有在點擊為頁面檢視，且[「頁面」](page.md)維度與最後一個頁面檢視的維度項目不同時，造訪深度才會增加。這是以造訪為基礎的維度，這表示其中包含整個造訪共同的值。此變數的設定範圍，涵蓋某個造訪結束後的所有點擊。

## 將資料填入此維度中

此維度可直接用於所有實施作業。如果報告套裝包含資料，此維度即會運作。

## 維度項目

維度項目包含 `"Pages per visit"` 字串，及其後代表造訪所含頁數的數字。維度項目為 `"Pages per visit: 1"` 時代表單頁造訪，若維度項目為 `"Pages per visit: 8"`，則代表有 8 次頁面檢視 (以及任意次數的連結追蹤呼叫) 的造訪。

## 與點擊深度比較

如需維度之間的比較，請參閱[點擊深度](hit-depth.md)。
