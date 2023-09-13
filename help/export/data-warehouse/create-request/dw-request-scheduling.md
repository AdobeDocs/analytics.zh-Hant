---
description: 說明如何建立 Data Warehouse 請求的步驟。
title: 設定Data Warehouse請求的報表目的地
feature: Data Warehouse
source-git-commit: 3b116cb8d0d3f3eb86b512d712f37b29876f2b22
workflow-type: tm+mt
source-wordcount: '375'
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
   | [!UICONTROL **立即傳送報告**] | 以一次性報表的形式傳送報表。 選取此選項時，會隱藏所有排程選項。 |
   | [!UICONTROL **排程於稍後進行**] | 提供排程報表傳送的選項。 所有選項說明如下。 |
   | [!UICONTROL **報告頻率**] | 傳送報表的頻率。 <p>提供下列選項：</p><ul><li>每小時</li><p>[!UICONTROL **每小時**] 只有在 [!UICONTROL **日期範圍**] 上的選項 [!UICONTROL **一般設定**] 索引標籤已設定為 [!UICONTROL **過去一小時**].</p><li>每日</li><li>每週</li><li>每月</li><li>每年</li></ul><p>系統會根據您選取的頻率顯示其他選項。</p> |
   | [!UICONTROL **開始於**] | 新排程應該開始的日期。 |
   | [!UICONTROL **每日時間**] | 報表應在一天中的哪個時間傳送。 |
   | [!UICONTROL **結束傳遞選項**] | 選擇何時結束排程的傳送。 您可以選擇永不結束、在特定發生次數後結束，或在特定日期結束。 |

   {style="table-layout:auto"}

1. 繼續在「 」上設定您的Data Warehouse請求 [!UICONTROL **通知電子郵件**] 標籤。 如需詳細資訊，請參閱 [設定Data Warehouse請求的通知電子郵件](/help/export/data-warehouse/create-request/dw-request-email.md).

