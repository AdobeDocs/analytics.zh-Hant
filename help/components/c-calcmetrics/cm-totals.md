---
title: 計算量度總計
description: 瞭解Analytics工具中計算量度總數的差異
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 計算量度總計

計算量度總計的顯示方式在與之 [!DNL Reports & Analytics] 間不 [!DNL Analysis Workspace]同。 本節將說明差異。

## 計算量度總計 [!DNL Reports & Analytics]

在中檢視報表時， [!DNL Reports & Analytics]計算量度一律顯示 `n/a` 在總計下方。 由於所有計算量度都是使用者定義的，因此有許多情況下，這個總計並不合理。 考量下列範例:

您的組織已建立計算量 `orders` 度/ `visits` ，以判斷在您網站上購買物品的瀏覽次數百分比。 如果您將此量度帶入產品報表，會將數個產品歸因於單一訂單。 此外，數種產品會歸因於單次瀏覽。 如果此報表包含計算量度總計，則會出現下列問題：

| 問題 | 回答 |
|---|---|
| 行項目加總是否有意義？ | 它不會，因為單一訂單中可包含多個產品，而單一瀏覽中可包含多個產品。 如果匯總行項目，訂單總數和瀏覽總數將不符合實際訂購總數和瀏覽總數。 |
| 接受總訂單和總瀏覽次數是否有意義？ | 它不符合，因為總計不符合個別行項目的總和。 此外，「訂購總數」和「瀏覽總數」是單獨計算的度量。 |

由於沒有邏輯和具體的方法來判斷計算度量在報告中是否有意義，因此會完全忽略度量總計。 如果要獲得總計，可以執行下列操作之一：

* 建立包含您要包含之量度「總版本」的計算量度。
* 建立可排程的資料擷取報表。
* Create a data request within [!DNL ReportBuilder].
* 使 [!DNL Analysis Workspace] 用（請參閱下面）。

## 計算量度總計(位於 [!DNL Analysis Workspace]

在分析工作區中檢視資料時，大多數情況下都會顯示計算量度總計。 在某些情況下，無法提供總計，例如報表列為混合格式（例如小數和貨幣）。

顯示總計時，通常會在伺服器端計算，這表示總計會去除重複的度量，例如瀏覽或訪客。 在特定情況下，計算量度是透過表格各列的總和來產生用戶端，這表示總計不會去重複的量度，例如瀏覽或訪客。 發生這種情況：

* 當自 [由表格中](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) ，使用靜態列時， **[!UICONTROL 會選取「顯示為目前列的總和]** 」選項（預設）。
* 在環圈 [圖視覺化中](/help/analyze/analysis-workspace/visualizations/donut.md)，這樣數字就會增加100%。
