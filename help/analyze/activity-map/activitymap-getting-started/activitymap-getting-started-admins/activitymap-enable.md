---
description: 說明若想啟用 Activity Map 連結收集和使用者下載，Analytics 管理員需要完成的步驟。
title: 啟用 Activity Map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
feature: Activity Map
role: Business Practitioner, Administrator
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 95%

---

# 啟用 Activity Map{#enable-activity-map}

說明若想啟用 Activity Map 連結收集和使用者下載，Analytics 管理員需要完成的步驟。

## 步驟 1.將 AppMeasurement (Javascript) 代碼更新至 v1.6 (或更高版本) {#section_5D1586289DF2489289B1B6C1C80C300D}

Activity Map 模組屬於 AppMeasurement.js 檔案的一部分 (位於檔案的頂端)。AppMeasurement 程式庫在初始化時就會載入 Activity Map 模組。

除非更新到 AppMeasurement 的這個版本 (或更高版本)，否則無法收集 Activity Map 資料。

1. 前往&#x200B;**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL 所有管理員]** > **[!UICONTROL 代碼管理器]**&#x200B;和[實作，以下載最新的AppMeasurement代碼(AppMeasurement_Javascript-1.6.zip)。](https://docs.adobe.com/content/help/zh-Hant/analytics/implementation/js/overview.html)

   我們隨附一些[實施代碼範例](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md)，協助您具體了解由於加入 Activity Map 模組而對代碼進行的變更。

1. 驗證實施：

   1. 當按下可點按元素，資料就會儲存至名為 s_sq 的 Cookie 中。
   1. 可以在追蹤呼叫的查詢字串中看到 Activity Map 資料。例如：

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. 依照&#x200B;**[!UICONTROL 「各地區的 Activity Map 連結」]**&#x200B;劃分此報表，查看該頁面的連結/地區：![](assets/am_breakdown.png){width=&quot;400px&quot;}

## 步驟 2.啟用 Activity Map 報表 {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

首先，您必須在報表套裝層級啟用 Activity Map 報表。

1. 登入 Adobe Analytics，並依序導覽至&#x200B;**[!UICONTROL 「Analytics]** > ****&#x200B;管理員 > **[!UICONTROL 報表套裝]** > 選取報表套裝 > **[!UICONTROL 編輯設定]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map 報表」]**。
1. Activity Map 會將連結資料收集至 Activity Map 報表中。您必須先按一下&#x200B;**[!UICONTROL 「啟用 Activity Map 報表」]**&#x200B;啟動變數，才能真正啟動。

   此步驟會新增收集資料所需的所有 Analytics 維度。

1. 大約一小時後，查看[「Activity Map 頁面報表」](/help/analyze/activity-map/activitymap-reporting-analytics.md)，當中就會顯示使用者有點按連結的所有頁面。

## 步驟 3.新增使用者至 Activity Map 存取群組 {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. 按一下&#x200B;**[!UICONTROL 「新增使用者至群組」]**。

   這會將您帶往管理控制台中的群組管理頁面。

1. [新增使用者到此群組](https://docs.adobe.com/content/help/zh-Hant/analytics/admin/user-product-management/user-groups/groups.html)，然後&#x200B;**[!UICONTROL 儲存群組]**。

1. 如此可讓您的管理員使用者從&#x200B;**[!UICONTROL 「Adobe Analytics]** > **[!UICONTROL 工具]** > **[!UICONTROL Activity Map」]**&#x200B;下載 Activity Map。

>[!NOTE]
>
> 如果您希望非管理員使用者下載 Activity Map，請建立新的使用者群組，以提供「工具」和「舊版 ClickMap 安裝程式」的權限。此權限層級與「Activity Map 存取」結合，提供下載和使用工具的權限。
