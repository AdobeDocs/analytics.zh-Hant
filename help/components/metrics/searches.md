---
title: 搜尋
description: 點擊符合外部搜尋條件的次數。
feature: Metrics
exl-id: b84c895d-e678-47a1-9e41-500970e0a80c
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 88%

---

# 搜尋

「搜尋」[量度](overview.md)會顯示符合Adobe外部搜尋偵測的點選數。 如果您想要查看非搜尋維度項目，並了解它們對搜尋引擎流量的貢獻，此量度就十分實用。

## 此量度的計算方式

此量度會計算符合 Adobe 外部搜尋偵測的點擊次數。它必須符合以下兩個條件：

* 點擊的反向連結值是 Adobe 認可的搜尋網域
* 點擊的反向連結 URL 包含關鍵字查詢字串參數。由於現今的隱私權實務趨於嚴謹，此查詢字串值通常為空白。Adobe 會將空白的關鍵字查詢字串辨識為搜尋偵測的一部分。
