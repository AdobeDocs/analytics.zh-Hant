---
title: 計算量度總計
seo-title: 計算量度總計
description: 瞭解Analytics工具中計算量度總計的差異
seo-description: 計算度量總計的計算方式
translation-type: tm+mt
source-git-commit: 658925799c530b46ff7b56d5d0685af6d9fef1b8

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
* Create a data request within [!DNL ReportBuilder].
* 使用 [!DNL Analysis Workspace] (請參閱下面)。

## 計算度量總計總計 [!DNL Analysis Workspace]

在分析工作區中檢視資料時，大部分情況下會顯示計算量度總計。在某些情況下，不可能提供總計，例如，當報表的行為混合格式(例如小數點和貨幣)時。

顯示總計時，通常會計算伺服器端，這表示總消除重復量度(例如造訪或訪客)。在特定情況下，計算度量是透過跨表格列的總和產生的，這表示總計不會去除諸如瀏覽或訪客等重復量度。發生此情況：

* [在自由表格](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) 中使用靜態列時，會選取「 **[!UICONTROL 顯示為目前列]** 」選項(預設)的總和。
* 在 [環圈圖視覺化](/help/analyze/analysis-workspace/visualizations/donut.md)中，數字最多可增加100%。
