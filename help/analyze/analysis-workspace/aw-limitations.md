---
description: 'null'
seo-description: 'null'
seo-title: 工作區限制，分析工作區的已知限制
title: 分析工作區的已知限制
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# 分析工作區的已知限制

以下是分析工作區及其相關元件的已知限制清單：

## 表格

* 當日期範圍或量度用作表格的列時，無法新增日期比較欄。
* 當區段用作表格的列時，會停用從選取範圍建立量度。 此外，「從選取範圍建立量度」不應套用至與日期對齊的欄。
* 劃分列的條件式格式無法使用自訂範圍。
* 套用「計算總行數」設定時（通常與「靜態」行項目搭配使用），表格總行數無法趨勢化。
* [!UICONTROL 貢獻分析] ，只能以每日詳細 [!UICONTROL 程度] 執 _行_。 無法對每小時、 [!UICONTROL 每週][!UICONTROL 等資]料執行。

## 視覺效果

* 運用「流失」、「流量」、「同類群組 [!UICONTROL 」]、「直方圖」分段的視覺化 [!UICONTROL ，無法接受計]算量度作為輸入。
* [!UICONTROL 流量]:登入／退出維度(例如「登入 [!UICONTROL 頁面」])無法用於「流量」。
* [!UICONTROL 同類群組]:非整數不能用作同類群組條件。

## 面板

* 區段比較：如果 [!UICONTROL 在初始放置區中使用區段範本，則不會建立「其他人] 」區段。

## 元件&gt;區段

* 某些度量和維度無法區隔，例如 [!UICONTROL 發生][!UICONTROL 次數、獨特訪客]等。
* 如果從「工作區」建立區段（而非從「元件&gt;區段」建立區段），則某些元件和運算子 [!UICONTROL 將無法使用]。 例如，IP位址。

## 元件&gt;計算量度

* 計算量度無法用於特定視覺化。 請參閱上方的「視覺化」。
* 計算量度無法用於「歸 [!UICONTROL 因] 」面板，因為計算量度本身可以包含個別的歸因模型。
* 如果從「工作區」建立計算量度（而非從「元件&gt;區段」建立），某些元件和運算子 [!UICONTROL 將無法使用]。 例如， [!UICONTROL IP位址]。

## 元件&gt;日期範圍

* 自訂日期範圍不支 [!UICONTROL 援去年的今天][!UICONTROL 、上個月的這天]，等等。

## 元件&gt;虛擬報表套裝

* 啟用報告時間處理時，不支援某些元件。 如需完整清單，請參閱報 [告時間處理](/help/components/vrs/vrs-report-time-processing.md)。

## 元件&gt;報表設定

* 「報表設定」頁面上的 [!UICONTROL 某些設定] ，則不適用。 分析工作區僅使用 [!UICONTROL 底部的「語言／貨幣／編碼] 」設定：千 [!UICONTROL 位分隔符號]、 [!UICONTROL 排程報表編碼]、 [!UICONTROL CSV分隔符號字元]。

## 歸因 IQ

* Attribution IQ不支援度量的 [!UICONTROL 子集]。 如需完整清單，請參閱 [Attribution IQ常見問答](/help/analyze/analysis-workspace/attribution-iq/attribution-faq.md)。
