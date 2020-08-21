---
title: 退出點
description: 造訪中最後一個值的例項。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 68%

---


# 退出點

*此說明頁面說明退出作為量度時的運作方式。若要瞭解退出作為維度時的運作方式，請參閱[退出維度](../dimensions/exit-dimensions.md)。*

「退出點」量度顯示指定維度項目在瀏覽中被擷取為最後一個值的次數。 如果您想要進一步瞭解訪客在離開您的網站前最後看到的內容，此量度將有所幫助。查看維度的最後一個值，有助於您瞭解訪客在離開前所獲得的體驗，並加以最佳化。

## 此量度的計算方式

After a [visit](visits.md) concludes, record the most recent dimension item as an exit. 在每次造訪中，每個維度只有一個退出。如果維度設定於先前的點擊中，則退出不一定是造訪的最後一次點擊。這是以造訪為基礎的量度，會追溯套用至造訪中的所有點擊。

>[!TIP]
>
>如果您針對並非每次瀏覽都設定的維度檢視此量度，則可以在分析工作區中隱藏「未指定」維度項目。 按一下篩選器圖示，然後取消勾選[!UICONTROL 「包含未指定項目 (無)」]。
