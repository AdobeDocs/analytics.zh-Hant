---
title: 點擊深度
description: 造訪中的點擊次數。
feature: Dimensions
exl-id: 84c27e3f-4228-4455-95bf-0239928337b5
TQID: https://experienceleague.adobe.com/dH1ItdXZTw9vcqvej3VOQDM-J9FFA38f4bq8HTJbKMo
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 262
ht-degree: 94%

---

# 點擊深度

「點選深度」[維度](overview.md)會報告指定的點選在造訪中的深入程度。 此維度十分有助於瞭解訪客在您的網站上執行動作時深入造訪的程度。 點擊深度會計算所有類型的點擊，包括頁面檢視 ([`t()`](/help/implement/vars/functions/t-method.md)) 和連結追蹤點擊 ([`tl()`](/help/implement/vars/functions/tl-method.md))。

## 將資料填入此維度中

此維度可直接用於所有實施作業。 如果報告套裝包含資料，此維度即會運作。

## 維度項目

維度項目包含 `"Hit Depth"` 字串，及其後代表造訪所含點擊數的數字。 維度項目為 `"Hit Depth 1"` 時，代表造訪的第一次點擊，維度項目為 `"Hit Depth 8"` 時，代表造訪的第 8 次點擊。

## 與造訪深度比較

點擊深度會計算所有類型的點擊，包括頁面檢視和連結追蹤點擊。 造訪深度只會隨著頁面檢視點擊而增加，_且_[「頁面」](page.md)維度項目會與上一頁的值不同。 造訪深度也是以造訪為基礎的維度，這表示這是造訪中所有點擊的共同值。 下表列出了範例造訪，並概觀其考量點擊深度 + 造訪深度的方式：

| 頁面順序 | 點擊深度 | 是否計入造訪深度？ | 造訪深度 |
| --- | --- | --- | --- |
| 首頁 | 1 | 是 | 4 |
| 產品頁面 | 2 | 是 | 4 |
| 首頁 | 3 | 是 | 4 |
| 自訂連結點按 | 4 | 否 (自訂連結) | 4 |
| 自訂連結點按 | 5 | 否 (自訂連結) | 4 |
| 產品頁面 | 6 | 是 | 4 |
| 自訂連結點按 | 7 | 否 (自訂連結) | 4 |
| 產品頁面 | 8 | 否 (與上一頁相同) | 4 |
