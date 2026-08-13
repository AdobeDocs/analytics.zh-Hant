---
title: 找不到頁面 (量度)
description: 包含錯誤的點擊次數。
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
TQID: https://experienceleague.adobe.com/V5jVT8wh71qMrchQmmM6c4EMofHPUEI388TmAf7Zf6M
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 139
ht-degree: 38%

---

# 找不到頁面

*此說明頁面說明「找不到頁面」作為量度時的運作方式。 請參閱[找不到頁面](../dimensions/pages-not-found.md)維度頁面，以取得如何當做維度使用的詳細資訊。*

「找不到頁面」[量度](overview.md)顯示訪客發生錯誤時，維度已設定或持續存在的點選次數。 如果您想要檢視哪些頁面或URL包含錯誤訊息（例如404），此量度就十分實用。 然後，您可以將此資訊傳遞至您的Web開發團隊，由他們判斷錯誤的原因並加以修正。

## 此量度的計算方式

此量度會計入 [`pageType`](/help/implement/vars/page-vars/pagetype.md) 變數等於 `"errorPage"` 值的所有點擊。 此量度等同於[找不到頁面](../dimensions/pages-not-found.md)維度。
