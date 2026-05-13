---
title: 點擊類型
description: 判斷點擊是前景或背景點擊。
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
TQID: https://experienceleague.adobe.com/6G-XpOMMZGum9LAQzKn0zGdeNRmHFPpmYizqRrbKuUE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2id: c77ba355-6681-41fe-b719-563d3f507fdbid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 164
ht-degree: 84%

---

# 點擊類型

「點選型別」[維度](overview.md)會判斷點選傳送至Adobe資料收集伺服器時，行動應用程式在前景或背景。 此維度僅與包含行動應用程式資料的報表套裝相關。 透過 AppMeasurement 收集的瀏覽器資料一律會將點擊回報為「前景」。

## 將資料填入此維度中

此維度可立即用於 4.13.6 版或更新版本上的所有行動 SDK 實施作業。 如果您不使用行動 SDK，所有點擊會列於「前景」維度項目中。 如果勾選「停用背景點擊數的舊式報告和歸因」，則背景點擊數僅會顯示在[「虛擬報表套裝」](../vrs/vrs-mobile-visit-processing.md)中。

## 維度項目

維度項目包含 `"Foreground"` 和 `"Background"` 未在行動應用程式背景傳送的所有點擊都屬於 `"Foreground"` 維度項目。 行動應用程式在背景時傳送的所有點擊都屬於 `"Background"` 維度項目。
