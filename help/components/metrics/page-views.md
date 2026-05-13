---
title: 頁面檢視次數
description: 維度項目的次數是設定或保存在 Adobe Analytics 中。
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
TQID: https://experienceleague.adobe.com/ZJOoxc3imuMfVTa7caV5eQ6-XJh0amCRq65ByuANFq0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 169
ht-degree: 100%

---

# 頁面檢視次數

**[!UICONTROL 頁面檢視次數]**[量度](overview.md)顯示特定維度項目在頁面上設定或持續存在的次數。 這是報表中最常用且最基本的量度之一。

## 此量度的計算方式

此量度會計入報表套裝中的所有頁面檢視追蹤呼叫 ([`t()`](/help/implement/vars/functions/t-method.md))。 維度包含維度項目被設定或持續存在的點擊次數。 其中不包括連結追蹤呼叫 ([`tl()`](/help/implement/vars/functions/tl-method.md)) 或來自[資料來源](/help/import/data-sources/overview.md)的資料。

## 與類似量度比較

* **頁面檢視次數與[造訪次數](visits.md)**：頁面檢視次數會計算頁面被檢視的次數。 造訪次數會計算瀏覽者使用工作階段的數量。 一次瀏覽包含一或多次頁面檢視。
* **頁面檢視次數與[頁面事件](page-events.md)**：頁面檢視次數會計算頁面檢視追蹤呼叫 (`t()`) 的數量，並排除連結追蹤呼叫 (`tl()`)。 頁面事件次數正好反相；這類次數會計算連結追蹤呼叫的數量，並排除頁面檢視追蹤呼叫。
