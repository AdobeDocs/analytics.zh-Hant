---
description: 分析報告 API 的比較表。提供支援文件的連結。
title: Analytics 報表 API 比較
uuid: fa533a8e-33c0-42f4-a294-cabee0258c8f
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Analytics 報表 API 比較

分析報告 API 的比較表。提供支援文件的連結。

> [!NOTE] 針對延遲情形，Analytics for Target (A4T) 可在相同點擊上結合 Analytics 和 Target 資料，以執行整合式報告。因為 Analytics 和 Target 呼叫發生在不同的時間，會在任何處理發生之前儲存點擊，以從兩個解決方案收集資料。此處理會對所有查核點新增&#x200B;**額外的 7-10 分鐘**&#x200B;延遲。

<table id="table_7AF4FD678D494063ADF459B3CBC3EF3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API 類型 </th> 
   <th colname="col2" class="entry"> 完整處理 </th> 
   <th colname="col3" class="entry"> 即時 </th> 
   <th colname="col4" class="entry"> Livestream </th> 
   <th colname="col5" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>說明</b> </td> 
   <td colname="col2"> 可在所有 Analytics 介面中使用的完整處理、已完成的資料。 </td> 
   <td colname="col3"> 收集資料後幾秒鐘內即可使用的部份處理、有限的量度。 </td> 
   <td colname="col4"> 收集資料後幾秒鐘內即可使用的部份處理的點擊資料。 </td> 
   <td colname="col5"> 用於提取大型資料匯出的完整處理、已完成的資料。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://marketing.adobe.com/resources/help/en_US/analytics/whitepapers/analytics-data-availability.pdf"  > 延遲性</a> </p> </td> 
   <td colname="col2"> 30-90 分鐘 </td> 
   <td colname="col3"> * 秒 -10 分鐘 </td> 
   <td colname="col4"> 秒 -10 分鐘 </td> 
   <td colname="col5"> 90 分鐘 + </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>處理完成</b> </td> 
   <td colname="col2"> 全螢幕 </td> 
   <td colname="col3"> 部份 </td> 
   <td colname="col4"> 部份 </td> 
   <td colname="col5"> 全螢幕 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="https://marketing.adobe.com/resources/help/zh_TW/reference/"  > 報告介面</a> </td> 
   <td colname="col2"> Reports &amp; Analytics、Report Builder、API </td> 
   <td colname="col3"> Reports &amp; Analytics、Report Builder、API 中的即時報告 </td> 
   <td colname="col4"> 僅 API </td> 
   <td colname="col5"> Data Warehouse 與 API </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>資料粒度</b> </td> 
   <td colname="col2"> 摘要 </td> 
   <td colname="col3"> 摘要 </td> 
   <td colname="col4"> 點擊層級 </td> 
   <td colname="col5"> 摘要 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>訪客資料處理</b> </td> 
   <td colname="col2"> 是 </td> 
   <td colname="col3"> 無 </td> 
   <td colname="col4"> 無 </td> 
   <td colname="col5"> 是 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>支援區段</b> </td> 
   <td colname="col2"> 是 </td> 
   <td colname="col3"> 無 </td> 
   <td colname="col4"> 無 </td> 
   <td colname="col5"> 是 (但僅限 Data Warehouse 相容區段) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Analytics SKU</b> </td> 
   <td colname="col2"> 標準+ </td> 
   <td colname="col3"> 標準+ </td> 
   <td colname="col4"> Premium Complete 或 Predictive Intelligence </td> 
   <td colname="col5"> 標準+ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>文件</b> </td> 
   <td colname="col2"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/get-started%E2%80%8B"  > 網站服務</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/real-time"  > 即時報告</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-live-stream/overview-1%E2%80%8B"  > Livestream 概述</a> </p> </td> 
   <td colname="col5"> <p><a href="https://marketing.adobe.com/resources/help/zh_TW/reference/data_warehouse.html"  > Data Warehouse</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**相關說明**

* [Adobe/IO](https://www.adobe.io/) - 將 Adobe 技術整合至您的應用程式所需的技術文件和工具的廣泛來源。
* [Data Workbench 查詢 API](https://marketing.adobe.com/developer/documentation/data-workbench-query-api/c-ins-qry-api)

