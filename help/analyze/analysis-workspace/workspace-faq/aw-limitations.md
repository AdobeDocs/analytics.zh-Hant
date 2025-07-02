---
description: 了解 Adobe Analysis Workspace 及其相關元件的已知限制
title: Analysis Workspace的已知限制
feature: Workspace Basics
role: User, Admin
exl-id: 520e970b-1387-4f70-985b-bfe397f4a21b
source-git-commit: d37fa0aff0b1bbe196b943bc26e86b1e79936184
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 98%

---

# Analysis Workspace 的已知限制

以下為 Analysis Workspace 及其相關元件的已知限制清單：

## 表格

* 日期範圍或量度在表格中設為列時，無法新增日期比較欄。
* 區段在表格中設為列時，「從選取項目建立量度」功能會遭停用。此外，「從選取項目建立量度」不可套用至對齊日期的欄。
* 用於劃分列的條件式格式無法使用自訂範圍。
* 採用「加總列中的值來計算總計」設定時 (通常與「靜態」列項目搭配使用)，表格總列數無法跟隨趨勢產生變化。

## 視覺效果

* 善用[!UICONTROL 「流失」]、[!UICONTROL 「流量」]、[!UICONTROL 「同類群組」]、[!UICONTROL 「直方圖」]等區段的視覺效果，無法將計算量度設為輸入項目。
* [!UICONTROL 流量]：「登入/退出」維度 (例如[!UICONTROL 「登入頁面」]) 無法用於「流量」。
* [!UICONTROL 同類群組]：非整數無法當作同類群組條件使用。

## 區段

* [!UICONTROL 「事件」]、[!UICONTROL 「人員」]等特定量度和維度無法進行劃分。
* 在[面板放置區](/help/analyze/analysis-workspace/c-panels/panels.md)中建立的臨時區段是一種快速區段。除非設定為公開，否則它們不會顯示在 Workspace 或區段元件管理器的左側面板中。如需詳細資訊，請參閱[快速區段](/help/components/segmentation/segmentation-workflow/seg-quick.md)。

## 計算的量度

* 特定視覺化呈現中無法使用計算量度。請參閱[視覺化呈現](#visualizations)。
* 「[!UICONTROL 歸因]」面板中無法使用計算量度，因為計算量度本身可能包含個別的歸因模型。
* 如果從工作區中建立計算量度，而非經由「[!UICONTROL 元件 > 區段]」建立，則某些元件和運算子會無法使用。例如 [!UICONTROL IP 位址]。

## 日期範圍

* 自訂日期範圍不支援「[!UICONTROL 去年的今天]」、「[!UICONTROL 上個月的今天]」等。


## 報告設定

* [!UICONTROL 「報表設定」]頁面上的某些設定並不適用。Analysis Workspace 僅會使用以下幾種位於底部的[!UICONTROL 「語言/貨幣/編碼」]設定：[!UICONTROL 「千位分隔符號」]、[!UICONTROL 「排程報表編碼」]和[!UICONTROL 「CSV 分隔符號字元」]。



<!--
# Known limitations in Analysis Workspace 

Here is a list of known limitations in Analysis Workspace and its related components:

## Tables

* Date comparison columns cannot be added when either date ranges or metrics are used as rows of a table.
* Create metric from selection is disabled when segments are used as rows of a table. Additionally, Create metric from selection should not be applied to date-aligned columns.
* Conditional formatting for breakdown rows cannot use custom ranges.
* Table total rows cannot be trended when Calculate totals by summing the row values setting is applied (typically used with Static row items).
* [!UICONTROL Contribution Analysis] can be run at the [!UICONTROL daily] granularity _only_. It cannot be run against [!UICONTROL hourly], [!UICONTROL weekly], etc., data.

## Visualizations

* Visualizations that leverage segmentation, such as [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort], and [!UICONTROL Histogram], cannot accept calculated metrics as inputs.
* [!UICONTROL Flow]: Entry/Exit dimensions, e.g. [!UICONTROL Entry page], cannot be used in Flow.
* [!UICONTROL Cohort]: Non-integers cannot be used as Cohort criteria.

## Panels

* Segment Comparison: The [!UICONTROL Everyone Else] segment does not get created if a segment template is used in the initial drop zone.

## Components > Segments

* Certain metrics and dimensions are not segmentable, such as [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], etc.
* Adhoc segments created in the [panel dropzone](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=zh-Hant) are a type of quick filter. They do not appear in the left rail of Workspace or the Segment component manager unless they are made public. For more information, see [Quick segments](/help/analyze/analysis-workspace/components/segments/quick-segments.md).

## Components > Calculated Metrics

* Calculated metrics cannot be used in certain visualizations. See 'Visualizations' above.
* Calculated metrics cannot be used in the [!UICONTROL Attribution] panel, since calculated metrics themselves can include separate attribution models.
* Certain components and operators are unavailable if a calculated metric is created from Workspace (as opposed to being created from [!UICONTROL Components > Segments]). For example, [!UICONTROL IP Address].

## Components > Date Ranges

* Custom date ranges do not support [!UICONTROL This day last year], [!UICONTROL This day last month], etc.

## Components > Virtual Reports Suites

* When report time processing is enabled, certain components are not supported. For a full list, see [Report Time Processing](/help/components/vrs/vrs-report-time-processing.md).

## Components > All components > Report settings

* Some of the settings on the [!UICONTROL Report Settings] page do not apply. Analysis Workspace uses only the [!UICONTROL Language/Currency/Encoding] settings at the bottom: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding], and [!UICONTROL CSV Separator Character].

## Attribution

* A subset of metrics is not supported in [!UICONTROL Attribution]. For a full list, see the [Attribution FAQ](/help/analyze/analysis-workspace/attribution/faq.md).
-->
