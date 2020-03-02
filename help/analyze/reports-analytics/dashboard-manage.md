---
description: 使用「控制面板管理員」可以複製、共用、封存和排程控制面板的傳送。
subtopic: Dashboards
title: 控制面板管理員
topic: Reports and analytics
uuid: 380fd148-2ed9-43bf-9d42-46e373e788e4
translation-type: tm+mt
source-git-commit: 92eaaeafdd587febcfe7fe60f696baca0691b4bc

---


# 控制面板管理員

使用「控制面板管理員」可以複製、共用、封存和排程控制面板的傳送。

>[!IMPORTANT]
>
>「控制面板管理員」的最佳使用作法是任何使用者的控制面板都不超過 300 個。此外也請注意，管理員會載入下方所有共用控制面板，因此，請在使用共用控制面板時多加留意。

## 控制面板管理員

使用「控制面板管理員」可以複製、共用、封存和排程控制面板的傳送。

按一下 **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**.

| 元素 | 說明 |
|--- |--- |
| 共用 | 顯示控制面板是否為共用。 |
| 已排程 | 可讓您計劃控制面板的傳送。 |
| 檢視封存 | 此功能已不再提供。 |
| 推送至使用者 | 可讓您共用控制面板。 |
| 管理 | 可讓您編輯、複製及刪除控制面板。 |

## 管理共用控制面板

說明如何使用共用控制面板管理選項的步驟。

1. Go to **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**.
1. Under [!UICONTROL Shared Dashboards], locate the shared dashboard (or legacy dashboard) you want to manage and choose one or more of the following options:

<table id="choicetable_857E0E816D63404683D4E24DC8D7FC69"> 
 <thead class="chhead sthead"> 
  <th class="choptionhd"> 選項 </th> 
  <th class="chdeschd"> 說明 </th> 
 </thead> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>檢視封存</strong></td> 
  <td class="chdesc stentry"> 此功能已不再提供。 </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Dashboard Player</strong></td> 
  <td class="chdesc stentry"> <p>SiteCatalyst 14 伺服器將不再回應 Dashboard Player 的資料請求。目前顯示在 Dashboard Player 中的任何控制面板都能透過「Report &amp; Analytics」的標準介面存取，或重新建立為即時控制面板。即時控制面板是專門為持續顯示而設計，包含全螢幕模式，可供顯示在電視或其他大型螢幕裝置上。 </p> <p>使用者需執行的動作：您需要停止使用 Dashboard Player。 </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>副本抄送我</strong></td> 
  <td class="chdesc stentry"> 將副本新增至控制面板清單，名稱與原始事件相同。不過，您無法看見控制面板擁有者進行的任何更新/變更。複製舊式控制面板會開啟空白的控制面板，讓您在其中新增舊式內容。 <p>重要：如果您控制面板的共用使用者在控制面板中看不到您所做的變更，請檢查控制面板管理員，查看是否使用者選擇了「<span class="uicontrol">副本抄送我</span>」選項。如果選擇了此選項，他們將看不到您所做的更新/變更。若要查看所有更新/變更，共用使用者必須在控制面板管理員中選取「<span class="uicontrol">功能表中</span>」選項。 </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>功能表中</strong></td> 
  <td class="chdesc stentry"> 讓您檢視控制面板擁有者所進行的變更/更新。 </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>取消共用</strong></td> 
  <td class="chdesc stentry"> 從共用控制面板的清單移除此控制面板。 </td> 
 </tr> 
</table>

## 遷移舊式控制面板

現有的舊式控制面板仍會繼續執行，您也可繼續編輯、下載和排程這些控制面板，但是不再能夠建立新的舊式控制面板。我們強烈建議您將現有的舊式控制面板升級至較新的控制面板格式。

> [!NOTE]日後請考慮使用 [Analysis Workspace 專案](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/)及其下載和排程功能。

複製舊控制面板時，系統會開啟舊控制面板以供編輯，您可新增舊內容或新內容。複製舊控制面板時，其原型會保留在舊控制面板的清單中。

> [!NOTE]若將舊式內容新增至控制面板，系統會根據最新的控制面板功能建立控制面板。不過，舊式小報告可能會包含以舊版資料平台為基礎的資料。

**若要遷移 14.x 版舊式控制面板**

1. 按一下 **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Manage Dashboards]**.
1. 在列的 [!UICONTROL Manage] 下方，單 [!UICONTROL Legacy Dashboards]擊 **[!UICONTROL Copy to New Dashboard]**。

   複製的控制面板會在控制面板配置編輯器中開啟。

   請參閱[編輯控制面板和小報表資料](/help/analyze/reports-analytics/dashboard.md)。

## 共用控制面板

說明管理員如何將控制面板與多個使用者共用 (或推送) 至多個使用者的步驟。When you push dashboards to users, the dashboards become available in user&#39;s [!UICONTROL Shared Dashboards] menu.

1. 在中， [!UICONTROL Dashboard Manager]找到控制面板，然後啟用 **[!UICONTROL Shared]**。
1. 按一下 **[!UICONTROL Push To Users]**.  ![](assets/push.png)

1. 在頁面 [!UICONTROL Push Dashboard] 上，選擇目標用戶或按一下 **[!UICONTROL Check All]**。
1. 按一下 **[!UICONTROL Save]**.

If shared users of your dashboard cannot see changes you made in the dashboard, check your Dashboard Manager to see if the users have chosen the **[!UICONTROL Copy Me]** option. 如果選擇了此選項，他們將看不到您所做的更新/變更。To see all the changes/updates, shared users need to select the **[!UICONTROL On Menu]** option in the Dashboard Manager.

## 計劃報告的傳送

In the [!UICONTROL Dashboard Manager], you can see whether a dashboard is scheduled for delivery, and edit the schedule. 控制面板傳送選項與報告傳送選項相同。

1. 開啟一個控制面板。
1. 按一下 **[!UICONTROL More]** > **[!UICONTROL Send]**.

   如需詳細資訊，請參閱[排程和分送](/help/analyze/reports-analytics/scheduling.md)。

## 封存控制面板

> [!NOTE]2020 年 1 月起不再提供此功能。

說明如何將任何傳送的控制面板封存為 PDF 檔案的步驟。系統會將封存檔儲存兩年，或直到達到封存報告的 4 GB 上限為止 (以先達到的為準)。

1. 開啟一個控制面板。
1. 按一下 **[!UICONTROL More]** > **[!UICONTROL Send]**.
1. 在群組 [!UICONTROL Email Report] 中，啟用 **[!UICONTROL Archive]**。
1. Specify delivery options, then click **[!UICONTROL Send]**.

   您可以在「控制面板管理員」中檢視已封存的控制面板。或者，開啟控制面板，然後按一 **[!UICONTROL More]** 下> **[!UICONTROL View Archive]**。
