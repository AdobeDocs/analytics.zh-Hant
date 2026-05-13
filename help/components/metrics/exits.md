---
title: 退出點
description: 造訪中最後一個值的例項。
feature: Metrics
exl-id: 0997ed1f-29b0-403d-9ed2-644a5ff19aef
TQID: https://experienceleague.adobe.com/KTpLeq4YjWgaFR-xcq1PBENAO5mb-wV-71BODlRGGlM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 88%

---

# 退出點

*此說明頁面說明退出作為量度時的運作方式。 若要瞭解退出作為維度時的運作方式，請參閱[退出維度](../dimensions/exit-dimensions.md)。*

「退出」[量度](overview.md)顯示指定的維度專案在造訪中被擷取為最後一個值的次數。 如果您想要進一步瞭解訪客在離開您的網站前最後看到的內容，此量度將有所幫助。 查看維度的最後一個值，有助於您瞭解訪客在離開前所獲得的體驗，並加以最佳化。

## 此量度的計算方式

在[造訪](visits.md)結束後，請將最近的維度項目記錄為退出。 在每次造訪中，每個維度只有一個退出。 如果維度設定於先前的點擊中，則退出不一定是造訪的最後一次點擊。 這是以造訪為基礎的量度，會追溯套用至造訪中的所有點擊。

>[!TIP]
>
>如果您對不一定設定於每次造訪中的維度檢視此量度，您可以在 Analysis Workspace 中隱藏「未指定」維度項目。 按一下篩選器圖示，然後取消勾選[!UICONTROL 「包含未指定項目 (無)」]。
