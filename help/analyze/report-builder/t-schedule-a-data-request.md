---
description: 您可以排程報表以按照定義的時間和檔案格式傳送。
seo-description: 您可以排程報表以按照定義的時間和檔案格式傳送。
seo-title: 排程資料請求
solution: Analytics
title: 排程資料請求
topic: Report Builder
uuid: f6d8c90f-e185-4d60-8035-f20 f74 bfcd89
translation-type: tm+mt
source-git-commit: 6a70b32b576cc7b5b6a6f0037d98e35b3f8c1426

---


# 排程資料請求

您可以排程報表以按照定義的時間和檔案格式傳送。

**排程資料請求**

1. 產生及儲存報表。
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]**.

   [!UICONTROL 「排程報表」]索引標籤會總結您建立的所有任務和剩餘的任務數量。
1. On the **[!UICONTROL Scheduled Reports]** tab, click **[!UICONTROL New]**.
1. 「基本排程精靈」顯示: 

   ![](assets/simple-schedule-wizard.png)

1. 在[!UICONTROL 「基本排程精靈」]中，設定下列選項:

* **選擇報表**：報表的名稱。對於新的排程報表，系統會將作用中活頁簿的名稱填入此欄位。

<table id="table_6D5B1B832EB0451293F1902E2A1D1068"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>選擇報表 </p> </td> 
   <td colname="col2"> <p>報表的名稱。對於新的排程報表，系統會將作用中活頁簿的名稱填入此欄位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>選擇 </p> </td> 
   <td colname="col2"> <p>顯示「<span class="wintitle">選擇報表</span>」頁面。您可以從伺服器 (儲存舊排程活頁簿的位置) 選擇報表，或從本機電腦選擇。如果您從本機磁碟選擇 <span class="filepath">.xls</span> 格式的活頁簿，系統會將檔案轉換為 <span class="filepath">.xlsx</span>。在轉換過程中，系統會在 Excel 開啟檔案並使其成為作用中狀態。如果排程報表的選擇活頁簿檔案名稱與目前在 Excel 中開啟的活頁簿檔案名稱相同，系統會選擇本機檔案而非先前上傳的檔案。如果您從排程庫選擇報表，系統會在伺服器中建立活頁簿的副本並更新檔案名稱 (加上 1)，而新建立的排程報表則會使用複製的活頁簿。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自訂 </p> </td> 
   <td colname="col2"> <p>可讓您自訂日期格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>收件者 </p> </td> 
   <td colname="col2"> <p>顯示 Outlook 通訊錄 (若有的話)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>傳送至: 電子郵件 </p> </td> 
   <td colname="col2"> <p>報表的電子郵件收件者。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>傳送至: 發佈清單 </p> </td> 
   <td colname="col2"> <p>顯示此公司的可用分送清單。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Power BI </p> </td> 
   <td colname="col2"> <p>如需詳細資訊，請參閱<a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_BA137EA92A46483F83BB5C1C40FBA002" format="dita" scope="local">將活頁簿發佈至 Microsoft Power BI</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>主旨 </p> </td> 
   <td colname="col2"> <p>使用者定義的說明。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>排程 </p> </td> 
   <td colname="col2"> <p> 可讓您指定傳送報表的時間。(立即、每小時、每日、每週、每月及每年。) </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Advanced Delivery Options]** to configure file and publishing options:

<table id="table_1BA8A5600DE94A33B83B096E69CE15F3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>「排程」</b>索引標籤 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>傳送時間 </p> </td> 
   <td colname="col2"> <p>可讓您立即排程報表或排程稍後的傳送時間。傳送時間與在電腦中指定的時區相關。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>週期模式 </p> </td> 
   <td colname="col2"> <p>根據您的選擇傳送報表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>週期範圍 </p> </td> 
   <td colname="col2"> <p>可讓您指定接收報表的開始時間和停止時間。 </p> <p> <p>附註: 將報表排程定於任何目前期間 (週、月、季或年) 的第一天只會傳回第一天的資料。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>「檔案選項」</b>索引標籤 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>檔案格式 </p> </td> 
   <td colname="col2"> <p>可讓您選擇傳送格式，包括 Excel 2007 (<span class="filepath">.xlsx</span>) 或 2003 (<span class="filepath">.xls</span>)、<span class="filepath">.pdf</span>、<span class="filepath">.csv、</span><span class="filepath">.mht</span>、<span class="filepath"> .txt</span> 及<span class="filepath"> .xml</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 檔案目標 </p> </td> 
   <td colname="col2"> <p> 指定電子郵件或 FTP。頁面中的選項會隨著您的選擇而改變。對於 FTP，您必須確認可從外部連接主機。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>發佈清單 </p> </td> 
   <td colname="col2"> <p> 如果將排程報表傳送給多份發佈清單，報表會針對每份清單執行一次。指派給發佈清單的報表套裝軟體會取代變動報表套裝軟體。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>檔案內容語言 </p> </td> 
   <td colname="col2"> <p>指定首頁所要使用的語言。您可以選擇中文 (簡體或繁體)、德文、法文、日文、韓文、葡萄牙文 (巴西) 或西班牙文。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>「發佈選項」</b>索引標籤 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>發佈至 Power BI </p> </td> 
   <td colname="col2"> 
    <ul id="ul_40697E4FB2CE4F34B857FBF153D6D6D5"> 
     <li id="li_023E4750814D415EBC899269C9EA5D46"><a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_BA137EA92A46483F83BB5C1C40FBA002" format="dita" scope="local"> 將活頁簿發佈至 Power BI</a> </li> 
     <li id="li_9B684BE22AF94ABC903405EE83951A80"><a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_E48148793E794169B766C73995897B9F" format="dita" scope="local"> 以 Power BI 資料集發佈所有 Report Builder 請求</a> </li> 
     <li id="li_7B0BD285BC1749D1B2C65759CA97877B"><a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_6F8422B90D3F4F7EB5D4C97BFFA807AD" format="dita" scope="local"> 以 Power BI 資料集發佈所有格式化表格</a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>將此 Power BI 報表標記為 </p> </td> 
   <td colname="col2"> <p>標記詳細資料 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL OK]**, then click **[!UICONTROL Exit]**.

   Report Builder 會在[「排程任務管理員」](../../analyze/report-builder/r-arb-scheduled-reports.md#section_69306B8D833F4DF7BBFA53753B0E6C31)中顯示排程報表。
