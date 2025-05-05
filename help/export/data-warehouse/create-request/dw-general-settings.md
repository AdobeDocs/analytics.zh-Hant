---
description: 說明如何建立 Data Warehouse 請求的步驟。
title: Data Warehouse請求一般設定
feature: Data Warehouse
exl-id: f564d5a9-78a2-431e-987a-78c4b0b9d31e
source-git-commit: 1e1a26b8595ca026fb049322125a6f91d9d5513c
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 32%

---

# Data Warehouse請求一般設定

建立 Data Warehouse 請求時有多種可用的設定選項。以下資訊說明如何設定請求的一般設定。

有關如何開始建立請求的資訊，以及其他重要設定選項的連結，請參閱「[建立 Data Warehouse 請求](/help/export/data-warehouse/create-request/t-dw-create-request.md)」。

若要設定Data Warehouse請求的一般設定：

1. 透過選取&#x200B;**[!UICONTROL 工具]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **新增**]，開始在Adobe Analytics中建立Data Warehouse要求。

   有關其他詳細資訊，請參閱「[建立 Data Warehouse 請求](/help/export/data-warehouse/create-request/t-dw-create-request.md)」。

1. 在[新增Data Warehouse要求]頁面上，選取[一般設定] **標籤。**

   ![報告目標標籤](assets/dw-general-settings.png)

1. 填入下列欄位：

   | 選項 | 函數 |
   |---------|----------|
   | 請求名稱 | 管理請求時，此名稱會顯示在主Data Warehouse頁面上。 |
   | 日期範圍 | 選取要納入報表的日期範圍。 <p>您可以選擇自訂日期或預設的日期範圍。 預設範圍是相對於報表傳送日期。</p><p>下列預設集選項可供使用：</p><ul><li>今天</li><li>昨天</li><li>最近 7 天</li><li>最近 30 天</li><li>本週</li><li>上週</li><li>過去2週</li><li>最近3週</li><li>最近4週</li><li>本月</li><li>上個月</li><li>過去一小時</li></ul> |
   | 詳細程度 | 時間粒度。 有效值為無、小時、日、週、月份、季度或年。<p>報表粒度需要更多的處理時間。如果是報告一整年的每月粒度，若是針對每個月提交一個報告請求，報告的處理速度會快很多。</p><p>**注意：**&#x200B;在Data Warehouse要求中套用詳細程度時，「日期」欄會新增到報告中。 根據所選的詳細程度，日期格式會變更，如下所示：</p><ul><li>**每小時粒度**：<ul> <li>**格式**： `mmmm d, yyyy`小時`H`</li><li>**範例**： 20XX年1月1日，小時0 </li></ul><li>**每日粒度**：<ul> <li>**格式**： `mmmm d, yyyy`</li><li>**範例**： 20XX年1月1日</li></ul><li>**每週粒度**：<ul> <li>**格式**：周`w, yyyy`</li><li>**範例**：第1週，20XX </li></ul><li>**每月粒度**：<ul> <li>**格式**： `mmmm yyyy`</li><li>**範例**： January 20XX </li></ul><li>**每季粒度**：<ul> <li>**格式**： `q`季`yyyy`</li><li>**範例**：第1季20XX </li></ul><li>**每年粒度**：<ul> <li>**格式**： `yyyy`</li><li>**範例**： 20XX</li></ul> |
   | 設為可供您組織中的使用者使用 | 只有您和任何系統管理員可看見所有Data Warehouse請求。 如果您想要讓組織中的所有人都能看到請求，請啟用此選項。 <p>如果您希望組織中的其他使用者協助建立或更新請求，啟用此選項會很有用。</p> |

   {style="table-layout:auto"}

1. 繼續在&#x200B;[!UICONTROL **建置您的報表**]&#x200B;標籤上設定您的Data Warehouse要求。 如需詳細資訊，請參閱[建立Data Warehouse要求的報表](/help/export/data-warehouse/create-request/dw-request-build-report.md)。
