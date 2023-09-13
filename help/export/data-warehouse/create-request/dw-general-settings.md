---
description: 說明如何建立 Data Warehouse 請求的步驟。
title: Data Warehouse請求一般設定
feature: Data Warehouse
source-git-commit: ea4c1ae21f2c83bad92723e6ffd2e706fac5e1e8
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 26%

---

# Data Warehouse請求一般設定

>[!AVAILABILITY]
>
>本文中說明的某些Data Warehouse功能(以及本節中的其他Data Warehouse文章)僅在版本的有限測試階段中可用，並且可能在您的環境中尚未提供。
>
>如需關於哪些功能尚未開放所有客戶使用的資訊，以及這些功能發行時間表的相關資訊，請參閱 [發行說明](/help/release-notes/latest.md).
>
>當該功能供一般用途時，此備註將被刪除。有關 Analytics 發佈流程的資訊，請參閱 [Adobe Analytics 功能發佈](/help/release-notes/releases.md)。

建立Data Warehouse請求時，有多種可用的設定選項。 以下資訊說明如何設定請求的一般設定。

如需有關如何開始建立請求的資訊，以及其他重要組態選項的連結，請參閱 [建立Data Warehouse請求](/help/export/data-warehouse/create-request/t-dw-create-request.md).

若要設定Data Warehouse請求的一般設定：

1. 透過選取「 」，開始在Adobe Analytics中建立Data Warehouse請求 **[!UICONTROL 工具]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **新增**].

   如需其他詳細資訊，請參閱 [建立Data Warehouse請求](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. 在新Data Warehouse請求頁面上，選取 [!UICONTROL **一般設定**] 標籤。

   ![報表目的地索引標籤](assets/dw-general-settings.png)

1. 填入下列欄位：

   | 選項 | 功能 |
   |---------|----------|
   | 請求名稱 | 管理請求時，此名稱會顯示在主Data Warehouse頁面上。 |
   | 日期範圍 | 選取要納入報表的日期範圍。 <p>您可以選擇自訂日期或預設的日期範圍。 預設範圍是相對於報表傳送日期。</p><p>下列預設集選項可供使用：</p><ul><li>今天</li><li>昨天</li><li>最近 7 天</li><li>最近 30 天</li><li>本週</li><li>上週</li><li>過去2週</li><li>最近3週</li><li>最近4週</li><li>本月</li><li>上個月</li><li>過去一小時</li></ul> |
   | 詳細程度 | <!--what does this setting do? It's not the schedule/frequency... --> 時間粒度。 有效值為無、小時、日、週、月份、季度或年。<p>報表粒度需要更多的處理時間。如果是報告一整年的每月粒度，若是針對每個月提交一個報告請求，報告的處理速度會快很多。</p> |

   {style="table-layout:auto"}

1. 繼續在「 」上設定您的Data Warehouse請求 [!UICONTROL **建置報告**] 標籤。 如需詳細資訊，請參閱 [為Data Warehouse請求建立報告](/help/export/data-warehouse/create-request/dw-request-build-report.md).