---
title: 登入點
description: 造訪中第一個值的例項。
feature: Metrics
exl-id: f5d359ce-e6ac-4f80-a30b-ff78cc5fc8dc
TQID: https://experienceleague.adobe.com/H3LE0wm2uDL3-pILbvOXvccAJQdo5o9X3uHJ4xZe7UU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 192
ht-degree: 89%

---

# 登入點

*此說明頁面說明登入作為量度時的運作方式。 若要瞭解登入作為維度時的運作方式，請參閱[登入維度](../dimensions/entry-dimensions.md)。*

「登入點」[量度](overview.md)會顯示指定的維度專案在造訪中被擷取為第一個值的次數。 如果您想要進一步瞭解訪客在您網站上的第一印象，此量度將有所幫助。 查看維度的第一個值，有助於您瞭解新訪客所獲得的體驗，並加以最佳化。

## 此量度的計算方式

對於指定的維度，將在造訪中看到的第一個維度項目記錄為登入。 在每次造訪中，每個維度只有一個登入。 如果最初未設定維度，則登入不一定是造訪的首次點擊。 這是以造訪為基礎的量度；一旦繫結至維度項目，就會持續存在於剩餘的造訪期間。

>[!TIP]
>
>如果您對不一定設定於每次造訪中的維度檢視此量度，您可以在 Analysis Workspace 中隱藏「未指定」維度項目。 按一下篩選器圖示，然後取消勾選[!UICONTROL 「包含未指定項目 (無)」]。
