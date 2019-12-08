---
description: 您可以排程報表以按照定義的時間和檔案格式傳送。
title: 排程資料請求
topic: Report builder
uuid: f6d8c90f-e185-4d60-8035-f20f74bfcd89
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 排程活頁簿

您可以排程活頁簿、指定進階傳送選項、指定收件者，以及檢視排程歷史記錄。 進階傳送選項可讓您設定要在特定時間或間隔傳送的活頁簿。 您也可以指定傳送活頁簿的檔案格式。

For example, you can schedule workbooks to be delivered immediately or on a recurring schedule, and specify the file format in [!DNL Advanced Delivery Options]. 活頁簿上傳的檔案大小限制為5 MB。

Additionally, after you create a workbook schedule in Report Builder, you can view and edit the schedule in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]**. (請參閱「Reports &amp; Analytics」說明中的[「報表排程與分發」](/help/analyze/reports-analytics/scheduling.md))。

> [!NOTE] 您必須已安裝Excel 2007或相容性套件，才能排程活頁簿。 每份Report Builder授權最多可有10個排程活頁簿。 不過，您可以從其他授權扣除，以建立更多活頁簿。To do so, go to **[!UICONTROL Admin]** &gt; **[!UICONTROL Company Settings]** &gt; **[!UICONTROL Report Builder Reports]**. 已排程（或已上傳至「活頁簿庫」）且超過28個月未觸及（更新、取代）的活頁簿將會刪除。

> [!NOTE] 使用者輸入的「傳送時間」/「每日時間」會指定活頁簿應開始處理的時間，而非實際傳送的時間。 實際傳送活頁簿的時間主要取決於處理所花的時間（複雜和大型活頁簿的處理時間比較簡單的活頁簿）。 例如，如果活頁簿需要15分鐘的處理時間，則實際傳送時間至少會超過最初指定的「傳送時間」/「日期時間」15分鐘。
>此外，還有許多其他因素可能會進一步增加實際傳送活頁簿之前的延遲：
>
> * **同時運行許多同類型的不同計畫** ，可能會使系統過載。 排程系統僅允許同時執行少數(5-10)種任何類型的活頁簿，因此當一次排程超過5-10個活頁簿時，有些活頁簿必須排好行，才能開始處理。 排程公司活頁簿的時間是一天或一小時，而非同時排程，以緩解此問題。
> * 除了特定活頁簿類型外，如果公司同時排程超過15-20種任何類型的活頁簿，活頁簿也會排在行中（跨所有不同的活頁簿類型） ****。 這可借由錯亂的排程時間來減輕，而非同時執行多次。
> * **排程器所仰賴的下游服務** ，也會影響活頁簿的傳送。 例如，如果您是獨立使用API來執行活頁簿並填寫API請求佇列，則排程的活頁簿在您競爭該資源時傳送速度可能會很慢。
> * **報表套裝延遲** （資料收集延遲）也可能會延遲某些排程的活頁簿。


## 排程活頁簿

1. 產生並儲存活頁簿。
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]**.

   [!UICONTROL 「排程報表」]索引標籤會總結您建立的所有任務和剩餘的任務數量。
1. On the **[!UICONTROL Scheduled Reports]** tab, click **[!UICONTROL New]**.
1. 「基本排程精靈」顯示: 

   ![](assets/simple-schedule-wizard.png)

1. 在[!UICONTROL 「基本排程精靈」]中，設定下列選項:

| 欄位 | 說明 |
|--- |--- |
| 選擇報表 | 活頁簿的名稱。 對於新的排程報表，系統會將作用中活頁簿的名稱填入此欄位。 |
| 選擇 | 顯示「選擇報表」頁面。您可以從伺服器 (儲存舊排程活頁簿的位置) 選擇報表，或從本機電腦選擇。如果您從本機磁碟選擇 .xls 格式的活頁簿，系統會將檔案轉換為 .xlsx。在轉換過程中，系統會在 Excel 開啟檔案並使其成為作用中狀態。如果排程報表的選擇活頁簿檔案名稱與目前在 Excel 中開啟的活頁簿檔案名稱相同，系統會選擇本機檔案而非先前上傳的檔案。如果您從排程儲存庫選取報表，則會在伺服器上建立活頁簿副本，其檔案名稱會更新為1。新建立的排程報表會使用複製的活頁簿。 |
| 自訂 | 可讓您自訂日期格式。 |
| 結束日期 | 顯示 Outlook 通訊錄 (若有的話)。 |
| 傳送至: 電子郵件 | 活頁簿的電子郵件收件者。 |
| 傳送至: 發佈清單 | 顯示此公司的可用分送清單。 |
| Power BI | 如需詳細資訊，請參閱[將活頁簿發佈至 Microsoft Power BI](/help/analyze/report-builder/c-publish-power-bi/integration-power-bi.md)。 |
| 主旨 | 使用者定義的說明。 |
| 排程 | 可讓您指定傳送活頁簿的時間。 (立即、每小時、每日、每週、每月及每年。) |

## 進階傳送選項

1. Click **[!UICONTROL Advanced Delivery Options]** to configure file and publishing options:

| 欄位 | 說明 |
|--- |--- |
| **「排程」索引標籤** |  |
| 傳送時間 | 可讓您立即排程活頁簿或排程稍後的時間。 傳送時間與在電腦中指定的時區相關。 |
| 週期模式 | 根據您的選擇傳送活頁簿。 |
| 週期範圍 | 可讓您指定何時開始和停止接收活頁簿。   注意： 排程活頁簿時間至任何目前期間（周、月、季或年）的第一天時，只會傳回第一天的資料。 |
| **「檔案選項」索引標籤** |  |
| 檔案格式 | 可讓您選擇傳送格式，包括 Excel 2007 (.xlsx) 或 2003 (.xls)、.pdf、.csv、.mht、 .txt 及 .xml。 |
| 檔案目標 | 指定電子郵件或 FTP。頁面中的選項會隨著您的選擇而改變。對於 FTP，您必須確認可從外部連接主機。 |
| 發佈清單 | 如果您將排程的活頁簿傳送至多個發佈清單，活頁簿會針對每個清單執行一次。 指派給發佈清單的報表套裝軟體會取代變動報表套裝軟體。 |
| 檔案內容語言 | 指定首頁所要使用的語言。您可以選擇中文 (簡體或繁體)、德文、法文、日文、韓文、葡萄牙文 (巴西) 或西班牙文。 |
| **「發佈選項」索引標籤** |  |
| 發佈至 Power BI | <ul><li>將活頁簿發佈至 Power BI</li><li>以 Power BI 資料集發佈所有 Report Builder 請求</li><li>以 Power BI 資料集發佈所有格式化表格</li></ul> |
| 將此 Power BI 報表標記為 | 標記詳細資料 |

1. Click **[!UICONTROL OK]**, then click **[!UICONTROL Exit]**.

   Report Builder displays the scheduled workbook in the [Scheduled Task Manager](/help/analyze/report-builder/r-arb-scheduled-reports.md).

