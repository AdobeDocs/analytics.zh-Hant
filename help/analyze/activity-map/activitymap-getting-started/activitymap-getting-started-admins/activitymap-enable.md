---
description: 說明若想啟用 Activity Map 連結收集和使用者下載，Analytics 管理員需要完成的步驟。
title: 啟用 Activity Map
topic: Activity map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 啟用 Activity Map{#enable-activity-map}

說明若想啟用 Activity Map 連結收集和使用者下載，Analytics 管理員需要完成的步驟。

## 步驟 1.將 AppMeasurement (Javascript) 代碼更新至 v1.6 (或更高版本) {#section_5D1586289DF2489289B1B6C1C80C300D}

Activity Map 模組屬於 AppMeasurement.js 檔案的一部分 (位於檔案的頂端)。AppMeasurement 程式庫在初始化時就會載入 Activity Map 模組。

除非更新到 AppMeasurement 的這個版本 (或更高版本)，否則無法收集 Activity Map 資料。

1. 請前往&#x200B;**[!UICONTROL 「分析]** > **[!UICONTROL 管理員]** > **[!UICONTROL 代碼管理器」]**&#x200B;下載最新的 AppMeasurement 代碼，然後[實作代碼](https://marketing.adobe.com/resources/help/zh_TW/sc/implement/js_implementation.html)。

   我們隨附一些[實作代碼範例](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md)，協助您具體了解由於加入 Activity Map 模組而對代碼進行的變更。

1. 驗證實作：

   1. 當按下可點按元素，資料就會儲存至名為 s_sq 的 Cookie 中。
   1. 可以在追蹤呼叫的查詢字串中看到 Activity Map 資料。例如：

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. 依照&#x200B;**[!UICONTROL 「各地區的 Activity Map 連結」]**&#x200B;劃分此報表，查看該頁面的連結/地區：![](assets/am_breakdown.png){width=&quot;400px&quot;}

## 步驟 2.啟用 Activity Map 報表 {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

首先，您必須在報表套裝層級啟用 Activity Map 報表。

1. 登入 Adobe Analytics，並依序導覽至&#x200B;**[!UICONTROL 「Analytics]** > **[!UICONTROL 管理員 > 報表套裝 >[選取報表套裝]> 編輯設定 > Activity Map]**>**[!UICONTROL  Activity Map 報表」]**。
1. Activity Map 會將連結資料收集至 Activity Map 報表中。您必須先按一下&#x200B;**[!UICONTROL 「啟用 Activity Map 報表」]**&#x200B;啟動變數，才能真正啟動。

   此步驟會新增收集資料所需的所有 Analytics 維度。

1. 大約一小時後，查看[「Activity Map 頁面報表」](/help/analyze/activity-map/activitymap-reporting-analytics.md)，當中就會顯示使用者有點按連結的所有頁面。

## 步驟 3.新增使用者至 Activity Map 存取群組 {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. 按一下&#x200B;**[!UICONTROL 「新增使用者至群組」]**。

   這會將您帶往管理控制台中的群組管理頁面。

1. [新增使用者到此群組](https://marketing.adobe.com/resources/help/zh_TW/reference/groups.html)，然後&#x200B;**[!UICONTROL 儲存群組]**。

1. 如此可讓您的管理員使用者從&#x200B;**[!UICONTROL 「Adobe Analytics]** > **[!UICONTROL 工具]** > **[!UICONTROL Activity Map」]**&#x200B;下載 Activity Map。

> [!NOTE] 如果您希望非管理員使用者下載 Activity Map，請建立新的使用者群組，以提供「工具」和「舊版 ClickMap 安裝程式」的權限。此權限層級與「Activity Map存取」結合，提供下載和使用工具的權限。
