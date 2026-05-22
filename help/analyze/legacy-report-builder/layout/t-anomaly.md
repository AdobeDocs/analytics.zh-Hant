---
description: 瞭解如何在Report Builder中建立異常偵測請求。
title: 如何設定異常偵測請求
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
feature: Report Builder
role: User, Admin
exl-id: 0a8b1971-8d32-424a-9d41-d7ab2af54d1e
TQID: https://experienceleague.adobe.com/9qyfB3mtj7QKDNLL1PRrQ2-3lzrb19-7gL4rnfxbph4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: c67272a6-888e-425e-9e97-a87304637eed
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 54%

---

# 設定異常偵測請求

{{legacy-arb}}

若要在Report Builder中建立異常偵測請求：

1. 選取趨勢化報表，如&#x200B;**[!UICONTROL 網站度量]**>**[!UICONTROL 流量]**&#x200B;報表。
1. 在[!UICONTROL 「套用顆粒度」]功能表，選取&#x200B;**[!UICONTROL 「日」]**。

   >[!NOTE]
   >
   >[!UICONTROL 「異常偵測」]功能表僅可在選取「日」顆粒度時適用。 前 30 天的資料用於統計資料培訓期間，無論您選取的日期範圍為何。

1. 設定日期範圍後，按&#x200B;**[!UICONTROL 「下一步」]**。

   請求精靈：步驟 2 之 2，新增度量，如&#x200B;**[!UICONTROL 造訪次數]**。

   若要新增度量，請按一下&#x200B;**[!UICONTROL 「無」]**&#x200B;連結。

   ![熒幕擷圖顯示異常偵測，然後插入，再插入上下界限的選項，而且必須是。](assets/anomaly_select.png)

1. 選取&#x200B;**[!UICONTROL 「異常偵測]** > **[!UICONTROL `<selection>`]**」。

   ![熒幕擷圖顯示「請求精靈：步驟2 — 流量報告」。](assets/anomaly_visit.png)

   選取其中一個選項時，系統會建立原始量度的「異常偵測」副本。 例如，對於造訪量度，會將下限造訪量度新增至[!UICONTROL 量度]群組。
1. 按一下&#x200B;**[!UICONTROL 「完成」]**，並選取要輸出成 Excel 的儲存格。

   請參閱[異常偵測](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)，了解定義。
