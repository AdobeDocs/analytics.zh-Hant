---
description: 說明如何建立 Data Warehouse 請求的步驟。
title: 為 Data Warehouse 請求設定報告目標
feature: Data Warehouse
exl-id: e5f8acaa-156f-41fb-a0fc-bc5475f1f3b7
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 33%

---

# 設定Data Warehouse請求的排程選項

建立 Data Warehouse 請求時有多種可用的設定選項。以下資訊說明如何設定請求的排程選項。

有關如何開始建立請求的資訊，以及其他重要設定選項的連結，請參閱「[建立 Data Warehouse 請求](/help/export/data-warehouse/create-request/t-dw-create-request.md)」。

若要設定Data Warehouse請求的排程選項：

1. 如果還沒有，可選取「**[!UICONTROL 工具]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **新增**]」，開始在 Adobe Analytics 中建立請求。

   有關其他詳細資訊，請參閱「[建立 Data Warehouse 請求](/help/export/data-warehouse/create-request/t-dw-create-request.md)」。

1. 在新的Data Warehouse請求頁面上，選取&#x200B;[!UICONTROL **排程選項**]&#x200B;索引標籤。

   ![報告目的地索引標籤](assets/dw-scheduling-options.png) <!-- update screenshot -->

1. 填入下列欄位：

   | 選項 | 函數 |
   |---------|----------|
   | [!UICONTROL **立即傳送報告**] | 以一次性報表的形式傳送報表。 選取此選項時，會隱藏所有排程選項。 |
   | [!UICONTROL **排程在稍後進行**] | 提供排程報表傳送的選項。 所有選項說明如下。 |
   | [!UICONTROL **報告頻率**] | 傳送報表的頻率。 <p>提供下列選項：</p><ul><li>每小時</li><p>[!UICONTROL **每小時**]&#x200B;僅當&#x200B;[!UICONTROL **一般設定**]&#x200B;索引標籤上的&#x200B;[!UICONTROL **日期範圍**]&#x200B;選項設定為&#x200B;[!UICONTROL **過去小時**]&#x200B;時才能使用。</p><li>每日</li><li>每週</li><li>每月</li><li>每年</li></ul><p>系統會根據您選取的頻率顯示其他選項。</p> |
   | [!UICONTROL **開始於**] | 新排程應該開始的日期。 |
   | [!UICONTROL **每日時間**] | 報表應在一天中的哪個時間傳送。 |
   | [!UICONTROL **結束傳遞選項**] | 選擇何時結束排程的傳送。 您可以選擇永不結束、在特定發生次數後結束，或在特定日期結束。 |

   {style="table-layout:auto"}

1. 繼續在&#x200B;[!UICONTROL **通知電子郵件**]&#x200B;標籤上設定您的Data Warehouse請求。 如需詳細資訊，請參閱[設定Data Warehouse要求的通知電子郵件](/help/export/data-warehouse/create-request/dw-request-email.md)。
