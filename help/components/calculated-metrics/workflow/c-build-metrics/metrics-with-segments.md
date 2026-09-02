---
description: 瞭解如何對個別量度進行分段，以便讓您在同一視覺效果中進行量度比較。
title: 區段量度
feature: Calculated Metrics
exl-id: 1e7e048b-9d90-49aa-adcc-15876c864e04
TQID: https://experienceleague.adobe.com/t1HtjinGP02YSBQk1Z95t6wIQ0OhuFb14GKfpd8Y9Eg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 463
ht-degree: 1%

---

# 區段量度

在[計算量度產生器](cm-build-metrics.md#definition-builder)中，您可以在量度定義中套用區段。 如果您想要在分析中將量度用於資料的子集，套用區段會很有幫助。

>[!NOTE]
>
>透過[區段產生器](/help/components/segmentation/segmentation-workflow/seg-build.md)更新區段定義。 如果您變更區段，該區段會在任何使用它的地方自動更新，包括如果該區段屬於計算量度定義的一部分。
>

您想要比較和您的品牌互動的德國人員與德國以外人員的量度。 因此，您可以回答以下問題：

1. 有多少德國和國際人士造訪您最受歡迎的[頁面](#popular-pages)。
1. 本月[總計](#totals)有多少德國和國際人士與您的品牌進行線上互動。
1. 造訪過您熱門頁面的德國人和海外人士的[百分比](#percentages)為何？

請參閱以下各節，說明區段量度如何協助您回答這些問題。 在適當的情況下，會參考更詳細的檔案。

## 受歡迎頁面

1. [從名為`Germany`的Workspace專案建立計算量度](../cm-workflow.md)。
1. 從[計算量度產生器](cm-build-metrics.md)中，[使用「國家/地區」欄位，建立標題為`Germany`的區段](/help/components/segmentation/segmentation-workflow/seg-build.md)。

   >[!TIP]
   >
   >在計算量度產生器中，您可以使用「元件」面板直接建立區段。
   >   

   您的區段可能如下所示。

   ![德國區段](assets/segment-germany.png)

1. 返回計算量度產生器，使用區段更新計算量度。

   ![計算量度Germany](assets/germany-visits.png)

針對計算量度的國際版本重複上述步驟。

1. 從您的Workspace專案中建立標題為`Non Germany visits`的計算量度。
1. 在計算量度產生器中，建立名為`Not Germany`的區段，此區段會使用您CRM資料中的CRM國家/地區欄位來判斷人員的來源。

   您的區段看起來應該像這樣。

   ![德國區段](assets/segment-not-germany.png)

1. 返回計算量度產生器，使用區段更新計算量度。

   ![計算量度Germany](assets/non-germany-visits.png)


1. 在Analysis Workspace中建立專案，在其中檢視德國和非德國訪客造訪的頁面。

   ![Workspace自由格式表格視覺效果顯示德國人員與國際人員](assets/workspace-german-vs-international.png)


## 總計

1. 根據「總量」建立兩個新計算量度。 開啟先前建立的每個區段、重新命名區段、將&#x200B;**[!UICONTROL 人員]**&#x200B;的&#x200B;**[!UICONTROL 量度型別]**&#x200B;設定為&#x200B;**[!UICONTROL 總計]**，並使用&#x200B;**[!UICONTROL 另存新檔]**&#x200B;以新名稱儲存區段。 例如：

   德國的![總計量度](assets/calculated-metric-germany-total.png)

1. 在您的Workspace專案中新增自由表格視覺效果，顯示今年的總頁面數。

   ![Workspace自由格式表格視覺效果顯示德文人員與國際人員總數](assets/workspace-german-vs-international-totals.png)


## 百分比

1. 建立兩個新計算量度，用於根據您先前建立的計算量度計算百分比。

   ![Workspace自由格式表格視覺效果顯示德文人員與國際總人員百分比](assets/calculated-metric-germany-total-percentage.png)


1. 更新您的Workspace專案。

   ![Workspace自由格式表格視覺效果顯示德文人員與國際人員總數](assets/workspace-german-vs-international-totals-percentage.png)

