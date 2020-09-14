---
description: '對個別量度分段可讓您在同一份報表中比較量度。 '
title: 區段量度
uuid: 88f9829b-76e4-4598-9494-084a91602bc1
translation-type: tm+mt
source-git-commit: 234a2eadfe02322daa886d2edbea042f8ad99e1e
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 59%

---


# 區段量度

在計算量度產生器中，您可以在量度定義中套用區段。 如果您想要衍生要在分析中使用的新量度，這將很有幫助。 請記住，區段定義可透過區段產生器更新。 如果進行變更，區段會隨處自動更新，包括屬於計算量度定義的一部分。

![](assets/german-visitors.png)

## 建立分段量度 {#create}

假設您想要比較「德國訪客」區段與「國際訪客」區段的不同方面。 您可以建立能提供下列分析項目的量度：

* 這兩個群組的內容瀏覽行為相較之下的結果為何？(另一個範例：這兩個區段的轉換率相較之下的結果為何？)
* 相較於國際訪客，以訪客總數的百分比表示，有多少德國訪客瀏覽了特定頁面？
* 就這兩個不同區段所存取的內容來說，最大差異為何？

1. 如果您沒有可比較的區段，請直接在計算量度產生器中建立一個臨機區段，稱為「德國訪客」，其中「國家」等於「德國」。 直接將「國家/地區」維度拖放到「定義」畫布中，然後選取「德國」作為值即可：

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >您也可以在[區段產生器](/help/components/segmentation/segmentation-workflow/seg-build.md)中進行此操作。但我們已藉由在計算量度產生器中提供維度簡化了工作流程。&quot;Adhoc&quot; means that the segment is not visible in the **[!UICONTROL Segments]** list in the left rail. 但您可以將游標停留在該區段旁的「i」圖示上，並按一下&#x200B;**[!UICONTROL 「設為公開」]**&#x200B;以公開該區段。

1. 如果您沒有可供比較的區段，請先建立一個名為「國際訪客」的區段，其中「國家/地區」不等於「德國」。
1. 將「德國」區段拖曳至「定義」畫布並將「獨特訪客」量度拖曳至其中，藉此建立並儲存名為「德國訪客」的量度：

   ![](assets/german-visitors.png)

1. 重複步驟 3，使用「國際訪客」區段和「獨特訪客」量度來建立「國際訪客」量度。
1. 在 Analysis Workspace 中，將&#x200B;**[!UICONTROL 「頁面]**&#x200B;維度」拖曳至「自由表格」中，並將 2 個相鄰的新計算量度拖曳到最上方：

   ![](assets/workspace-pages.png)

## 總量度的百分比 {#percent-total}

您可以進一步將區段與總人口進行比較，以進一步瞭解上述範例。 若要這麼做，請建立兩個新度量：「德國訪客總數%」和「國際訪客總數%」:

1. 將德國 (或國際) 訪客區段拖曳至畫布中。
1. 將另一個德國 (或國際) 訪客區段拖曳至下方。但這次按一下其設定 (齒輪) 圖示，選取量度類型「總計」。格式應為「百分比」。運算元應為「除以」。結果會產生此量度定義：

   ![](assets/cm_metric_total.png)

1. 將此量度套用至專案：

   ![](assets/cm_percent_total.png)

