---
description: Adobe Analysis Workspace 及其相關元件的已知限制清單：
title: Analysis Workspace 的已知限制
feature: Workspace Basics
role: User, Admin
exl-id: 520e970b-1387-4f70-985b-bfe397f4a21b
source-git-commit: 2eff7656741bdba3d5d7d1f33e9261b59f8e6083
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 100%

---

# Analysis Workspace 的已知限制

以下為 Analysis Workspace 及其相關元件的已知限制清單：

## 表格

* 日期範圍或量度在表格中設為列時，無法新增日期比較欄。
* 區段在表格中設為列時，「從選取項目建立量度」功能會遭停用。此外，「從選取項目建立量度」不可套用至對齊日期的欄。
* 用於劃分列的條件式格式無法使用自訂範圍。
* 採用「加總列中的值來計算總計」設定時 (通常與「靜態」列項目搭配使用)，表格總列數無法跟隨趨勢產生變化。
* [!UICONTROL 貢獻分析]_只能_&#x200B;在[!UICONTROL 每日]粒度下執行，無法針對[!UICONTROL 每小時]、[!UICONTROL 每週]等粒度的資料執行。

## 視覺效果

* 運用[!UICONTROL 「流失」]、[!UICONTROL 「流量」]、[!UICONTROL 「同類群組」]、[!UICONTROL 「長條圖」]等區段的視覺效果，無法將計算量度設為輸入項目。
* [!UICONTROL 流量]：「登入/退出」維度 (例如[!UICONTROL 「登入頁面」]) 無法用於「流量」。
* [!UICONTROL 同類群組]：非整數無法當作同類群組條件使用。

## 面板

* 區段比較：如果在初始放置區中使用區段範本，系統不會建立[!UICONTROL 「其他人」]區段。

## 元件 > 區段

* [!UICONTROL 「發生次數」]、[!UICONTROL 「不重複訪客」]等特定量度和維度無法設為區段。
* 在[面板放置區](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=zh-Hant)中建立的臨時區段是一種快速篩選器。除非設定為公開，否則它們不會顯示在 Workspace 或「區段」元件管理器的左側邊欄中。如需更多資訊，請參閱[快速區段](/help/analyze/analysis-workspace/components/segments/quick-segments.md)。

## 元件 > 計算量度

* 計算量度無法使用於特定視覺效果中。請參閱上方的「視覺效果」。
* 計算量度無法用於[!UICONTROL 「歸因」]面板，因為計算量度本身就可包含個別的歸因模型。
* 如果從 Workspace 中建立計算量度，而非經由[!UICONTROL 「元件 > 區段」]建立，則某些元件和運算子將無法使用，例如 [!UICONTROL IP 位址]。

## 元件 > 日期範圍

* 自訂日期範圍不支援[!UICONTROL 「去年的今天」]、[!UICONTROL 「上個月的今天」]等。

## 元件 > 虛擬報表套裝

* 啟用報表時間處理功能時，系統不支援某些元件。如需完整清單，請參閱[報表時間處理](/help/components/vrs/vrs-report-time-processing.md)。

## 元件 > 所有元件 > 報告設定

* [!UICONTROL 「報表設定」]頁面上的某些設定並不適用。Analysis Workspace 僅會使用以下幾種位於底部的[!UICONTROL 「語言/貨幣/編碼」]設定：[!UICONTROL 「千位分隔符號」]、[!UICONTROL 「排程報表編碼」]和[!UICONTROL 「CSV 分隔符號字元」]。

## 歸因

* 有一部分的量度不受「[!UICONTROL 歸因]」支援。如需完整清單，請參閱[歸因常見問題集](/help/analyze/analysis-workspace/attribution/faq.md)。
