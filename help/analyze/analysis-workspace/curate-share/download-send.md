---
description: 您可以下載已儲存和未儲存的專案，有 PDF 和 CSV 兩種格式。
seo-description: 您可以下載已儲存和未儲存的專案，有 PDF 和 CSV 兩種格式。
seo-title: 下載 PDF 或 CSV 檔案
title: 下載 PDF 或 CSV 檔案
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290 a48 ef5 f
translation-type: tm+mt
source-git-commit: b9e57162fae605719d7d85aad52a29165cb63fe4

---


# 下載 PDF 或 CSV 檔案

您可以下載已儲存和未儲存的專案，有 PDF 和 CSV 兩種格式。

PDF 或 CSV 檔案的名稱會和專案目前名稱相同。若專案尚未儲存，下載的檔案會包含專案中未儲存的變更。請注意，您不能替未儲存的專案排程 PDF 或 CSV。

>[!NOTE]
>
>我們也支援CSV格式的流失視覺效果。

>[!NOTE]
>
>當我們將專案轉換為PDF時，只會轉譯頁面上的內容。如果專案有自訂視覺效果和面板，您必須將其變更為自動縮放 (右上角按鈕)，內容才不會遭截斷。

1. 建立或開啟專案。
1. Click **[!UICONTROL Project]** &gt; **[!UICONTROL Download CSV (or Download PDF).]**

On April 11, 2019, several changes were made to **[!CSV downloads]** (and **[!Copy to Clipboard]**) from Analysis Workspace to remove formatting from exported data.
* 不再使用千分位分隔符號。(The decimal separator will continue to be included, and will adhere to the format defined under **[!UICONTROL Components &gt; Report Settings &gt; Thousands Separator]**).
* 不會顯示貨幣符號。
* 不會顯示百分比符號。
* 百分比為小數點；例如75%代表0.75。
* 時間會以秒為單位顯示。
* 世代表格僅顯示原始值；百分比移除。
* 如果數字無效，則會顯示空白儲存格。

>[!Nte：]
>
> 使用逗號做為小數點分隔符號的數值將繼續在匯出的CSV中引用。