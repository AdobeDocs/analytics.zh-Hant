---
description: Data Connectors 整合精靈會引導您完成 Data Connectors 整合程序。
title: 執行 Data Connectors 整合精靈
uuid: 714417f7-c1df-4e61-a07f-d319f6581c9c
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 執行 Data Connectors 整合精靈{#running-the-data-connectors-integration-wizard}

Data Connectors 整合精靈會引導您完成 Data Connectors 整合程序。

若要設定整合：

1. 登入 Experience Cloud。
1. 在 Adobe Analytics 首頁上，按一下風車星形或工具列上的 Data Connectors™ 圖示。
1. 在 Data Connectors 頁面上，選取您要設定整合的報表套裝。

   >[!NOTE]
   >
   >請務必從 Data Connectors 頁面左上角的&#x200B;**「報表套裝」**&#x200B;下拉式清單中選取所需的報表套裝。

1. 按一下 Data Connectors UI 左側&#x200B;**「合作夥伴清單」**&#x200B;上方的&#x200B;**「字母順序」**&#x200B;標籤，然後找到 **Datran** 圖示。
1. 將 **Datran** 圖示拖曳至 Adobe Analytics 報表套裝裡空的外掛程式插槽，以啟動「Data Connectors 整合精靈」。

1. 檢閱「Datran 整合」簡介頁面上的文字，接著選取核取方塊以接受與整合相關聯的費用，然後按一下&#x200B;**「下一步」**。

   此頁面會提供整合的概述，以及實用的相關資訊連結。此整合會同時產生 Adobe 和 Datran 的相關費用。請連絡這兩個組織的適當銷售代表，並確定您瞭解費用結構。
1. 在 Data Connectors 整合精靈的每個頁面上提供所需資訊，如下表所述：

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" valign="top" align="left" class="entry"> <p><b>精靈頁面 #</b> </p> </th> 
   <th colname="col2" class="entry"> <p><b>欄位</b> </p> </th> 
   <th colname="col3" class="entry"> <p><b>說明</b> </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2" valign="top" align="left"> <p>整合名稱 </p> </td> 
   <td colname="col3"> <p>指定 Data Connectors 在報表套裝的「作用中的整合清單」中顯示的整合名稱。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>整合電子郵件地址 </p> </td> 
   <td colname="col3"> <p>指定要接收與這項整合相關之所有通知的電子郵件地址，然後按一下<b>「下一步」</b>以繼續執行精靈的步驟 2。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>帳戶 ID </p> </td> 
   <td colname="col3"> <p>指定您的 Datran 帳戶 ID (Datran 指派給您的組織的唯一識別碼)，然後按一下<b>「下一步」</b>以繼續執行精靈的步驟 3。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>訊息 ID </p> </td> 
   <td colname="col3"> <p>識別用於追蹤電子郵件訊息 ID 的 Adobe Analytics eVar。 </p> <p>訊息 ID 會用於行銷/再促銷活動。訊息 ID 通常稱為「追蹤代碼」。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>收件者 ID </p> </td> 
   <td colname="col3"> <p>識別用於追蹤電子郵件收件者 ID 的 Adobe Analytics eVar。 </p> <p>收件者 ID 會用於行銷/再促銷活動。訊息 ID 通常稱為「訪客代碼」。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>「接受」核取方塊 </p> </td> 
   <td colname="col3"> <p>檢閱「接受」核取方塊旁顯示的資訊： </p> <p><i>我瞭解，透過啟用「收件者 ID」追蹤功能，可追蹤我們的網站訪客的個人識別資訊。這隱含隱私權問題，需要我的組織實施適當的程序，例如向我們的網站訪客提供通知並授予同意。</i> </p> <p>如果您同意接受聲明，請選取核取方塊，然後按一下<b>「下一步」</b>以繼續執行精靈的步驟 4。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>用戶端定義的報表套裝層級區段 </p> </td> 
   <td colname="col3"> <p>這項整合會建立合作夥伴定義的區段，顯示在整合精靈的「整合區段」頁面左側。 </p> <p>此外，您可以選取要納入整合中的現有報表套裝層級區段。 </p> <p>在頁面右側選取所需的區段，然後按一下<b>「下一步」</b>以繼續執行精靈的步驟 5。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>已點按 </p> </td> 
   <td colname="col3"> <p>指定 Adobe Analytics 事件，用於儲存從電子郵件系統匯入的電子郵件「已點按」資料。 </p> <p>「已點按」事件可讓您查看已點按電子郵件訊息的訪客數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>已開啟 </p> </td> 
   <td colname="col3"> <p>指定 Adobe Analytics 事件，用於儲存從電子郵件系統匯入的電子郵件「已開啟」資料。 </p> <p>「已開啟」事件可讓您查看已開啟電子郵件訊息的訪客數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>已傳送 </p> </td> 
   <td colname="col3"> <p>指定 Adobe Analytics 事件，用於儲存從電子郵件系統匯入的電子郵件「已傳送」資料。 </p> <p>「已點按」事件可讓您查看已傳送的電子郵件訊息數目。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>總跳出數 </p> </td> 
   <td colname="col3"> <p>指定 Adobe Analytics 事件，用於儲存從電子郵件系統匯入的電子郵件「總跳出數」資料。 </p> <p>「總跳出數」事件可讓您查看因發生傳遞問題而未傳遞給收件者的電子郵件訊息數目。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>已取消訂閱 </p> </td> 
   <td colname="col3"> <p>指定 Adobe Analytics 事件，用於儲存從電子郵件系統匯入的電子郵件「已取消訂閱」資料。 </p> <p>「已取消訂閱」事件可讓您查看在開啟電子郵件訊息後按一下「取消訂閱」連結以選擇退出貴組織未來的電子郵件訊息的訪客人數。 </p> <p>按一下「下一步」以繼續執行精靈的步驟 6。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>資料收集：JavaScript 外掛程式 </p> </td> 
   <td colname="col3"> <p>如果您想要使用外掛程式做為此整合的收集模型，請選取<b>「JavaScript 外掛程式」</b>，然後按一下<b>「下一步」</b>以繼續執行精靈的步驟 7。 </p> <p> <p>注意：自動化解決方案是預設的選取項目。 </p> </p> <p>請聯絡您的 Adobe 顧問，以取得用於這項整合的 JavaScript 外掛程式副本。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>資料收集：自動化解決方案 </p> </td> 
   <td colname="col3"> <p>如果您想要針對這項整合使用自動化收集模型，請選取<b>「自動化解決方案」</b>，然後指定用於這項整合的唯一識別碼。 </p> <p> <p>注意：自動化解決方案是預設的選取項目。 </p> </p> <p>如果您選取此選項，請指定用於這項整合的唯一識別碼： </p> <p><b>訊息 ID 查詢字串參數：</b>此值代表您的電子郵件合作夥伴附加至登陸頁面 URL 的訊息 ID。 </p> <p><b>收件者 ID 查詢字串參數：</b>此值代表您的電子郵件合作夥伴附加至登陸頁面 URL 的收件者 ID。 </p> <p>按一下<b>「下一步」</b>以繼續執行精靈的步驟 7。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>整合摘要 </p> </td> 
   <td colname="col3"> <p>按一下每個類別旁的加號 (+)，然後按一下<b>「儲存」</b>以繼續執行精靈的步驟 8，以便驗證整合參數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>整合完成 </p> </td> 
   <td colname="col3"> <p>按一下<b>「完成」</b>以完成整合。 </p> <p><b>重要：</b>在您按一下<b>「完成」</b>之前，Adobe Analytics 不會儲存整合設定。 </p> </td> 
  </tr> 
 </tbody> 
</table>
