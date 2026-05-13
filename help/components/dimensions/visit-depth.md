---
title: 造訪深度
description: 報告造訪深度的造訪相關維度。
feature: Dimensions
exl-id: 3e9aca08-2255-46ca-9949-77334ee7120e
TQID: https://experienceleague.adobe.com/mT5dQzR6edNpvU6Fbf9LlLwQuxW6RA-ZCZJDaIFkyAw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705cid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 170
ht-degree: 90%

---

# 造訪深度

「造訪深度」 [維度](overview.md)會報告訪客在整個造訪中檢視的頁面檢視次數。 只有在點擊為頁面檢視，且[「頁面」](page.md)維度與最後一個頁面檢視的維度項目不同時，造訪深度才會增加。 這是以造訪為基礎的維度，這表示其中包含整個造訪共同的值。 此變數的設定範圍，涵蓋某個造訪結束後的所有點擊。

## 將資料填入此維度中

此維度可直接用於所有實施作業。 如果報告套裝包含資料，此維度即會運作。

## 維度項目

維度項目包含 `"Pages per visit"` 字串，及其後代表造訪所含頁數的數字。 維度項目為 `"Pages per visit: 1"` 時代表單頁造訪，若維度項目為 `"Pages per visit: 8"`，則代表有 8 次頁面檢視 (以及任意次數的連結追蹤呼叫) 的造訪。

## 與點擊深度比較

如需維度之間的比較，請參閱[點擊深度](hit-depth.md)。
