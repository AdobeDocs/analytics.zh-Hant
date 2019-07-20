---
description: 'null'
seo-description: 'null'
seo-title: 啓用廣告分析的報表套裝
title: 啓用廣告分析的報表套裝
uuid: 934f0e02-b5 d-7a-93d8-92f95 bd714 a714 a
translation-type: tm+mt
source-git-commit: e3b1ac3139f26ca3a97f3d2228276e690ec4cb79

---


# 啓用廣告分析的報表套裝

若要在Analytics中查看任何Advertising Analytics搜尋資料，您必須為Advertising Analytics報表設定每個Experience Cloud映射的報表套裝。

1. [將報表套裝對應至組織](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html)。
1. Navigate to **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.

1. Select the report suite that is [mapped to your Experience Cloud organization](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html).
1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Advertising Analytics Configuration]**.

   ![](assets/aa_reporting.png)

   >[!IMPORTANT]
   >
   >AMO ID是指要插入搜尋資料的Adobe Advertising Cloud變數。

1. 請設定您想要 AMO ID 變數使用的變數配置和到期日。轉換變數 (eVars) 可讓 Adobe Analytics 將成功事件歸因於特定變數值。有時候，變數在感應到成功事件之前會遇到一個以上的值。在此情況下，配置會決定哪個變數值可以取得該事件的評分。

   | 設定 | 定義 |
   |--- |--- |
   | 原始值 (首次) | 第一個顯示的值擁有完全分配評價，無論該變數後續的值為何。 |
   | 最近 (最後一個) | 最後一個顯示的值擁有成功事件的完全分配評價，無論先前引發的變數為何。 |
   | 過期時間 | 可讓您指定時段或事件，在經過此時段或事件發生後 eVar 值就會過期 (即不再接收成功事件的評價)。如果成功事件發生在 eVar 過期後，「無」值會接收事件的評分 (沒有作用中的 eVar 值)。 |

1. Click **[!UICONTROL Enable Advertising Analytics Reporting]** (first time), or **[!UICONTROL Update Advertising Analytics Reporting]** (subsequent times). 您的報表套裝現在已準備就緒，可以接收 Advertising Analytics 搜尋資料。您現在已經準備就緒，可以[建立 Advertising 帳戶](../../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md#concept_1958E8C15C334E8B9DC510EC8D5DCA7C)了。

