---
description: 您可以下載已儲存和未儲存的專案，有 PDF 和 CSV 兩種格式。
title: 下載 PDF 或 CSV 檔案
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: tm+mt
source-git-commit: 08d564f7fb06b94c2010515ea4a1dcbb2e6e2815

---


# 下載 PDF 或 CSV 檔案

您可以下載已儲存和未儲存的專案，有 PDF 和 CSV 兩種格式。

PDF 或 CSV 檔案的名稱會和專案目前名稱相同。若專案尚未儲存，下載的檔案會包含專案中未儲存的變更。請注意，您不能替未儲存的專案排程 PDF 或 CSV。

請記住：

* 我們也支援 CSV 格式的流失視覺效果。
* 將專案轉譯為 PDF 時，我們只會轉譯頁面上的內容。如果專案有自訂視覺效果和面板，您必須將其變更為自動縮放 (右上角按鈕)，內容才不會遭截斷。
* 在瀏覽器中下載的PDF匯出可能需要幾分鐘的時間。 這是因為我們必須在伺服器上重新執行整個專案，才能以PDF格式轉譯。 我們建議您在瀏覽器中下載PDF之前，不要離開專案。 不過，您可以在等待時繼續變更專案。
* 我們知道，如果您有很長的工作區專案，PDF目前會匯出為一個巨大的頁面，而非編頁檔案。 我們正在改善工作區PDF匯出，以便進行分頁。

1. 建立或開啟專案。
1. 按一下 **[!UICONTROL Project]** > **[!UICONTROL Download CSV (or Download PDF).]**

2019 年 4 月 11 日起，Analysis Workspace 中的&#x200B;**[!CSV 「下載」]**(和&#x200B;**[!C「複製至剪貼簿」]**) 功能已有諸多變動，以移除匯出資料中的格式設定。
* 不再使用千分位分隔符號。(The decimal separator will continue to be included, and will adhere to the format defined under **[!UICONTROL Components > Report Settings > Thousands Separator]**).
* 不顯示貨幣符號。
* 不顯示百分比符號。
* 百分比以小數點形式表示，例如 75% 顯示為 0.75。
* 時間以秒為單位顯示。
* 同類群組表格僅顯示原始值；已移除百分比。
* 如果數字無效，則顯示空白儲存格。

>[!N注意：]
>
> 匯出的 CSV 會繼續引用使用逗號作為小數分隔符號的數值。
