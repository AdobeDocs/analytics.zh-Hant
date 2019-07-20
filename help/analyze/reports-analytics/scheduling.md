---
description: 排程、下載和發佈報表的相關資訊。
seo-description: 排程、下載和發佈報表的相關資訊。
seo-title: 報表排程與分發
solution: Analytics
subtopic: 排程
title: 報表排程與分發
topic: Reports & Analytics
uuid: 1230b0f3-e026-4b83-b231-14d6 f75 a3836
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# 報表排程與分發

排程、下載和發佈報表的相關資訊。

## Report schedule and distribution {#concept_4EA333DFC7FD4E9CA086385A3DA10BE9}

排程、下載和發佈報表的相關資訊。

在 Adobe Analytics 應用程式內排程要傳送的報表時，您可以使用「排程和分送」工具檢視已自動傳送的檔案，以及修改或終止傳送。

由於處理機制和平台的差異，Adobe Analytics 中各種可供下載資料和排程報表，在單一請求中可處理的最大列數都有不同的限制。以下是每個項目的限制:

* Word、CSV、Excel、HTML 和 PDF: 與報表中的可見列數相同。依預設此限制為 50 列，但可提高至 200 列。劃分報表則嚴格限制為 50 列。
* 資料擷取: 50,000 列
* Data Warehouse: 無限制

請注意，以上是個別排程和下載報表的限制，控制面板則限制為小報表中可用空間的總量。

## 傳送報告 {#task_27642CD33D484FD0BF59EBD159EEF52C}

說明如何下載和透過電子郵件傳送各種格式之報告及計劃報告傳送的步驟。

<!-- 

t_send_report.xml

 -->

1. Run a report, then click **[!UICONTROL More]** &gt; **[!UICONTROL Send]**.
1. 指定傳送選項:

   | 選項 | 說明 |
   |--- |--- |
   | 格式 | 選取 PDF 或 HTML。 |
   | 傳送至 | 提供接收報告的電子郵件地址。 |
   | 主旨 | 電子郵件的主旨。 |
   | 排程 | 選取立即發送報告，或以不同間隔發送。 |

1. Click **[!UICONTROL Advanced Delivery Options]** to specify a delivery schedule.

   <table id="choicetable_2934E54FEE6E4D33B07EAC21F6DF628E"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> 選項 </th> 
   <th class="chdeschd"> 說明 </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>報告檔案名稱</strong></td> 
   <td class="chdesc stentry"> <p>指定報告的名稱。預設格式為 <code>&lt;套裝&gt; 的 &lt;報告名 &gt; - &lt;報告日期範圍&gt;</code>。 </p> <p>若要指定自訂名稱，請選取<span class="uicontrol">自訂</span>。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>報告格式</strong></td> 
   <td class="chdesc stentry"> <p>可讓您指定 PDF、CSV、Excel、HTML、Word 或行動格式以進行傳送。如果選取 CSV，則也可以指定 CSV 的編碼: </p> <p> 
      <ul id="ul_4A2EB8D9512246589994052CF482BFD7"> 
      <li id="li_A4FC4D795A9D4F92AAB187ACDFBA180D"> <p> <span class="uicontrol">Shift-JIS</span>: 日文字元編碼。 </p> </li> 
      <li id="li_405C7EC97F994D649A50F84466FADA3D"> <p> <span class="uicontrol">EUC-JP</span>: 擴展 Unix 編碼，主要用於日文、韓文和簡體中文。 </p> </li> 
      </ul> </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>報告內容</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol">表格的行數</span>: 指定要在傳送報告的表格中顯示的行數。 </p> <p> <span class="uicontrol">頁首和頁尾的語言</span>: 指定頁首和頁尾的語言。 </p> <p> <span class="uicontrol">備註</span>: 指定出現在報告起始處的文字。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>傳送數位簽名檔案</strong></td> 
   <td class="chdesc stentry"> <p>當您請求報告時 (例如書籤化報告或 Data Warehouse 請求)，可以請求一個資料簽名。Adobe 的數位簽名不限制存取資料的權限，但是數位簽名檔案 (.sig) 是用於驗證已傳送報告檔案的有效性。使用數位簽名，報告的接收方可以驗證檔案是否來自 Adobe 且沒有發生更改。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>報告目標</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol">電子郵件</span>: 可讓您設定電子郵件地址設定、主旨行以及附註。 </p> <p> <span class="uicontrol">FTP</span>: 可讓您設定 FTP 設定，包括主機、連接埠、目錄、使用者名稱以及密碼。 </p> </td> 
   </tr> 
   </table>

1. Click **[!UICONTROL Scheduling Options]**.

   <table id="choicetable_589A39087F4C497D8913364FFF0125B7"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> 選項 </th> 
   <th class="chdeschd"> 說明 </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>立即傳送報告</strong></td> 
   <td class="chdesc stentry"> <p>立即傳送報告。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>稍後計劃</strong></td> 
   <td class="chdesc stentry"> <p>顯示選項，供您指定時間範圍和傳送選項。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>報告時間範圍</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol">固定</span>: 防止日期隨時間流逝而前移。 </p> <p> <span class="uicontrol">滾動</span>: 允許日期隨時間流逝而前移。需要考慮的事項︰ </p> <p> 
      <ul id="ul_5CDCCBEFEB364800A428614183A0E6A1"> 
      <li id="li_37B8F32A9E3B4979B5239A58F0C5A71C"> <p>如果您選擇滾動起始日期和結束日期，並且選擇前一日的每日報告，每日您將收到前一日的電子郵件報告。 </p> </li> 
      <li id="li_83FFD2400C6A453783CDD9BB3B9BA3F9"> <p>如果您選擇固定起始日期，並滾動結束日期，您將於第一日收到前一日的報告。第二日您將收到前兩日的報告，而第三天將收到前三天的報告，以此類推。 </p> </li> 
      <li id="li_28F8552D699841BC942058247D39DBB9"> <p>如果您選擇固定起始和結束日期，每日您將收到指定日期相應的報告。 </p> </li> 
      <li id="li_A594A6E2A4044ED6AC0A80F88EB203B3"> <p>不能同時選擇滾動的開始日期和固定的結束日期。 </p> </li> 
      </ul> </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>傳送頻度</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol">每小時</span>: 以每小時、每兩小時或任何其他小時間隔傳送電子郵件。 </p> <p> <span class="uicontrol">每日</span>: 以每天、每兩天、每三天或任何其他天數間隔傳送電子郵件。另外也可以每週中傳送。 </p> <p> <span class="uicontrol">每週</span>: 以每週、每兩週、每三週或任何其他週數間隔傳送電子郵件。另可指定傳送的週日期。 </p> <p> <span class="uicontrol">每月</span>: 指定間隔的月份數，也可選擇在一個月內的哪一天傳送電子郵件，或在一個月內指定週的哪一天傳送電子郵件。 </p> <p> <span class="uicontrol">每年</span>: 指定在一年內的某一天傳送電子郵件，或者可以在一年中任意週內指定的某一天傳送。 </p> <p> <span class="uicontrol">每日時間</span>: 適用於選定報告套裝上所附的時區。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>結束傳送選項</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol">從不結束</span>: 指定永不結束。 </p> <p> <span class="uicontrol">&lt;值&gt; 次之後結束</span>: 指定發生幾次之後結束傳送。 </p> <p> <span class="uicontrol">結束於</span>: 可讓您指定特定的日期。 </p> <p>如果您希望在處理報告資料的同一個日期處理資料，報告則僅包含發送報告時資料庫裡所記錄的資料。處理完畢最長時需要 24 小時，因此，可能無法在傳送報告時使用完整的資料。要獲得完整資料，請始終將處理時間設為報表結束後的 24 小時。 </p> </td> 
   </tr> 
   </table>

## 列印報告 {#task_0F7CF6D6ED54462CAE4A793E271AF7E5}

說明如何列印報告的步驟。

<!-- 

t_reports_print.xml

 -->

1. 執行報告.
1. Click **[!UICONTROL More]** &gt; **[!UICONTROL Print]**.  ![](assets/print.png)

## 使用基本選項下載報表 {#task_43660107A1C9485D92981CD75B562577}

以 PDF、CSV、Excel 或「原始資料集匯出」格式下載特定報表的詳細資訊。

<!-- 

t_download-report.xml

 -->

1. 在 **Analytics** &gt; **[!UICONTROL 報表]**&#x200B;中，選取報表以檢視。
1. Click **[!UICONTROL Download]**.

   ![](assets/download_basic.png)

1. 選取想要的報表格式: 

   * **[!UICONTROL PDF]**: 指定該報表將下載為 Adobe PDF，因此您可與其他人共用報表，無論收件者的電腦系統為何都能開啟該檔案。
   * **[!UICONTROL CSV]**：指定報表將下載(逗號分隔 [!DNL .csv] 值格式)。
   * **[!UICONTROL Excel]**: 指定該報表將下載為 Microsoft Excel 格式，因此您可與其他人共用報表，讓別人在試算表程式中將其開啟。
   * **[!UICONTROL Word]**&#x200B;指定該報表將下載為 Microsoft Word 格式。
   >[!NOTE]
   >
   >如果您使用其中一種原始匯出格式下載報表，而頁面名稱空白，Adobe Analytics可能沒有足夠的時間處理資料。稍後下載報表。

## 管理計劃報告 {#task_C17677C543454FF2B06D10EA5652DFBC}

與管理計劃報告相關的資訊。

<!-- 

t_schedule_manage.xml

 -->

在[!UICONTROL 計劃報告管理器]中，您可以編輯和刪除周期性報告的傳送。您可以建立傳送計劃，透過電子郵件或 FTP 將報告傳送至指定位址。您可以設定這些計劃以特定時間間隔或無限制自動傳送報告，或停止傳送週期性報告。

[!UICONTROL 計劃報告管理器]會顯示特定使用者建立的項目。若應用程式內的使用者帳戶已被停用，所有已安排的傳送將停止。

1. To access the manager, click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Scheduled Reports]**.

## 共用報告連結 {#task_9711DDE9E140451B8C914EC5513E21EC}

描述如何透過產生報告連結 (URL) 以傳送給另一個使用者來共用報告的步驟。

<!-- 

t_reports_share_link.xml

 -->

當收件者按一下連結時，系統即要求登入憑證 (公司名稱、使用者名稱和密碼)。登入後，收件者顯示報告由最初使用者產生。套用標準權限限制。

**要共用報告連結**

1. 執行報告.
1. Click **[!UICONTROL More]** &gt; **[!UICONTROL Link to This Report]**.

## 取消訂閱排程報表 {#concept_6B48360F935740B6851BA85D32DEF637}

您可以取消訂閱排程報表。您不會再收到報表，即使將您的使用者名稱重新新增回排程報表亦同。

<!-- 

t_schedule_unsubscribe.xml

 -->

>[!IMPORTANT]
>
>為了讓您再次收到報表，必須建立新的排程。

若要取消訂閱排程報表:

1. 找出具有您想取消訂閱之報表連結的電子郵件。

   ![](assets/unsubscribe-email.png)

1. Click the **[!UICONTROL click here]** link next to **[!UICONTROL To cancel automatic delivery of this report]**.

1. 確認您要取消報表傳送。

   >[!NOTE]
   >
   >無論您是報表排程者或報表收件者，此工作流程都相同。

取消訂閱報表並不會取消排程的報表。

若要取消排程報表，請導覽至「計劃管理員」並按一下報表名稱旁的紅色 X。[更多...](../../analyze/reports-analytics/scheduling.md#task_C17677C543454FF2B06D10EA5652DFBC)
