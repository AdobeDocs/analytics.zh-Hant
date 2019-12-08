---
description: 在「選項」面板，您可以指定日期設定、延遲設定 (目前的資料)、記錄設定，還能設定更新。
title: Report Builder 選項
topic: Report builder
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Report Builder 選項

在「選項」面板，您可以指定日期設定、延遲設定 (目前的資料)、記錄設定，還能設定更新。

1. In the Add-Ins toolbar, click **[!UICONTROL Options]** ![](assets/options_icon.png):

| 元素 | 說明 |
|--- |--- |
| [!UICONTROL 截止日期] |  |
| 設為目前的日期 | 可讓您指定或重設「[!UICONTROL 截止日期]」以讓 Report Builder 使用目前的日期，或在重新整理時詢問您要使用哪個日期。 |
| 重新整理時詢問我是否需要設定 | 可讓您在重新整理請求時設定「[!UICONTROL 截止日期]」。 |
| [!UICONTROL 資料時近] |  |
| [!UICONTROL 包含目前的資料] | 可讓您檢視最晚到報告前最後一刻的資料延遲度 (也稱為「[!UICONTROL 資料時近]」)，有時甚至是在 Adobe Analytics 處理資料之前。<br>當您未使用此選項時，會使用已完成模式（已處理），這通常會更為 [延遲](https://marketing.adobe.com/resources/help/en_US/reference/data_latency.html)。<br>此設定適用於活頁簿中所有算是相容的「目前的資料」的請求。如果請求不相容，則會套用已完成模式。<br>請注意以下使用「包括當前數 [!UICONTROL 據」模式] :「格式<br>**選項」的情況**:您可以指定格式化顯示標題時是否顯[!UICONTROL 示此資訊(資料時近]) [](/help/analyze/report-builder/layout/t-format-display-headers.md)。<br>**分支**: 不支援。如果「[!UICONTROL 資料時近]」模式設為「目前的資料」，且其中一個請求包含分支元素，則此請求會回復為非目前資料模式。不過，其他請求會繼續使用「目前的資料」模式。<br>**請求管理員**: 您可以在「請求管理員」中檢視「目前的資料」欄，瞭解設定是否已套用至排程請求。<br>**排程活頁簿**: 排程程序期間會在活頁簿層級儲存此模式。If you open a scheduled workbook that is using finalized data, and apply [!UICONTROL Include Current Data], current mode is used thereafter.<br>**權限**: 如果使用者無權存取目前的資料，則會隱藏此選項。啟用此選項時，如果無法套用一個或多個請求，則會發出警告。 |
| 停用目前資料不相容要求警示 | 如果選取「[!UICONTROL 包含目前的資料]」模式，但資料模式無法套用至編輯的請求，則會顯示警告。例如，如果您設定「[!UICONTROL 包含目前的資料]」，然後編輯已選取區段的請求，則會發出警告。 |
| 將 Report Builder 請求記錄到本機檔案 (用於疑難排解) | 可讓您將請求記錄到本機檔案。使用此記錄檔進行疑難排解。 |
| 解譯輸入的值... | 在將篩選控制項中輸入的值視為篩選運算式之前，先解譯為儲存格位置。<br>例如，如果您建立「前10頁」請求，使用篩選鞋，請求會顯示包含類似下列項目的儲存格：  篩選：前1-10頁，頁面包含鞋 |
| 有新版本可用時進行更新 | 告訴系統要在有新版本可安裝時通知您。 |
