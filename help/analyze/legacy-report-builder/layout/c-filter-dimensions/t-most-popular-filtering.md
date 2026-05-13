---
description: 能使用布林邏輯搭配 AND/OR 搜尋運算式來排名篩選並設定篩選條件。
title: 最受歡迎篩選
uuid: 558fa592-41be-4e66-8705-81262afe1fc7
feature: Report Builder
role: User, Admin
exl-id: 31587740-6caa-40cb-bb24-d7a15181f642
TQID: https://experienceleague.adobe.com/TLo2RytIM7ZQlpFMqXsTdoz7vFAXnwqoTJGHDG7gWLg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 633
ht-degree: 35%

---

# 最受歡迎篩選

{{legacy-arb}}

能使用布林邏輯搭配 AND/OR 搜尋運算式來排名篩選並設定篩選條件。

「最受歡迎」篩選是使用布林邏輯搭配 AND/OR 條件設定而成的運算式篩選器，例如[!UICONTROL 「不含 ]*`<product name>`*的頁面」搭配條件或條件群組，例如[!UICONTROL 「包含全部」]、[!UICONTROL 「包含任一項」]或[!UICONTROL 「排除全部」]。 您可以[儲存](/help/analyze/legacy-report-builder/layout/c-filter-dimensions/saved-filters.md)這些運算式，以供此活頁簿中的其他請求或其他活頁簿使用。

**建立最受歡迎篩選**

1. 建立或編輯請求，然後前往[!UICONTROL 「請求精靈: 步驟 2」]。

1. 在[!UICONTROL 「請求精靈: 步驟 2」]中，於格線內按一下維度旁的連結，然後選擇&#x200B;**[!UICONTROL 「篩選」]**。

   ![熒幕擷圖顯示[定義篩選]對話方塊，其中包含依應用程式、使用者和專案篩選的選項。](/help/admin/tools/assets/filter.png)

1. 在[!UICONTROL 「選擇頁面」]表單中啟用&#x200B;**[!UICONTROL 「最受歡迎」]**，然後設定以下選項：

   **起始排名：**&#x200B;維度的起始排名。 預設排名1表示報告資料清單中的排名最前的專案。 例如，對於維度[!UICONTROL Page]，1的起始標籤表示您網站中請求次數最多的單一頁面。 您可以指定10或其他值作為起始排名儲存格，這會產生以10開頭為最高值的報表。 量度會以遞減順序排列，因此具有最大活動的條列專案會先在清單中報告。 如果您在一個請求中需要超過50,000個頁面名稱，但要在其中報告數千個頁面，您可以複製請求並變更起始排名，以擷取50,000個區塊中的適當資料。

   **項目數：**([!UICONTROL 僅限樞紐配置]) 定義要針對日期範圍內特定度量報告的項目數。 有些量度可能會列出數百個量度專案，而其他量度則只會顯示少數專案。 例如，對於維度[!UICONTROL 網站區段]，25個專案表示報表顯示25個最常造訪的頁面。

   箭頭可讓您變更工作表中第一個資料點的[!UICONTROL 起始排名]和[!UICONTROL 專案數]。 根據預設，[!UICONTROL 起始排名]設為1，而[!UICONTROL 專案數]設為10。 這些值可針對特定量度從最小值1調整為最大值50,000。 每個量度在[!UICONTROL 專案數]上都有自己的上限。 這些欄位中不允許負值或零。 如果您選擇[!UICONTROL 起始排名]為15，[!UICONTROL 專案數]為10，量度的資料請求會傳回10個最常造訪的頁面，其中第一個最常造訪的頁面是特定日期範圍清單中的第15個。 所有排名第15到25的最請求頁面都會以遞減順序列出。

   >[!NOTE]
   >
   >將篩選條件套用至現有請求，會導致顯示的資料改變。 假設您將前10個[!UICONTROL 頁面]對應到儲存格$A$1到$A$10，其中1表示[!UICONTROL 起始排名]，10表示[!UICONTROL 專案數]。 如果您將這些值變更為[!UICONTROL 起始排名]顯示1，而[!UICONTROL 專案數]僅顯示3，則先前填入儲存格$A$4到$A$10的資料將不再顯示。

1. 若要建立搜尋運算式，請按一下&#x200B;**[!UICONTROL 「新增」]**。

1. 在[!UICONTROL 「定義篩選」]表單中，根據需求設定合適的條件。


   ![顯示[定義篩選]對話方塊的熒幕擷圖。](assets/expressions_define_filter.png)

   選取儲存格圖示可讓您找出在儲存格值中定義的條件。 ![選取儲存格圖示。](assets/select_cell_icon.png)

   **新增條件**&#x200B;連結可讓您新增條件至運算式。 可新增的條件數量沒有限制。

1. 按一下&#x200B;**[!UICONTROL 「確定」]**。

   ![右下角顯示[定義篩選]對話方塊熒幕擷圖。](assets/choose_page_02.png)

1. 在[!UICONTROL 「選擇頁面」]表單中按一下&#x200B;**[!UICONTROL 「儲存」]**，儲存運算式。
1. 按一下&#x200B;**[!UICONTROL 「確定」]**。
