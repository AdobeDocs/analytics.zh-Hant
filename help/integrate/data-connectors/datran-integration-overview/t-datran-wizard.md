---
description: Data Connectors整合精靈會引導您進行資料連接器整合程序。
seo-description: Data Connectors整合精靈會引導您進行資料連接器整合程序。
seo-title: 執行Data Connectors整合精靈
title: 執行Data Connectors整合精靈
uuid: 714417f7-c1 df-4e61 f-d319 f6581 c9 c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d55b23a5baf5be1d7afb708cc6ef94851eac3e77

---


# Running the Data Connectors Integration Wizard{#running-the-data-connectors-integration-wizard}

Data Connectors整合精靈會引導您進行資料連接器整合程序。

若要設定整合：

1. 登入 Marketing Cloud。
1. 在Adobe Analytics首頁上，按一下紙風車或工具列上的Data Connectors™圖示。
1. 在「資料連接器」頁面上，選取您要設定整合的報表套裝。

   >[!NOTE]
   >
   >Make sure that you select the desired report suite from the **Report Suite** drop-down list in the upper-left corner of the Data Connectors page.

1. Click the **Alphabetical** tab at the top of the **Partner List** on the left side of the Data Connectors UI, then locate the **Datran** icon.
1. Drag the **Datran** icon to an empty plug-in slot in your Adobe Analytics report suite to launch the Data Connectors Integration Wizard.

1. On the Datran Integration introduction page, review the text, then select the check box to accept the fees associated with the integration, then click **Next**.

   此頁面會提供整合的概述，以及實用的相關資訊連結。此整合有Adobe和Datran的相關費用。請連絡這兩個組織的適當銷售代表，並確定您瞭解費用結構。
1. 在「資料連接器整合精靈」的每個頁面上，提供必要資訊，如下表所述：

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" valign="top" align="left" class="entry"> <p><b>WEEWE PAGE#</b> </p> </th> 
   <th colname="col2" class="entry"> <p><b>Field</b> </p> </th> 
   <th colname="col3" class="entry"> <p><b>說明</b> </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2" valign="top" align="left"> <p>整合名稱 </p> </td> 
   <td colname="col3"> <p>指定資料連接器在報表套裝的作用中整合清單中顯示的整合名稱。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>整合電子郵件地址 </p> </td> 
   <td colname="col3"> <p>Specify the email address that receives all notifications related to this integration, then click <b>Next</b> to proceed to Step 2 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>帳戶ID </p> </td> 
   <td colname="col3"> <p>Specify your Datran Account ID (the unique identifier assigned to your organization by Datran), then click <b>Next</b> to proceed to Step 3 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>訊息ID </p> </td> 
   <td colname="col3"> <p>識別用於追蹤電子郵件訊息ID的Adobe Analytics eVar。 </p> <p>訊息ID用於行銷/再行銷促銷活動。訊息ID通常稱為「追蹤代碼」。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col3"> <p>識別用於追蹤電子郵件收件者ID的Adobe Analytics eVar。 </p> <p>「收件者ID」用於行銷/再行銷促銷活動。訊息ID通常稱為「訪客代碼」。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>接受核取方塊 </p> </td> 
   <td colname="col3"> <p>檢閱「接受」核取方塊旁顯示的資訊： </p> <p><i>我瞭解，透過啓用「收件者ID」追蹤，此功能可能會追蹤我們網站訪客的個人識別資訊。This has privacy implications requiring the implementation of appropriate procedures by my organization, such as providing notice to, and consent of, our site visitors. </i> </p> <p>If you agree to the acceptance statement, select the check box, then click <b>Next</b> to proceed to Step 4 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>用戶端定義的報表套裝層級區段 </p> </td> 
   <td colname="col3"> <p>此整合會建立合作夥伴定義區段，顯示在整合精靈的「整合區段」頁面左側。 </p> <p>此外，您還可以選取要納入整合的現有報表套裝層級區段。 </p> <p>Select the desired segments on the right side of the page, then click <b>Next</b> to proceed to Step 5 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>點按 </p> </td> 
   <td colname="col3"> <p>指定Adobe Analytics事件，以儲存從電子郵件系統匯入的點按資料。 </p> <p>點擊的事件可讓您查看點擊電子郵件訊息的訪客人數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>已開啓 </p> </td> 
   <td colname="col3"> <p>指定儲存從電子郵件系統匯入之開啓資料的Adobe Analytics事件。 </p> <p>「開啓的事件」可讓您查看開啓電子郵件訊息的訪客人數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>已傳送 </p> </td> 
   <td colname="col3"> <p>指定儲存從電子郵件系統匯入之傳送資料的Adobe Analytics事件。 </p> <p>點擊事件可讓您查看傳送的電子郵件訊息數目。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>彈回數總計 </p> </td> 
   <td colname="col3"> <p>指定Adobe Analytics事件，儲存從電子郵件系統匯入的電子郵件總彈回數。 </p> <p>「總計」事件可讓您查看由於傳送問題而未傳送給收件者的電子郵件訊息數量。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>取消訂閱 </p> </td> 
   <td colname="col3"> <p>指定儲存從電子郵件系統匯入之取消訂閱資料的Adobe Analytics事件。 </p> <p>「取消訂閱」事件可讓您查看開啓電子郵件訊息但按一下「取消訂閱」連結，以取消組織未來電子郵件訊息的訪客數量。 </p> <p>按一下「下一步」繼續精靈的步驟6。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>資料收集：JavaScript外掛程式 </p> </td> 
   <td colname="col3"> <p>Select <b>JavaScript Plug-in</b> if you want to use the plug-in as the collection model for this integration, then click <b>Next</b> to proceed to Step 7 of the Wizard. </p> <p> <p>注意：「自動化解決方案」是預設選擇。 </p> </p> <p>請連絡您的Adobe顧問，取得用於此整合的JavaScript外掛程式副本。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>資料收集：自動化解決方案 </p> </td> 
   <td colname="col3"> <p>Select <b>Automated Solution</b> if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. </p> <p> <p>注意：「自動化解決方案」是預設選擇。 </p> </p> <p>如果您選取此選項，請指定用於此整合的唯一識別碼： </p> <p><b>訊息ID查詢字串參數：</b>此值代表電子郵件合作夥伴附加至著陸頁面URL的訊息ID。 </p> <p><b>收件者ID查詢字串參數：</b> 此值代表電子郵件合作夥伴附加至著陸頁面URL的收件者ID。 </p> <p>Click <b>Next</b> to proceed to Step 7 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>整合摘要 </p> </td> 
   <td colname="col3"> <p>Verify the integration parameters by clicking the plus sign (+) next to each category, then click <b>Save</b> to proceed to Step 8 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>整合完成 </p> </td> 
   <td colname="col3"> <p>Click <b>Finish</b> to complete the integration. </p> <p><b>重要：</b> Adobe Analytics在您按一下 <b>「完成」</b>後，才會儲存整合設定。 </p> </td> 
  </tr> 
 </tbody> 
</table>

