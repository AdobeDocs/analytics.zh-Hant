---
description: 在 Analysis Workspace 中使用區段。
title: 區段
uuid: 677f6030-5b3e-4dfa-bb79-9f27f3382fb1
feature: Workspace Basics
role: User, Admin
exl-id: 67112e13-4d0a-4d77-be50-496c3d28779c
source-git-commit: 86766c4452a571a7c7b36ad6693a1a1e0bc2deea
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 98%

---


# 區段 {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

您可以在工作區中建立不同類型的區段，實際類型將依據這些區段需要的複雜程度、是否應僅套用於此專案等因素而定。以下是區段類型的摘要：

| 區段類型 | 在哪裡建立？ | 適用於何處？ | 何時使用 |
| --- | --- | --- | --- |
| 元件清單區段 | 按一下「+」(加號)，系統即會將您帶至「[區段生產器](/help/components/segmentation/segmentation-workflow/seg-build.md)」 | 您所有的工作區專案 | 適用於較複雜的區段、循序區段 |
| 快速區段 | [快速區段產生器](/help/analyze/analysis-workspace/components/segments/quick-segments.md) | 僅限專案，但可以儲存並新增至您的分段清單中。 | 新增/編輯一個或多個規則的靈活性 |
| 臨時區段： |  |  |  |
| - 臨時工作區專案區段 | [拖放至專案的區段托放區中](/help/analyze/analysis-workspace/components/segments/ad-hoc-segments.md) | 僅限專案，但可以儲存並新增至您的分段清單中。 | 若為單一規則區段 |
| - 以計算量度為基礎的區段 | [計算量度產生器](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/metrics-with-segments.html?lang=zh-Hant) | 至個別計算量度 | 在您的量度定義中套用區段 |
| - 以 VRS 為基礎的區段 | [虛擬報表套裝產生器](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html?lang=zh-Hant) | 至個別虛擬報表套裝 | 在您的 VRS 定義中套用區段 |

## 影片

在Analysis Workspace中使用區段：

>[!VIDEO](https://video.tv.adobe.com/v/23977/?quality=12)

尋找和建立區段:

>[!VIDEO](https://video.tv.adobe.com/v/334092/?quality=12)

區段中的滾動日期範圍：

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## 建立區段 {#section_693CFADA668B4542B982446C2B4CF0F5}

您可以在 Analysis Workspace 中建立不同類型的區段：

* [快速區段](/help/analyze/analysis-workspace/components/segments/quick-segments.md)
* [臨時區段](/help/analyze/analysis-workspace/components/segments/ad-hoc-segments.md)
* 您在「區段產生器」中建立且最後出現在區段資料庫中的常規元件清單區段 (見下文)

### 建立元件清單區段 {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

元件功能表下的區段側邊欄會顯示
* 您或您的公司建立的區段
* 區段範本，由 Adobe 圖示表示：

![](assets/segment_icons.png)

若要建立這種類型的區段，您有 2 種選項。兩者都會將您帶至 Adobe Analytics 中的[區段產生器](/help/components/segmentation/segmentation-workflow/seg-build.md)，您可在此找到進一步說明。

* 在左側邊欄中，請按一下[!UICONTROL 區段]旁的加號 (+)：

![](assets/create-seg.png)

或

* 請前往「[!UICONTROL 元件]>[!UICONTROL 區段]」，然後按一下「[!UICONTROL + 新增]」。


### 套用區段的其他方法 {#section_10FF2E309BA84618990EA5B473015894}

>[!VIDEO](https://video.tv.adobe.com/v/30994/?quality=12)

另有數個可套用區段至自由格式專案的方法。

| 動作 | 說明 |
|--- |--- |
| 從選取項目建立區段 | 建立內嵌區段。此區段僅套用至開啟的專案，不會儲存為 Analytics 區段。1. 選取所需的列。2. 以滑鼠右鍵按一下選取項目。3. 按一下&#x200B;*「從選取項目建立區段」*。 |
| 元件 > 新增區段 | 顯示區段產生器。如需分段的詳細資訊，請參閱[區段產生器](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=zh-Hant)。 |
| 「共用 > 共用專案」或「共用 > 監管專案資料」 | 在[「監管與共用」](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=zh-Hant#concept_4A9726927E7C44AFA260E2BB2721AFC6)中，您可以了解套用至專案的區段可如何供收件者使用於共用分析中。 |
| 使用區段作為維度 | 影片：[在 Analysis Workspace 中使用區段作為維度](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/using-segments-as-dimensions-in-analysis-workspace.html?lang=zh-Hant) |

## 區段 IQ

區段 IQ (也稱為區段比較) 包括以下功能：

* [區段比較面板：](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)區段 IQ 的核心功能。將兩個區段拖曳至面板中，並透過資料全面的報表，檢視兩種目標對象之間在統計數據上的顯著差異和重疊之處。
* [比較區段的流失：](/help/analyze/analysis-workspace/visualizations/fallout/compare-segments-fallout.md)透過流失率視覺效果，互相比較不同目標對象的流失情況。

## 更多資訊

如需有關 Adobe Analytics 中的區段的深入討論，請前往[這裡](/help/components/segmentation/seg-overview.md)。