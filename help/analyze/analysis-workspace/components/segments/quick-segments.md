---
description: 在Analysis Workspace中使用快速區段。
title: 快速區段
feature: Workspace Basics
role: User, Admin
source-git-commit: 9622131ebd4a856cb7756e6844d7d7979029e70e
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 5%

---


# 快速區段

您可以在專案內建立快速區段，以略過完整[區段產生器](/help/components/segmentation/segmentation-workflow/seg-build.md)的複雜度。 如需快速區段可以執行哪些動作與完整元件層級區段的比較，請前往[此處](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md)。

>[!IMPORTANT]
> 快速區段目前正在進行有限測試，目前尚未正式提供。

## 建立快速區段

1. 在自由表格中，按一下面板標題中的「篩選+」圖示：

   ![](assets/quick-seg1.png)

   請注意:

   - 只有一個區段容器可讓您在區段中加入維度/量度/日期範圍（或將其排除在區段之外）。
   - 您可以將容器設為「點擊」、「造訪」或「訪客」層級。 預設為「點擊」。

1. 以下列三種方式之一新增維度/量度/日期範圍：

   - 開始輸入後，快速區段產生器就會自動尋找適當的元件。
   - 使用下拉式清單來尋找元件。
   - 從左側邊欄拖放元件。

1. 指定第一個規則，例如`Page equals workspace`。 區段定義中最多可以有三個規則。 只需按一下「+」符號即可新增其他規則。 您可以將「AND」或「OR」限定符新增至規則，但無法在單一區段定義中混合「AND」和「OR」。

   以下是結合維度和量度的區段範例：

   ![](assets/quick-seg2.png)

1. 按一下「**[!UICONTROL 套用]**」，將此區段套用至面板。
區段會顯示在頂端。 請注意其灰色側欄，而非左側元件層級區段的藍色長條。

   ![](assets/quick-seg3.png)

## 將快速區段設為公用

您可以遵循下列步驟將這些區段設為公用 (全域)：

1. 將滑鼠指標暫留在快速區段上，然後按一下「i」圖示。
1. 按一下「**[!UICONTROL 開啟產生器]**」。
這會在「區段產生器」中開啟區段。
   >[!NOTE]
   >在「區段產生器」中套用或儲存區段後，您就無法在「快速區段產生器」中編輯該區段。
1. 按一下「**[!UICONTROL 確定]**」。
1. 在「區段產生器」中，按一下「**[!UICONTROL 套用]**」。
1. 返回工作區，注意區段現在如何有藍色側欄，表示它是元件程式庫的一部分。

   ![](assets/quick-seg4.png)

