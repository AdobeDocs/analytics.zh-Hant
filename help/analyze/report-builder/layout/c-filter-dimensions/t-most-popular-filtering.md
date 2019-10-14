---
description: 能使用布林邏輯搭配 AND/OR 搜尋運算式來排名篩選並設定篩選條件。
seo-description: 能使用布林邏輯搭配 AND/OR 搜尋運算式來排名篩選並設定篩選條件。
seo-title: 最受歡迎篩選
solution: Analytics
title: 最受歡迎篩選
topic: Report Builder
uuid: 558fa592-41be-4e66-8705-81262afe1fc7
translation-type: tm+mt
source-git-commit: 506c670e4b2903cc71bb6880cd74c3392bbc751c

---


# 最受歡迎篩選

能使用布林邏輯搭配 AND/OR 搜尋運算式來排名篩選並設定篩選條件。

Most Popular filters are expression filters that you configure using Boolean logic with AND/OR conditions, such as [!UICONTROL Page does not contain]*`<product name>`* with conditions or groups of conditions like [!UICONTROL Includes All], [!UICONTROL Includes Any], or [!UICONTROL Excludes All]. You can [save](../../../../analyze/report-builder/layout/c-filter-dimensions/saved-filters.md#concept_562AC2C5628247909FBA5E1867BB6AE5) these expressions for other request in this workbook, or in other workbooks.

**建立最受歡迎篩選**

1. 建立或編輯請求，然後前往[!UICONTROL 「請求精靈: 步驟 2」]。

   ![步驟資訊](assets/dimension_filter.png)

1. On the [!UICONTROL Request Wizard: Step 2], click the link next to the dimension in the grid, then choose **[!UICONTROL Filter]**.
1. 在[!UICONTROL 「選擇頁面]**」表單中啟用[!UICONTROL 「最受歡迎]**」，然後設定以下選項:

   **起始排名:**&#x200B;維度的起始排名。預設排名 1 代表報告之資料清單中最上層的項目。例如，對於「[!UICONTROL 頁面]」維度來說，起始標記 1 表示是網站中最常收到請求的單一頁面。您可以將 10 或其他值指定為起始排名儲存格，這會產生以 10 (最高排名) 起始的報表。由於度量是以遞減順序排列的，因此系統會將活動數量最多的行項目報告為清單中的第一個項目。如果一個請求須傳回 50,000 個以上的頁面名稱，但是要報告的頁面高達數千頁，您可以複製請求並變更起始排名，以利用 50,000 為單位的區塊擷取適量的資料。

   **項目數:** ([!UICONTROL 僅限樞紐配置]) 定義要針對日期範圍內特定度量報告的項目數。某些度量會針對一個度量列出數百個項目，但某些度量可能只會顯示一些項目。例如，對於「[!UICONTROL 網站區段]」維度，25 個項目代表報告會顯示 25 個最常受訪的頁面。

   箭號可讓您變更工作表中第一個資料點的「[!UICONTROL 起始排名]」和「[!UICONTROL 項目數]」。依預設，「[!UICONTROL 起始排名]」設定為 1 而「[!UICONTROL 項目數]」為 10。對於某些度量來說，這些值的調整範圍介於 1 到 50,000 之間。每個度量的「[!UICONTROL 項目數]」都有不同的上限。這些欄位都不允許負數值或零。如果您將「[!UICONTROL 起始排名]」選為 15 並將「[!UICONTROL 項目數]」選為 10，度量的資料請求會傳回 10 個最常受訪的頁面，而清單中第一個最常受訪的頁面是特定日期範圍內排名第 15 名的頁面。系統會以遞減順序列出所有最常收到請求的頁面中第 15 名到第 25 名的頁面。

   >[!NOTE]
   >
   >將篩選套用至現有請求會造成顯示資料的變更。 假設您已將前十名的[!UICONTROL 頁面]映射至儲存格 $A$1 到 $A$10，並將「[!UICONTROL 起始排名]」指定為 1，將「[!UICONTROL 項目數]」指定為 10。如果您變更這些值，使「[!UICONTROL 起始排名]」顯示 1，使「[!UICONTROL 項目數]」只顯示 3，先前填入儲存格 $A$4 到 $A$10 的資料將會消失。

1. To create a search expression, click **[!UICONTROL Add]**.

   ![步驟資訊](assets/expressions_define_filter.png)

1. 在[!UICONTROL 「定義篩選」]表單中，根據需求設定合適的條件。

   ![select_cell_icon.png](assets/select_cell_icon.png): 讓您找出在儲存格值中定義的條件。

   **新增條件:** 將條件新增至運算式。可新增的條件數量沒有限制。

1. Click **[!UICONTROL OK]**.

   ![步驟資訊](assets/choose_page_02.png)

1. 在[!UICONTROL 「選擇頁面」]**表單中按一下[!UICONTROL 「儲存」]**&#x200B;以儲存運算式。
1. Click **[!UICONTROL OK]**.
