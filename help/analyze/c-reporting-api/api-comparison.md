---
description: Analytics報表API的比較表。 提供支援檔案的連結。
title: Analytics 報表 API 比較
uuid: fa533a8e-33c0-42f4-a294-cabee0258c8f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Analytics 報表 API 比較

Analytics報表API的比較表。 提供支援檔案的連結。

>[!NOTE] 針對延遲情形，Analytics for Target (A4T) 可在相同點擊上結合 Analytics 和 Target 資料，以執行整合式報告。由於Analytics和Target呼叫發生在不同的時間，因此會在進行任何處理之前儲存點擊，以便從兩個解決方案收集資料。 此程式會 **為所有查核點增加** 7-10分鐘的延遲。

<table id="table_7AF4FD678D494063ADF459B3CBC3EF3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API類型 </th> 
   <th colname="col2" class="entry"> 完全處理 </th> 
   <th colname="col3" class="entry"> 即時 </th> 
   <th colname="col4" class="entry"> Livestream </th> 
   <th colname="col5" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>說明</b> </td> 
   <td colname="col2"> 所有Analytics介面都提供已完全處理且已完成的資料。 </td> 
   <td colname="col3"> 收集後數秒內可用的部分處理、有限量度。 </td> 
   <td colname="col4"> 部分處理的點擊資料可在收集後數秒內取得。 </td> 
   <td colname="col5"> 完全處理、已完成的資料，用於提取大型資料匯出。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://marketing.adobe.com/resources/help/en_US/analytics/whitepapers/analytics-data-availability.pdf"  > 延遲性</a> </p> </td> 
   <td colname="col2"> 30-90分鐘 </td> 
   <td colname="col3"> *秒-10分鐘 </td> 
   <td colname="col4"> 秒-10分鐘 </td> 
   <td colname="col5"> 90 分鐘 + </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>處理完成</b> </td> 
   <td colname="col2"> 全部 </td> 
   <td colname="col3"> 部分 </td> 
   <td colname="col4"> 部分 </td> 
   <td colname="col5"> 全部 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="https://marketing.adobe.com/resources/help/zh_TW/reference/"  > 報告介面</a> </td> 
   <td colname="col2"> 報告與分析、報告建立工具、API </td> 
   <td colname="col3"> 報告與分析、報告建立工具、API中的即時報告 </td> 
   <td colname="col4"> 僅限API </td> 
   <td colname="col5"> 資料倉庫與API </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>資料詳細程度</b> </td> 
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
   <td colname="col5"> 是（但僅與資料倉庫相容的區段） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Analytics SKU</b> </td> 
   <td colname="col2"> 標準+ </td> 
   <td colname="col3"> 標準+ </td> 
   <td colname="col4"> Premium Complete或Predictive Intelligence </td> 
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

* [Adobe/IO](https://www.adobe.io/) —— 將Adobe技術整合至應用程式所需之技術檔案與工具的完整來源。
* [資料工作台查詢API](https://marketing.adobe.com/developer/documentation/data-workbench-query-api/c-ins-qry-api)

