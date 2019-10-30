---
description: 說明Analytics管理員要完成以啟用[!DNL Activity Map]連結收集和使用者下載的步驟。
seo-description: 說明Analytics管理員要完成以啟用[!DNL Activity Map]連結收集和使用者下載的步驟。
seo-title: 啟用[!DNL Activity Map]
solution: Analytics
title: 啟用[!DNL Activity Map]
topic: Activity Map
uuid: 3043319-d0e6-4977-951a-4492b356e1f2
translation-type: tm+mt
source-git-commit: ae18932eda59c059e2aa635cc30f233b88840031

---


# 啟用 [!DNL Activity Map]{#enable-activity-map}

Explains the steps the Analytics Admin needs to complete to enable [!DNL Activity Map] link collection and user download.

## 步驟 1.將 AppMeasurement (Javascript) 代碼更新至 v1.6 (或更高版本) {#section_5D1586289DF2489289B1B6C1C80C300D}

The [!DNL Activity Map] module is part of the AppMeasurement.js file (located at the top of the file). The AppMeasurement library will load the [!DNL Activity Map] module when instantiated.

[!DNL Activity Map]除非更新到 AppMeasurement 的這個版本 (或更高版本)，否則無法收集 資料。

1. Download the latest AppMeasurement code (AppMeasurement_Javascript-1.6.zip) by going to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]** and [implement it](https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html).

   我們隨附一些[實作代碼範例](../../../../analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md#concept_EC27DA8A62F5411EBED51284CB7E1734)，協助您具體了解由於加入 模組而對代碼進行的變更。[!DNL Activity Map]

1. 驗證實作:

   1. 當按下可點按元素，資料就會儲存至名為 s_sq 的 Cookie 中。
   1. The [!DNL Activity Map] data can be seen in the query-string on the tracking call. 例如:

      ```
      …&c.&a.&[!DNL Activity Map].&link=My%20Link&region=My%20Region&page=My%20Page&.[!DNL Activity Map]&.a&.c&...
      ```

1. Break this report down by **[!UICONTROL [!DNL Activity Map]Link by Region]** to see the link/region for that page:  ![](assets/am_breakdown.png){width="400px"}

## 步驟 2.啟用報 [!DNL Activity Map] 告 {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

First, you need to enable [!DNL Activity Map] reports at a report-suite level.

1. Log in to Adobe Analytics and navigate to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin &gt; Report Suites &gt;[select report suite]&gt; Edit Settings &gt;[!DNL Activity Map]]** &gt; **[!UICONTROL [!DNL Activity Map]Reporting]** .
1. [!DNL Activity Map] 在報表中收集連結 [!DNL Activity Map] 資料。 For the activation to happen, you must first activate the variables by clicking **[!UICONTROL Enable[!DNL Activity Map]Reports]**.

   此步驟會新增收集資料所需的所有 Analytics 維度。

1. After about an hour, check the [[!DNL Activity Map] Page report](/help/analyze/activity-map/activitymap-reporting-analytics.md), which shows all the pages where users clicked on a link.

## 步驟 3.Add users to [!DNL Activity Map] access group {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Click **[!UICONTROL Add Users to Group]**.

   這會將您帶往管理控制台中的群組管理頁面。

1. [新增使用者至此群組](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) ，並 **[!UICONTROL 儲存群組]**。

1. This allow your Admin users to download [!DNL Activity Map] from  **[!UICONTROL Adobe Analytics]** &gt; **[!UICONTROL Tools]** &gt; **[!UICONTROL ActivityMap]** .

> [!NOTE] 如果您想要讓非管理員使用者下載 [!DNL Activity Map]，請建立新的使用者群組，以提供「工具」和「舊版ClickMap安裝」的權限。 此權限層級與「存取」結 [!DNL Activity Map] 合，提供下載和使用工具的權限。
