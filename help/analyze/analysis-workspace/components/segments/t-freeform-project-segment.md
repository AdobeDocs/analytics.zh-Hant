---
description: 在 Analysis Workspace 中使用區段。
title: 區段
uuid: 677f6030-5b3e-4dfa-bb79-9f27f3382fb1
feature: Workspace Basics
role: User, Admin
exl-id: 67112e13-4d0a-4d77-be50-496c3d28779c
source-git-commit: 63f833ffb3578614d7148bfcc6c786d4ddc8a2a8
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 42%

---


# 區段 {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

您可以在工作區中建立不同類型的區段，視其需要的複雜程度、是否應該只套用至此專案等而定。 以下是區段類型的摘要：

| 區段類型 | 建立位置？ | 適用於何處？ | 使用時機 |
| --- | --- | --- | --- |
| 元件清單區段 | 按一下+，接著便會前往[區段產生器](/help/components/segmentation/segmentation-workflow/seg-build.md) | 所有工作區專案 | 對於更複雜的區段，循序區段 |
| 快速區段 | [快速區段產生器](/help/analyze/analysis-workspace/components/segments/quick-segments.md) | 僅限專案，但可儲存並新增至區段清單。 | 可彈性新增/編輯一或多個規則 |
| 臨機區段： |  |  |  |
|  — 臨機工作區專案區段 | [拖放至專案中的區段拖放區域](/help/analyze/analysis-workspace/components/segments/ad-hoc-segments.md) | 僅限專案，但可儲存並新增至區段清單。 | 單一規則區段（無限制） |
|  — 計算量度型區段 | [計算量度產生器](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/metrics-with-segments.html) | 至個別計算量度 | 在量度定義中套用區段 |
|  — 以VRS為基礎的區段 | [虛擬報表套裝產生器](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) | 至個別虛擬報表套裝 | 在VRS定義中套用區段 |

以下是有關在Analysis Workspace中使用區段的影片：

>[!VIDEO](https://video.tv.adobe.com/v/23977/?quality=12)

## 建立區段 {#section_693CFADA668B4542B982446C2B4CF0F5}

您可以在Analysis Workspace中建立不同類型的區段：

* [快速區段](/help/analyze/analysis-workspace/components/segments/quick-segments.md)
* [臨機區段](/help/analyze/analysis-workspace/components/segments/ad-hoc-segments.md)
* 您在「區段產生器」中建立且最終出現在區段程式庫（請參閱下方）的一般元件清單區段

### 建立元件清單區段 {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

「元件」功能表下的區段邊欄會顯示
* 您或您公司建立的區段
* 區段範本，如Adobe圖示所指示：

![](assets/segment_icons.png)

若要建立此類型的區段，有2個選項。 這兩個參數都會帶您前往Adobe Analytics的[區段產生器](/help/components/segmentation/segmentation-workflow/seg-build.md)，您可在此處找到進一步指示。

* 在左側邊欄中，按一下[!UICONTROL Segments]旁的加號(+):

![](assets/create-seg.png)

或

* 前往「[!UICONTROL 元件] > [!UICONTROL 區段]」，然後按一下「[!UICONTROL +新增]」。


### 套用區段的其他方法 {#section_10FF2E309BA84618990EA5B473015894}

>[!VIDEO](https://video.tv.adobe.com/v/30994/?quality=12)

另有數個可套用區段至自由格式專案的方法。

| 動作 | 說明 |
|--- |--- |
| 從選取項目建立區段 | 建立內嵌區段。此區段僅套用至開啟的專案，不會儲存為 Analytics 區段。1. 選取所需的列。2. 以滑鼠右鍵按一下選取項目。3. 按一下&#x200B;*「從選取項目建立區段」*。 |
| 元件 > 新增區段 | 顯示區段產生器。如需分段的詳細資訊，請參閱[區段產生器](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html)。 |
| 「共用 > 共用專案」或「共用 > 監管專案資料」 | 在[「監管與共用」](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6)中，您可以了解套用至專案的區段可如何供收件者使用於共用分析中。 |
| 使用區段作為維度 | 影片：[在 Analysis Workspace 中使用區段作為維度](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/using-segments-as-dimensions-in-analysis-workspace.html?lang=en) |

## 區段 IQ

區段IQ（也稱為區段比較）包含下列功能：

* [區段比較面板：](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)區段 IQ 的核心功能。將兩個區段拖曳至面板中，並透過資料全面的報表，檢視兩種目標對象之間在統計數據上的顯著差異和重疊之處。
* [比較區段的流失：](/help/analyze/analysis-workspace/visualizations/fallout/compare-segments-fallout.md)透過流失率視覺效果，互相比較不同目標對象的流失情況。

## 更多資訊

如需Adobe Analytics中分段的深入討論，請前往[此處](/help/components/segmentation/seg-overview.md)。