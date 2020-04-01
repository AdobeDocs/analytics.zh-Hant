---
description: Adobe Analysis Workspace 及其相關元件的已知限制清單：
title: Analysis Workspace 的已知限制
translation-type: tm+mt
source-git-commit: fd4d016ffd47e74ebcd4c850f35a5471ca358366

---


# Analysis Workspace 的已知限制

以下為 Analysis Workspace 及其相關元件的已知限制清單：

## 表格

* 日期範圍或量度在表格中設為列時，無法新增日期比較欄。
* 區段在表格中設為列時，「從選取項目建立量度」功能會遭停用。此外，「從選取項目建立量度」不可套用至對齊日期的欄。
* 用於劃分列的條件式格式無法使用自訂範圍。
* 採用「加總列中的值來計算總計」設定時 (通常與「靜態」列項目搭配使用)，表格總列數無法跟隨趨勢產生變化。
* [!UICONTROL Contribution Analysis] 只能以詳細程 [!UICONTROL daily] 度 _執行_。 It cannot be run against [!UICONTROL hourly], [!UICONTROL weekly], etc., data.

## 視覺效果

* Visualizations that leverage segmentation, such as [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort], and [!UICONTROL Histogram], cannot accept calculated metrics as inputs.
* [!UICONTROL Flow]:登入／退出維度，例如, [!UICONTROL Entry page]不能用於流。
* [!UICONTROL Cohort]:非整數不能用作同類群組條件。

## 面板

* Segment Comparison: The [!UICONTROL Everyone Else] segment does not get created if a segment template is used in the initial drop zone.

## 元件 > 區段

* Certain metrics and dimensions are not segmentable, such as [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], etc.
* Certain components and operators are unavailable if a segment is created from Workspace (as opposed to being created from [!UICONTROL Components > Segments]). 例如 IP 位址。

## 元件 > 計算量度

* 計算量度無法使用於特定視覺效果中。請參閱上方的「視覺效果」。
* Calculated metrics cannot be used in the [!UICONTROL Attribution] panel, since calculated metrics themselves can include separate attribution models.
* Certain components and operators are unavailable if a calculated metric is created from Workspace (as opposed to being created from [!UICONTROL Components > Segments]). 例如：[!UICONTROL IP Address]。

## 元件 > 日期範圍

* 自訂日期範圍不支 [!UICONTROL This day last year]援 [!UICONTROL This day last month]等。

## 元件 > 虛擬報表套裝

* 啟用報表時間處理功能時，系統不支援某些元件。如需完整清單，請參閱[報表時間處理](/help/components/vrs/vrs-report-time-processing.md)。

## 元件 > 報表設定

* Some of the settings on the [!UICONTROL Report Settings] page do not apply. 分析工作區僅使用 [!UICONTROL Language/Currency/Encoding] 底部的設定： [!UICONTROL Thousands separator]、 [!UICONTROL Scheduled Report Encoding]和 [!UICONTROL CSV Separator Character]。

## 歸因 IQ

* A subset of metrics is not supported in [!UICONTROL Attribution IQ]. 如需完整清單，請參閱[歸因 IQ 常見問題集](/help/analyze/analysis-workspace/c-panels/attribution/attribution-faq.md)。
