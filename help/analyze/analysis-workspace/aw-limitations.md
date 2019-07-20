---
description: 'null'
seo-description: 'null'
seo-title: 工作區限制，分析工作區中已知的限制
title: 分析工作區的已知限制
translation-type: tm+mt
source-git-commit: 9d6b35c7c6de6fcb49fea3b662ff8bc9044b5e29

---


# 分析工作區的已知限制

以下列出分析工作區及其相關元件的已知限制清單：

## 表格

* 當日期範圍或度量用作表格的列時，無法新增日期比較欄。
* 當區段被用作表格的列時，從選取範圍建立量度時會停用。此外，從選取範圍建立量度不應套用至對齊日期的欄。
* 劃分列的條件式格式無法使用自訂範圍。
* 套用列值設定時(通常用於靜態列項目)計算總計時，無法趨勢化表格總計列。
* [!UICONTROL 貢獻分析] 只能在 [!UICONTROL 每日] 詳細程度 _上執行_。It cannot be run against [!UICONTROL hourly], [!UICONTROL weekly], etc., data.

## 視覺效果

* Visualizations that leverage segmentation, such as [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort], and [!UICONTROL Histogram], cannot accept calculated metrics as inputs.
* [!UICONTROL 流程]：登入/退出維度(例如 [!UICONTROL 登入頁面])無法用於流量。
* [!UICONTROL 世代]：非整數無法用作世代標準。

## 面板

* Segment Comparison: The [!UICONTROL Everyone Else] segment does not get created if a segment template is used in the initial drop zone.

## 元件&gt;區段

* Certain metrics and dimensions are not segmentable, such as [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], etc.
* Certain components and operators are unavailable if a segment is created from Workspace (as opposed to being created from [!UICONTROL Components &gt; Segments]). 例如IP位址。

## 元件&gt;計算量度

* 計算量度無法用於某些視覺化。請參閱上述「視覺效果」。
* Calculated metrics cannot be used in the [!UICONTROL Attribution] panel, since calculated metrics themselves can include separate attribution models.
* Certain components and operators are unavailable if a calculated metric is created from Workspace (as opposed to being created from [!UICONTROL Components &gt; Segments]). For example, [!UICONTROL IP Address].

## 元件&gt;日期範圍

* Custom date ranges do not support [!UICONTROL This day last year], [!UICONTROL This day last month], etc.

## 元件&gt;虛擬報表套裝

* 啓用報告時間處理時，不支援某些元件。For a full list, see [Report Time Processing](/help/components/vrs/vrs-report-time-processing.md).

## 元件&gt;報表設定

* [!UICONTROL 「報表設定」] 頁面上的部分設定不適用。Analysis Workspace uses only the [!UICONTROL Language/Currency/Encoding] settings at the bottom: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding], and [!UICONTROL CSV Separator Character].

## 歸因 IQ

* [!UICONTROL Attribution IQ不支援量度子集]。For a full list, see the [Attribution IQ FAQ](/help/analyze/analysis-workspace/attribution-iq/attribution-faq.md).