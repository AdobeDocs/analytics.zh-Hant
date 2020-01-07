---
title: 計算量度總計
description: 瞭解 Analytics 工具中計算量度總計的差異
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 計算量度總計

[!DNL Reports & Analytics] 和 [!DNL Analysis Workspace] 中顯示計算量度總計的方式有所不同。本節會說明其中差異。

## [!DNL Reports & Analytics] 中的計算量度總計

在 [!DNL Reports & Analytics] 中檢視報表時，計算量度在總計下方一律顯示 `n/a`。由於所有計算量度都是使用者定義的，因此在許多情況下這個總計並不適用。考量下列範例:

貴組織已建立計算量度 `orders` / `visits`，用於判斷訪客在您網站上購物占造訪次數的百分比。如果將此量度帶入產品報表中，會將數個產品歸因於單筆訂單，而且多個產品會歸因於單次造訪。如果此報表包含計算量度總計，便會出現下列問題:

| 問題 | 回答 |
|---|---|
| 條列項目加總是否有意義? | 無意義，因為單筆訂單中可包含多項產品，且單次造訪中可包含多項產品。如果彙總條列項目，訂單總計和造訪總計將不符合實際的訂單總計和造訪總計。 |
| 接受總訂單和總造訪次數是否有意義? | 無意義，因為總計與個別條列項目的總和不一致。此外，訂單總計和造訪總計是獨立計算的量度。 |

由於沒有邏輯和具體的方式可判斷計算量度在報表中是否有意義，因此會完全忽略量度總計。如果要取得總計，可以執行下列其中一項操作:

* 建立一個計算量度，其中包含您希望納入的量度總計版本。
* 建立可排程的資料擷取報表。
* 在 [!DNL ReportBuilder] 中建立資料要求。
* 使用 [!DNL Analysis Workspace] (請參閱下文)。

## [!DNL Analysis Workspace] 中的計算量度總計

在 Analysis Workspace 中檢視資料時，大多數情況下都會顯示計算量度總計。某些情況下無法提供總計，像是報表的列為混合格式時 (例如小數和貨幣混合)。

顯示總計時，通常會在伺服器端計算，這表示總計會去除重複的量度，例如造訪或訪客。在特定情況下，計算量度是透過表格各列的總和來於用戶端產生，這表示總計不會去除重複的量度，例如造訪或訪客。以下情境中會發生此情況:

* 當自由表格中使用[靜態列](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md)，且選取&#x200B;**[!UICONTROL 顯示為目前列的總和]**&#x200B;選項 (預設值) 時。
* 在[環形圖視覺效果](/help/analyze/analysis-workspace/visualizations/donut.md)中，因此數字加起來為 100%。
