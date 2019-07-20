---
description: 'null'
seo-description: 'null'
seo-title: Adobe Campaign報告
title: Adobe Campaign報告
uuid: 0919ae9f-84eb-43a5-8282-6cd6dec63dc1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Adobe Campaign報告

如需如何設定整合的詳細資訊，請前往 [Adobe Campaign 文件](https://helpx.adobe.com/campaign/standard/integrating/using/about-campaign-analytics-integration.html)。

Adobe Analytics 與 Adobe Campaign 之間的整合

* 讓您從 Adobe Campaign Standard 共用您的 KPI (關鍵績效指標) 資料至 Adobe Analytics。
* 使用 Adobe Analytics 參數充實追蹤公式。
* Adds a new report under  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]** &gt; **[!UICONTROL Adobe Campaign.]**
* 增加 5 個全新 Adobe Campaign 分類。
* 增加 10 個全新 Adobe Campaign 量度。
* 增加 6 個全新 Adobe Campaign 維度。
* 每 15 分鐘同步資料至 Analytics。

## 步驟 1. 啟用 Adobe Campaign 報告功能 {#section_C685EF10505045708A6536BB13F6CD58}

若要在 Analytics 檢視 Campaign 資料，必須先啟用 Campaign 報表。

1. Navigate to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL <select report suite>]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Adobe Campaign]** &gt; **[!UICONTROL Adobe Campaign Reporting]** .
1. Click **[!UICONTROL Enable Campaign Reporting]**.

   ![](assets/enable-campaign.png)

## 步驟 2.檢視 Adobe Campaign 報表 {#section_9C18A29F3CC54BD4AC5EA96417F17B33}

The integration between Adobe Campaign Standard and Adobe Analytics adds the following report under  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]**

<table id="table_3627F40DC90646A7B5E217A88B6FD630"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 報告 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Campaign 執行的傳送 ID </p> </td> 
   <td colname="col2"> <p>顯示從 Adobe Campaign 匯入之由 Adobe Campaign 傳送的電子郵件的相關資料。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 步驟 3. 使用 Adobe Campaign 分類 {#section_74A28AF3F4CA4091943789DE4D8B2B63}

**[!UICONTROL 「分析]** &gt; **[!UICONTROL 管理]** &gt; **[!UICONTROL 報表套裝]** &gt; **[!UICONTROL <select report suite>]** &gt; **[!UICONTROL 編輯設定]** &gt; **[!UICONTROL Adobe Campaign]** &gt; **[!UICONTROL Adobe Campaign分類」]**

在您針對 Adobe Campaign 啟用報表套裝後，以下分類即可使用:

* 傳送 ID (您在 Campaign 所見的「內部傳送名稱」)
* 傳送標籤((促銷活動中的傳送-個別傳送/週期性傳送/交易傳送)
* Campaign ID (您在 Campaign 所見的「內部行銷活動名稱」)
* Campaign 標籤 (Adobe Campaign 中的行銷活動)
* 已執行的傳送標籤 (個別已執行傳送清單)

## Adobe Analytics 中可用的 Adobe Campaign 維度和量度 {#section_F33385C9660644AF84172EC39601469B}

以下&#x200B;**量度**&#x200B;可透過 Adobe Analytics 報表套裝中的 Campaign 使用:

* Adobe Campaign 已傳送
* Adobe Campaign 已打開
* Adobe Campaign 已點擊
* Adobe Campaign 已處理
* Adobe Campaign 已傳送
* Adobe Campaign 不重複打開
* Adobe Campaign 不重複點擊
* Adobe Campaign 取消訂閱
* Adobe Campaign 彈回數總計
* Adobe Campaign 執行的傳送 ID 例項

以下&#x200B;**維度**&#x200B;可透過 Adobe Analytics 報表套裝中的 Campaign 使用:

| 維度名稱 | 定義 |
|--- |--- |
| 行銷活動 ID | 在活動期間傳送的 KPI 之所有行銷活動的 ID |
| 行銷活動標籤 | 行銷活動 ID 標籤 |
| 傳送 ID | 在活動期間傳送的 KPI 之所有傳送 ID亦包括循環傳送和交易傳送的主傳送 ID。範例: 已排程循環傳送 DM1，而 DM2、DM3、DM4 和 DM5 是該循環傳送的子傳送。「傳送 ID」會顯示所有傳送的結果，從 DM1 至 DM5 都會顯示。 |
| 傳送標籤 | 傳送 ID 標籤 |
| 已執行傳送ID | 僅限已執行傳送的 ID。沒有循環/交易主傳送的 ID。範例: 已排程循環傳送 DM1，而 DM2、DM3、DM4 和 DM5 是該循環傳送的子傳送。已執行傳送 ID 會顯示從 DM2 到 DM5，實際已執行的傳送之所有傳送結果。 |
| 已執行傳送標籤 | 已執行傳送 ID 標籤 |
