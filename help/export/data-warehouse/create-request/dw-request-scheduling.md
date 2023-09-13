---
description: 說明如何建立 Data Warehouse 請求的步驟。
title: 設定Data Warehouse請求的報表目的地
feature: Data Warehouse
source-git-commit: 0abf0c76f38b481c0b72d113fe49e0da03ddd8cd
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 15%

---

# 設定Data Warehouse請求的排程選項

>[!AVAILABILITY]
>
>本文中說明的某些Data Warehouse功能(以及本節中的其他Data Warehouse文章)僅在版本的有限測試階段中可用，並且可能在您的環境中尚未提供。
>
>如需關於哪些功能尚未開放所有客戶使用的資訊，以及這些功能發行時間表的相關資訊，請參閱 [發行說明](/help/release-notes/latest.md).
>
>當該功能供一般用途時，此備註將被刪除。有關 Analytics 發佈流程的資訊，請參閱 [Adobe Analytics 功能發佈](/help/release-notes/releases.md)。

建立Data Warehouse請求時，有多種可用的設定選項。 以下資訊說明如何設定請求的排程選項。

如需有關如何開始建立請求的資訊，以及其他重要組態選項的連結，請參閱 [建立Data Warehouse請求](/help/export/data-warehouse/create-request/t-dw-create-request.md).

若要設定Data Warehouse請求的排程選項：

1. 透過選取「 」，開始在Adobe Analytics中建立請求 **[!UICONTROL 工具]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **新增**].

   如需其他詳細資訊，請參閱 [建立Data Warehouse請求](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. 在新Data Warehouse請求頁面上，選取 [!UICONTROL **排程選項**] 標籤。

   ![報表目的地索引標籤](assets/dw-scheduling-options.png) <!-- update screenshot -->

1. 填入下列欄位：

   | 選項 | 功能 |
   |---------|----------|
   | 立即傳送報告 | 以一次性報表的形式傳送報表。 選取此選項時，會隱藏所有排程選項。 |
   | 排程於稍後進行 | 提供排程報表傳送的選項。 所有選項說明如下。 |
   | 報告頻率 | 傳送報表的頻率。 <p>提供下列選項：</p><ul><li>每小時</li><p>[!UICONTROL **每小時**] 只有在 [!UICONTROL **日期範圍**] 上的選項 [!UICONTROL **一般設定**] 索引標籤已設定為 [!UICONTROL **過去一小時**].</p><li>每日</li><li>每週</li><li>每月</li><li>每年</li></ul>  <!-- Is this valid? Was in the old docs: "To schedule Data Warehouse requests for Daily, Weekly, Monthly, or Yearly, make sure *Preset* is correctly selected" --> |
   | 每月週期 | 傳送報告的月數間隔。 |
   | 當月的第幾天 | 每月傳送報告的日期。<p>當此選項可用時， [!UICONTROL **當月第幾週**] 和 [!UICONTROL **星期**] 選項則否。 選取 [!UICONTROL **替代格式**] 按鈕來回切換。 </p> |
   | 當月的第幾週 | 每月應傳送報表的周。 <p>提供下列選項：</p><ul><li>第一個</li><li>秒</li><li>第三個</li><li>第四個</li><p>在第4週傳送報告，即使是在有5週的月份中亦然。 選擇 [!UICONTROL **上次**] 是否希望報表在每個月的最後一週傳送。</p><li>上次</li></ul><p>當此選項可用時， [!UICONTROL **當月日期**] 選項則否。 選取 [!UICONTROL **替代格式**] 按鈕來回切換。 </p> |
   | 星期幾 | 應在一週中傳送報告的日期。 <p>當此選項可用時， [!UICONTROL **當月日期**] 選項則否。 選取 [!UICONTROL **替代格式**] 按鈕來回切換。 </p> |
   | 開始於 | 新排程應該開始的日期。 |
   | 每日時間 | 報表應在一天中的哪個時間傳送。 |
   | 結束傳遞選項 | 選擇何時結束排程的傳送。 您可以選擇永不結束、在特定發生次數後結束，或在特定日期結束。 |

   {style="table-layout:auto"}

1. 繼續在「 」上設定您的Data Warehouse請求 [!UICONTROL **通知電子郵件**] 標籤。 如需詳細資訊，請參閱 [設定Data Warehouse請求的通知電子郵件](/help/export/data-warehouse/create-request/dw-request-email.md).

