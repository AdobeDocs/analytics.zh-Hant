---
description: Data Connectors 整合精靈會引導您完成 Data Connectors 整合程序。
title: Silverpop 整合
uuid: dc5e6a09-3238-412d-9980-4a105ce14819
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Silverpop 整合{#silverpop-integration}

Data Connectors 整合精靈會引導您完成 Data Connectors 整合程序。

若要設定整合：

1. 在 Adobe Experience Cloud 中，從產品下拉式清單中選取 Data Connectors™。
1. 按一下&#x200B;**[!UICONTROL 新增]**，並在&#x200B;**[!UICONTROL 顯示]**&#x200B;下拉式清單中選取&#x200B;**[!UICONTROL 依名稱]**。
1. 找到 **Silverpop Engage 2.0** 圖示，然後將其拖曳至 Analytics 報表套裝中的空外掛程式槽，即可啟動 Data Connectors整合精靈。
1. 在 Silverpop 整合簡介頁面上檢閱文字，然後選取核取方塊以接受與整合相關的費用。
1. 選取您要用於此整合的報表套裝。
1. 提供易記名稱以識別此整合，然後按一下&#x200B;**[!UICONTROL 「建立並設定此整合」]**。

   此頁面會提供整合的概述，以及實用的相關資訊連結。此整合會同時產生 Adobe 和 Silverpop 的相關費用。請連絡這兩個組織的適當銷售代表，並確定您瞭解費用結構。
1. 在 Data Connectors 整合精靈的每個頁面上提供所需資訊，如下表所述：

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col2" class="entry"> <p> <b>欄位</b> </p> </th> 
   <th colname="col03" valign="top" align="left" class="entry"> <p> <b>設定區域</b> </p> </th> 
   <th colname="col3" class="entry"> <p> <b>說明</b> </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>整合名稱 </p> </td> 
   <td colname="col03"> <p>(1) 整合設定 </p> </td> 
   <td colname="col3"> <p>指定 Data Connectors 在報表套裝的「作用中的整合清單」中顯示的整合名稱。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>下載檔案 </p> </td> 
   <td colname="col03"> <p>(2) 變數對應 </p> </td> 
   <td colname="col3"> <p> 用於檔案下載再行銷。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> 電子郵件地址 </p> </td> 
   <td colname="col03"> <p>(2) 變數對應 </p> </td> 
   <td colname="col3"> <p>用於向沒有已知 Silverpop ID 的訪客進行再行銷。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>帳戶 ID </p> </td> 
   <td colname="col03"> <p>(2) 變數對應 </p> </td> 
   <td colname="col3"> <p>指定您的 Silverpop 帳戶 ID (由 Silverpop 指派給貴組織的不重複識別碼)，然後按<b>「下一步」</b>，繼續精靈的步驟 3。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>表單名稱 </p> </td> 
   <td colname="col03"> <p>(2) 變數對應 </p> </td> 
   <td colname="col3"> <p>用於放棄表單再行銷。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>郵件 ID </p> </td> 
   <td colname="col03"> <p>(2) 變數對應 </p> </td> 
   <td colname="col3"> <p>(必填) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Silverpop ID </p> </td> 
   <td colname="col03"> <p>(2) 變數對應 </p> </td> 
   <td colname="col3"> <p>(必填) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> 彈回數 </p> </td> 
   <td colname="col03"> <p>(2) 變數對應 </p> </td> 
   <td colname="col3"> <p>(必要) 指定 Analytics 事件，用於儲存從電子郵件系統匯入的電子郵件「總跳出數」資料。 </p> <p>「總跳出數」事件可讓您查看因發生傳遞問題而未傳遞給收件者的電子郵件訊息數目。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>已點按 </p> </td> 
   <td colname="col03"> <p>(2) 變數對應 </p> </td> 
   <td colname="col3"> <p>(必要) 指定 Analytics 事件，用於儲存從電子郵件系統匯入的電子郵件「已點按」資料。 </p> <p>「已點按」事件可讓您查看已點按電子郵件訊息的訪客數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> 檔案已下載 </td> 
   <td colname="col03"> <p>(2) 變數對應 </p> </td> 
   <td colname="col3"> <p> 用於檔案下載再行銷。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> 表單已完成 </td> 
   <td colname="col03"> <p>(2) 變數對應 </p> </td> 
   <td colname="col3"> <p>用於放棄表單再行銷。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> 表單已開始 </td> 
   <td colname="col03"> <p>(2) 變數對應 </p> </td> 
   <td colname="col3"> <p>用於放棄表單再行銷。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>已開啟 </p> </td> 
   <td colname="col03"> <p>(2) 變數對應 </p> </td> 
   <td colname="col3"> <p>(必要) 指定 Analytics 事件，用於儲存從電子郵件系統匯入的電子郵件「已開啟」資料。 </p> <p>「已開啟」事件可讓您查看已開啟電子郵件訊息的訪客數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>已傳送 </p> </td> 
   <td colname="col03"> <p>(2) 變數對應 </p> </td> 
   <td colname="col3"> <p>(必要) 指定 Analytics 事件，用於儲存從電子郵件系統匯入的電子郵件「已傳送」資料。 </p> <p>「已傳送」事件可讓您查看已傳送的電子郵件數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>已取消訂閱 </p> </td> 
   <td colname="col03"> <p>(2) 變數對應 </p> </td> 
   <td colname="col3"> <p>(必要) 指定 Analytics 事件，用於儲存從電子郵件系統匯入的電子郵件「已取消訂閱」資料。 </p> <p>「已取消訂閱」事件可讓您查看在開啟電子郵件訊息後按一下「取消訂閱」連結以選擇退出貴組織未來的電子郵件訊息的訪客人數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>區段 </p> </td> 
   <td colname="col03"> <p>(3) 資料設定 </p> </td> 
   <td colname="col3"> <p>這項整合會建立顯示在「合作夥伴區段」部分中的合作夥伴定義區段。 </p> <p>此外，您可以選取要納入整合中的現有報表套裝層級區段。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>存取要求 </p> </td> 
   <td colname="col03"> <p>(3) 資料設定 </p> </td> 
   <td colname="col3"> <p> (必要) 啟用 <span class="uicontrol"> 允許此整合以下載產品資料</span>。 </p> <p>選用：允許此整合以下載收入、訂單數和件數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>資料彙集 </p> </td> 
   <td colname="col03"> <p>(3) 資料設定 </p> </td> 
   <td colname="col3"> <p>如果您想要使用 s_code.js 外掛程式做為此整合的收集模式，請選取 <b>JavaScript 外掛程式</b> (請參閱 <a href="../silverpop-overview/silverpop-analytics-code.md">Analytics 外掛程式代碼</a>)。 </p> <p>如果您想要針對這項整合使用自動化收集模型，請選取<b>「自動化解決方案」</b>，然後指定用於這項整合的唯一識別碼。 </p> <p>如果您選取此選項，請指定用於這項整合的唯一識別碼： </p> <p> <b>訊息 ID 查詢字串參數：</b>此值代表您的電子郵件合作夥伴附加至登陸頁面 URL 的訊息 ID。 </p> <p> <b>收件者 ID 查詢字串參數：</b>此值代表您的電子郵件合作夥伴附加至登陸頁面 URL 的收件者 ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>產生控制面板和書籤 </p> </td> 
   <td colname="col03"> <p>(4) 報表設定 </p> </td> 
   <td colname="col3"> <p>針對整合自動產生控制面板和書籤。 </p> </td> 
  </tr> 
 </tbody> 
</table>

