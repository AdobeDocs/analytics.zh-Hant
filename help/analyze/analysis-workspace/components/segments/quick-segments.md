---
description: 在Analysis Workspace中使用快速區段。
title: 快速區段
feature: Workspace Basics
role: User, Admin
source-git-commit: f3185f1ee341348fb7bdbaab8b68d421e7c79076
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---


# 快速區段

您可以在專案內建立快速區段，以略過完整[區段產生器](/help/components/segmentation/segmentation-workflow/seg-build.md)的複雜度。 如需快速區段可以執行哪些動作與完整元件清單區段的比較，請前往[此處](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md)。

>[!IMPORTANT]
> 快速區段目前正在進行有限測試，目前尚未正式提供。

## 建立快速區段

1. 在自由表格中，按一下面板標題中的「篩選+」圖示：

   ![](assets/quick-seg1.png)

   請注意:

   - 只有一個區段容器可讓您在區段中加入維度/量度/日期範圍（或將其排除在區段之外）。
   - 您可以將容器設為「點擊」、「造訪」或「訪客」層級。 預設為「點擊」。

1. 以下列三種方式之一新增維度/量度/日期範圍：

   - 開始輸入，[!UICONTROL 快速區段產生器]會自動尋找適當的元件。
   - 使用下拉式清單來尋找元件。
   - 從左側邊欄拖放元件。

1. 指定第一個規則，例如`Page equals workspace`。 一個區段定義中最多可以有三個規則。 只需按一下「+」符號即可新增其他規則。 您可以將「AND」或「OR」限定符新增至規則，但無法在單一區段定義中混合「AND」和「OR」。

   以下是結合維度和量度的區段範例：

   ![](assets/quick-seg2.png)

1. 按一下「**[!UICONTROL 套用]**」，將此區段套用至面板。
區段會顯示在頂端。 請注意其灰色側欄，而非左側區段庫中元件層級區段的藍色側欄。

   ![](assets/quick-seg3.png)

## 編輯快速區段

1. 將滑鼠指標暫留在快速區段上，並選取鉛筆圖示。
1. 編輯區段定義或區段名稱。

## 儲存快速區段

您可以依照下列步驟選擇儲存快速區段。

>[!IMPORTANT]
>儲存或套用區段後，您就無法在「快速區段產生器」中編輯區段，只能在一般的區段產生器中編輯。

1. 將滑鼠指標暫留在快速區段上，並選取資訊(「i」)圖示。
1. 選擇&#x200B;**[!UICONTROL 保存段]**

   ![](assets/save-quick-seg.png)

1. 保留名稱原樣，或重新命名區段。

   返回「工作區」，注意區段現在有藍色側欄的方式。 這表示您無法再在快速區段產生器中編輯/開啟區段。 儲存後就會成為元件清單的一部分。

   ![](assets/quick-seg4.png)

套用區段後，您可以選取將其新增至區段元件清單，並供所有專案使用。

1. 將滑鼠指標暫留在儲存的區段上，並選取鉛筆圖示。

1. 在「區段產生器」頂端，注意此對話方塊：

   ![](assets/project-only.png)

1. 選取&#x200B;**[!UICONTROL 讓此區段可供所有專案使用並新增至元件清單旁的核取方塊。]**
1. 按一下「**[!UICONTROL 儲存]**」。
1. 區段現在會顯示在您所有專案的區段元件清單中。
1. 您也可以[與組織中的其他人員共用區段](/help/components/segmentation/segmentation-workflow/t-seg-share.md)。

## 什麼是僅限專案的區段？

僅限專案的區段是快速區段或臨機工作區專案區段。 在區段產生器中編輯/開啟這些區段時，將會顯示僅限專案方塊。 如果他們在產生器中套用快速區段，但未勾選「可用」方塊，則它仍是僅限專案的區段，但無法在QS產生器中開啟它。 如果他們勾選方塊並儲存，現在就會是元件清單區段。