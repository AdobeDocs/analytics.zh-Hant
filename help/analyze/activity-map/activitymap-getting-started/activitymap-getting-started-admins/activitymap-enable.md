---
description: 說明若想啟用 Activity Map 連結收集和使用者下載， Analytics 管理員需要完成的步驟。
seo-description: 說明若想啟用 Activity Map 連結收集和使用者下載， Analytics 管理員需要完成的步驟。
seo-title: 啓用Activity Map
solution: Analytics
title: 啓用Activity Map
topic: Activity Map
uuid: 30433319-d0 e6-4977-951a-4492b356 e1 f
translation-type: tm+mt
source-git-commit: 8f72f8cf086be0eade5616b074123a9f22e33347

---


# Enable Activity Map{#enable-activity-map}

說明若想啟用 Activity Map 連結收集和使用者下載， Analytics 管理員需要完成的步驟。

## 步驟 1. 將 AppMeasurement (Javascript) 代碼更新至 v1.6 (或更高版本) {#section_5D1586289DF2489289B1B6C1C80C300D}

Activity Map 模組屬於 AppMeasurement.js 檔案的一部分 (位於檔案的頂端)。AppMeasurement 程式庫在初始化時就會載入 Activity Map 模組。

除非更新到 AppMeasurement 的這個版本 (或更高版本)，否則無法收集 Activity Map 資料。

1. Download the latest AppMeasurement code (AppMeasurement_Javascript-1.6.zip) by going to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]** and [implement it](https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html).

   我們隨附一些[實作代碼範例](../../../../analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md#concept_EC27DA8A62F5411EBED51284CB7E1734)，協助您具體了解由於加入 Activity Map 模組而對代碼進行的變更。

1. 驗證實作:

   1. 當按下可點按元素，資料就會儲存至名為 s_sq 的 Cookie 中。
   1. 可以在追蹤呼叫的查詢字串中看到 Activity Map 資料。例如:

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. Break this report down by **[!UICONTROL Activity Map Link by Region]** to see the link/region for that page:  ![](assets/am_breakdown.png){width="400px"}

## 步驟 2.Enable Activity Map reports {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

首先，您必須在報表套裝層級啟用 Activity Map 報表。

1. Log in to Adobe Analytics and navigate to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin &gt; Report Suites &gt;[select report suite]&gt; Edit Settings &gt; Activity Map]** &gt; **[!UICONTROL Activity Map Reporting]** .
1. Activity Map 會將連結資料收集至 Activity Map 報表中。For the activation to happen, you must first activate the variables by clicking **[!UICONTROL Enable Activity Map Reports]**.

   此步驟會新增收集資料所需的所有 Analytics 維度。

1. 大約一小時後，查看「[Activity Map 頁面報表](/help/analyze/activity-map/activitymap-reporting-analytics.md)」，當中就會顯示使用者有點按連結的所有頁面。

## 步驟 3. Add users to Activity Map access group {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Click **[!UICONTROL Add Users to Group]**.

   這會將您帶往管理控制台中的群組管理頁面。

1. [新增使用者至此群組](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) 和 **[!UICONTROL 「儲存群組]**」。

1. This allow your Admin users to download Activity Map from  **[!UICONTROL Adobe Analytics]** &gt; **[!UICONTROL Tools]** &gt; **[!UICONTROL ActivityMap]** .

<note>
  If you want Non-Admin users to download Activity Map, you need to create a new user group that provides permission to 
 <span class="uicontrol"> Tools </span> &gt; 
 <span class="uicontrol"> Legacy ClickMap Installation </span>. 然後，您可以新增非管理員使用者至此群組。此層級的權限和Activity Map存取權將提供下載和使用工具的完整權限。 
</note>
