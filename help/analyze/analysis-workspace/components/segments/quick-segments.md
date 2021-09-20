---
description: 在Analysis Workspace中使用快速區段。
title: 快速區段
feature: Workspace Basics
role: User, Admin
source-git-commit: 8cd5d5ec1525e29779a13330dfeaeae120dfdd56
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

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

