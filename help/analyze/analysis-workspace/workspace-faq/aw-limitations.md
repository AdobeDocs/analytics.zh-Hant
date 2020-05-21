---
description: Adobe Analysis Workspace 及其相關元件的已知限制清單：
title: Analysis Workspace 的已知限制
translation-type: ht
source-git-commit: 025ac334f9191b6455eea0530a2a21c01199000a

---


# Analysis Workspace 的已知限制

以下為 Analysis Workspace 及其相關元件的已知限制清單：

## 表格

* 日期範圍或量度在表格中設為列時，無法新增日期比較欄。
* 區段在表格中設為列時，「從選取項目建立量度」功能會遭停用。此外，「從選取項目建立量度」不可套用至對齊日期的欄。
* 用於劃分列的條件式格式無法使用自訂範圍。
* 採用「加總列中的值來計算總計」設定時 (通常與「靜態」列項目搭配使用)，表格總列數無法跟隨趨勢產生變化。
* 「[!UICONTROL Contribution Analysis]」_只能_&#x200B;以「[!UICONTROL daily]」粒度執行。無法針對「[!UICONTROL hourly]」、「[!UICONTROL weekly]」等粒度的資料執行。

## 視覺效果

* 運用「[!UICONTROL Fallout]」、「[!UICONTROL Flow]」、「[!UICONTROL Cohort]」和「[!UICONTROL Histogram]」等區段的視覺效果，無法接受以計算量度作為輸入項目。
* [!UICONTROL Flow]：「登入/退出」維度 (例如「[!UICONTROL Entry page]」) 無法用於「流量」。
* [!UICONTROL Cohort]：非整數無法當作同類群組條件使用。

## 面板

* 區段比較：如果在初始放置區中使用區段範本，系統將不會建立「[!UICONTROL Everyone Else]」區段。

## 元件 > 區段

* 「[!UICONTROL Occurrences]」、「[!UICONTROL Unique Visitors]」等特定量度和維度無法設為區段。
* 如果從 Workspace 中建立區段，而非經由「[!UICONTROL Components > Segments]」建立，則某些元件和運算子將無法使用，例如 IP 位址。

## 元件 > 計算量度

* 計算量度無法使用於特定視覺效果中。請參閱上方的「視覺效果」。
* 計算量度無法用於「[!UICONTROL Attribution]」面板，因為計算量度本身就可包含個別的歸因模型。
* 如果從 Workspace 中建立計算量度，而非經由「[!UICONTROL Components > Segments]」建立，則某些元件和運算子將無法使用，例如：[!UICONTROL IP Address]。

## 元件 > 日期範圍

* 自訂日期範圍不支援「[!UICONTROL This day last year]」、「[!UICONTROL This day last month]」等項目。

## 元件 > 虛擬報表套裝

* 啟用報表時間處理功能時，系統不支援某些元件。如需完整清單，請參閱[報表時間處理](/help/components/vrs/vrs-report-time-processing.md)。

## 元件 > 報表設定

* 「[!UICONTROL Report Settings]」頁面上的某些設定不適用。Analysis Workspace 僅使用底部的「[!UICONTROL Language/Currency/Encoding]」設定：「[!UICONTROL Thousands separator]」、「[!UICONTROL Scheduled Report Encoding]」和「[!UICONTROL CSV Separator Character]」。

## 歸因 IQ

* 「[!UICONTROL Attribution IQ]」不支援一組量度子集。如需完整清單，請參閱[歸因 IQ 常見問題集](/help/analyze/analysis-workspace/c-panels/attribution/attribution-faq.md)。
