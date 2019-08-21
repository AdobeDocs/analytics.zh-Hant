---
description: 您可以排程報表以按照定義的時間和檔案格式傳送。
seo-description: 您可以排程報表以按照定義的時間和檔案格式傳送。
seo-title: 排程資料請求
solution: Analytics
title: 排程資料請求
topic: Report Builder
uuid: f6d8c90f-e185-4d60-8035-f20 f74 bfcd89
translation-type: tm+mt
source-git-commit: 62937df0a763f6b9b34389d968c5641056b47aa8

---


# 排程活頁簿

您可以排程活頁簿、指定進階傳送選項、指定收件者，以及檢視排程歷史記錄。進階傳送選項可讓您設定要在特定時間或間隔傳送的活頁簿。您也可以指定要傳送活頁簿的檔案格式。

For example, you can schedule workbooks to be delivered immediately or on a recurring schedule, and specify the file format in [!DNL Advanced Delivery Options]. 活頁簿上傳的檔案大小限制為MB。

Additionally, after you create a workbook schedule in Report Builder, you can view and edit the schedule in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]**. (請參閱「Reports &amp; Analytics」說明中的[「報表排程與分發」](/help/analyze/reports-analytics/scheduling.md))。

>[!NOTE]
>
>您必須安裝Excel2007或相容性套件才能排程活頁簿。每個報告建立工具授權最多可有10個排程活頁簿。不過，您可以從其他授權扣除，以建立更多活頁簿。To do so, go to **[!UICONTROL Admin]** &gt; **[!UICONTROL Company Settings]** &gt; **[!UICONTROL Report Builder Reports]**. 將刪除已排程(或上傳至活頁簿庫)且尚未在28個月內遭到接觸點(更新、取代)的活頁簿。

>[!NOTE]
>
>使用者輸入的「傳送時間」/「每日時間」指定活頁簿應該開始處理的時間，而不是實際傳遞的時間。將活頁簿傳送的實際時間主要取決於處理時間(複雜和大型活頁簿需要花費較長時間處理較簡單的活頁簿)。例如，如果活頁簿需要15分鐘處理，則實際傳送時間將至少超過原本指定的「傳送時間」/「每日時間」的15分鐘。
>此外，還有一些其他因素可進一步提高在實際遞送活頁簿之前的延遲：
>
> * **同時執行相同類型的許多不同排程會** 使系統超載。「排程」系統只允許任何一種類型的活頁簿並行執行，因此，當有超過5-10的活頁簿全部排定時，有些人需要在線上等候其他活頁簿完成，才能開始處理。這個問題可以借由在一天或多小時的交錯時間內排程公司活頁簿來減輕，而不是同時進行。
> * 除了特定活頁簿類型外，如果公司一 **次擁有超過15-20種活頁簿類型(所有不同活頁簿類型)，活頁簿**&#x200B;也會同時等候。這可以透過排程時間來減輕，而不是同時執行許多工作。
> * **排程器依賴於下游服務** 的問題也會影響傳送活頁簿。例如，如果您獨立使用API來執行活頁簿並填寫API請求佇列，則您的排程活頁簿可能會在您競爭該資源時緩慢地傳遞。
> * **報表套裝延遲** (資料收集延遲)也可以延遲某些排程活頁簿。


**排程活頁簿**

1. 產生並儲存活頁簿。
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]**.

   [!UICONTROL 「排程報表」]索引標籤會總結您建立的所有任務和剩餘的任務數量。
1. On the **[!UICONTROL Scheduled Reports]** tab, click **[!UICONTROL New]**.
1. 「基本排程精靈」顯示: 

   ![](assets/simple-schedule-wizard.png)

1. 在[!UICONTROL 「基本排程精靈」]中，設定下列選項:

* **選擇報表**：活頁簿的名稱。對於新排程的活頁簿，此欄位會填入作用中活頁簿名稱。

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
   <td colname="col2"> <p>顯示「<span class="wintitle">選擇報表</span>」頁面。您可以從伺服器 (儲存舊排程活頁簿的位置) 選擇報表，或從本機電腦選擇。如果您從本機磁碟選擇 <span class="filepath">.xls</span> 格式的活頁簿，系統會將檔案轉換為 <span class="filepath">.xlsx</span>。在轉換過程中，系統會在 Excel 開啟檔案並使其成為作用中狀態。如果排程報表的選擇活頁簿檔案名稱與目前在 Excel 中開啟的活頁簿檔案名稱相同，系統會選擇本機檔案而非先前上傳的檔案。如果您從排程存放庫選取報表，則會在伺服器上建立活頁簿副本，檔案名稱會以1更新。新建立的排程報表會使用複製的活頁簿。 </p> </td> 
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
   <td colname="col2"> <p>活頁簿的電子郵件收件者。 </p> </td> 
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
   <td colname="col2"> <p> 可讓您指定傳送活頁簿的時機。(立即、每小時、每日、每週、每月及每年。) </p> </td> 
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
   <td colname="col2"> <p>可讓您立即排程活頁簿或稍後排程活頁簿。傳送時間與在電腦中指定的時區相關。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>週期模式 </p> </td> 
   <td colname="col2"> <p>根據您的選擇傳送活頁簿。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>週期範圍 </p> </td> 
   <td colname="col2"> <p>可讓您指定何時開始和停止接收活頁簿。 </p> <p> <p>注意：在任何目前時段(周、月、季或年)的第一天排程活頁簿，只會傳回第一天的資料。 </p> </p> </td> 
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
   <td colname="col2"> <p> 如果您將排程活頁簿傳送到多份發佈清單，活頁簿會針對每份清單執行一次。指派給發佈清單的報表套裝軟體會取代變動報表套裝軟體。 </p> </td> 
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

   Report Builder displays the scheduled workbook in the [Scheduled Task Manager](../../analyze/report-builder/r-arb-scheduled-reports.md#section_69306B8D833F4DF7BBFA53753B0E6C31).

