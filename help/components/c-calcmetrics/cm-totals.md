---
title: 計算量度總計
seo-title: 計算量度總計
description: 瞭解Analytics工具中計算量度總計的差異
seo-description: 計算度量總計的計算方式
translation-type: tm+mt
source-git-commit: 540e03f2e541cc5ea0a78e4402cd367241b44200

---


# 計算量度總計

計算量度總計如何顯示在 [!DNL Reports & Analytics] 和 [!DNL Analysis Workspace]之間不同。本節說明差異。

## 計算量度總計總計 [!DNL Reports & Analytics]

當您檢視報表時 [!DNL Reports & Analytics]，計算量度一律會顯示 `n/a` 在總計下方。由於所有計算度量都是由使用者定義，因此在這種情況下總是不合理。考量下列範例:

您的組織已建立計算量度 `orders` / `visits` 判斷在您的網站上購買某物的瀏覽百分比。如果您將此量度帶入產品報表，則有幾項產品會計為單一訂單。此外，數個產品都歸屬於單一瀏覽。如果此報告包含計算量度總計，則會出現下列問題：

| 問題 | 回答 |
|---|---|
| 加總行項目是否有意義？ | 不是，因為多個產品可以包含在單一訂單中，而多個產品可以包含在單一瀏覽中。如果明細項目已匯總，則訂單總數和瀏覽總數將不符合實際訂購總數和瀏覽總數。 |
| 訂單總數和瀏覽總數是否有意義？ | 不會，因為總計不符合個別行項目的總和。此外，總訂購和瀏覽總數全都是單獨計算量度。 |

由於沒有邏輯和具體方法來判斷計算量度是否有意義，所以總忽略量度總計。如果您想要取得總計，您可以執行下列其中一項作業：

* 建立計算量度，其中包含您想納入的量度總版本。
* 建立可排程的資料擷取報表。
* 在ReportBuilder內建立資料請求。
* 使用分析工作區(請參閱下面)。

## 計算度量總計總計 [!DNL Analysis Workspace]

在Analysis工作區中，在特定情況下，計算量度會相加以顯示總計：

* [當有靜態列](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) 和 **[!UICONTROL 計算總計時，會選取目前每欄]** 選項(預設)中的值。
* 在 [環圈圖視覺化](/help/analyze/analysis-workspace/visualizations/donut.md)中。
* 在 [「摘要變更」視覺化](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)中。
