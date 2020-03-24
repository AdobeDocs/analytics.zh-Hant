---
title: 工作區中有多個報表套裝
description: 了解在有多個報表套裝的工作區中建立專案的方法及原因
translation-type: tm+mt
source-git-commit: 03ab0edc60f4e858acd98f14390d058387af67fa

---


# 工作區中有多個報表套裝

您現在可以在 Analysis Workspace 中建立含有來自多個報表套裝之資料的專案。現在，您可以在面板層級選擇報表套裝，以便針對相同 Workspace 專案內的每個面板，選擇不同的報表套裝。

此功能相當實用。舉例來說，如果您想

* 比較兩個不同地區的資料，而這些資料位於兩個不同的報表套裝時，您可以建立表格和視覺效果，以便並排比較資料。

* 建立量度和視覺效果的控制面板，以便向其他組織提交報告。您現在可以將各種報表套裝的資料提取到同一個專案中。

## 套用報表套裝至所有面板

您可以在任何面板標題上按滑鼠右鍵並選取，一次將報表套裝套用至所有面板 **[!UICONTROL Apply Report Suite to All Panels]**。

![](assets/apply-rs-all-panels.png)

## 使用中面板

我們將透過此功能，介紹「使用中面板」與「非使用中面板」的概念。您可以通過周圍的淺藍色邊框來識別活動面板。 只要按一下面板內部，該面板就會變成作用中面板。

>[!IMPORTANT]
>您可以拖放至與作用中面板位於相同報表套裝中的任何面板。 拖曳至相同報表套裝的非作用中面板後，面板就會變成作用中。

| 任務 | 使用中面板 | 非使用中面板 |
|---|---|---|
| 變更報表套裝 | 有 | 無 |
| 拖放元件 | 有 | 是，適用於與作用中面板位於相同報表套裝的任何面板。 |
| 拖放視覺效果 | 有 | 是，適用於與作用中面板位於相同報表套裝的任何面板。 |

## 使用多個報表套裝

![](assets/mrs-ui.png)

1. 在工作區中建立具有 2 個或更多面板的新專案。

1. 將元件 (量度、維度、區段、日期範圍) 拖放至面板中。確認面板擁有專屬於其報表套裝的資料和視覺效果。


   >[!NOTE]
   >有時，在載入專案（或切換至報表套裝）時會顯示橫幅，其中並非專案中包含的所有元件都包含在報表套裝中。 畫面會列出缺少的元件。請依照[這些指示](/help/admin/admin-console/permissions/product-profile.md)，將權限設為所需的量度/維度。

   ![](assets/incompat-rs.png)

   因應這種不相容的狀況有 3 種方法：
   * 啟用必要的維度／量度
   * 變更報表套裝。
   * 在缺少部分元件的情況下繼續操作。這會導致這些元件沒有任何資料，和/或視覺效果空白。

1. 將面板變更為其他報表套裝，並注意元件標籤 (目前使用中的報表套裝) 和列出的元件會如何根據新的報表套裝來更新。

1. Use a keyboard shortcut (`shift` while dragging) to turn an inactive panel to an active panel.

1. (選用) 您也可以前往其他 Analytics 元件產生器，並確定其是否顯示報表套裝標籤，指出

   * 建立區段的位置：[區段產生器](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-build.html)。
   * 建立計算量度的位置：[計算量度產生器](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html)。
   * 建立警報的位置：[警報產生器](https://docs.adobe.com/content/help/en/analytics/components/alerts/alert-builder.html)。