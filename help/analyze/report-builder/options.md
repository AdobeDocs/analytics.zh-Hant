---
description: 在「選項」面板，您可以指定日期設定、延遲設定 (目前的資料)、記錄設定，還能設定更新。
title: Report Builder 選項
topic: Report builder
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Report Builder 選項

在「選項」面板，您可以指定日期設定、延遲設定 (目前的資料)、記錄設定，還能設定更新。

1. In the Add-Ins toolbar, click **[!UICONTROL Options]** ![](assets/options_icon.png):

| 元素 | 說明 |
|--- |--- |
| [!UICONTROL As Of Date] |  |
| 設為目前的日期 | Lets you specify or reset the  [!UICONTROL As Of Date] so that report builder uses the current date or asks you which date to use upon refresh. |
| 重新整理時詢問我是否需要設定 | 可讓您在重新整理 [!UICONTROL As Of Date] 請求時設定。 |
| [!UICONTROL Data Recency] |  |
| [!UICONTROL Include Current Data] | Lets you view data latency (also known as  [!UICONTROL Data Recency]) down to the minute in reporting, occasionally even before this data has been processed by  Adobe Analytics.<br>若未使用此選項，系統會使用已完成模式 (已處理)，但速度通常會[更緩慢](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/current-data.html)。<br>此設定適用於活頁簿中所有算是相容的「目前的資料」的請求。如果請求不相容，則會套用已完成模式。<br>請注意以下使用模式的 [!UICONTROL Include Current Data] 情況：<br>**格式選項&#x200B;**:您可以指定在格式化顯示標題時[!UICONTROL Data Recency]是否[顯示此資訊](/help/analyze/report-builder/layout/t-format-display-headers.md)。<br>**劃分**：不支援。If the  [!UICONTROL Data Recency] mode is set to the Current Data, and one of the requests contains a break-down element, this request reverts to non-current data mode. 不過，其他請求會繼續使用「目前的資料」模式。<br>**請求管理員&#x200B;**：您可以在「請求管理員」中檢視「目前的資料」欄，了解設定是否已套用至排程請求。<br>**排程活頁簿**：排程程序期間會在活頁簿層級儲存此模式。If you open a scheduled workbook that is using finalized data, and apply [!UICONTROL Include Current Data], current mode is used thereafter.<br>**權限&#x200B;**：如果使用者無權存取目前的資料，系統會隱藏此選項。啟用此選項時，如果無法套用一個或多個請求，則會發出警告。 |
| 停用目前資料不相容要求警示 | Displays warnings if the  [!UICONTROL Include Current Data] mode is selected but the data mode cannot be applied to the edited request.  For example, if you set [!UICONTROL Include Current Data], and then edit a request that has a segment selected, a warning is issued. |
| 將 Report Builder 請求記錄到本機檔案 (用於疑難排解) | 可讓您將請求記錄到本機檔案。使用此記錄檔進行疑難排解。 |
| 解譯輸入的值... | 在將篩選控制項中輸入的值視為篩選運算式之前，先解譯為儲存格位置。<br>舉例來說，如果您使用「鞋子」作為篩選條件，建立「前 10 頁」請求時，請求會顯示包含類似下列項目的儲存格：   篩選器：前 1-10 頁，頁面包含「鞋子」 |
| 有新版本可用時進行更新 | 告訴系統要在有新版本可安裝時通知您。 |
