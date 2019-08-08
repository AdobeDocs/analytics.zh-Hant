---
description: Data Connectors整合精靈會引導您進行資料連接器整合程序。
seo-description: Data Connectors整合精靈會引導您進行資料連接器整合程序。
seo-title: Silverpop整合
title: Silverpop整合
uuid: dc5e6a09-3238-412d-9980-4a105ce14819
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Silverpop整合{#silverpop-integration}

Data Connectors整合精靈會引導您進行資料連接器整合程序。

若要設定整合：

1. 在Adobe Marketing Cloud中，從產品下拉式清單中選取「資料連接器™」。
1. 按一下 **[!UICONTROL 「新增新]** 功能」，然後在 ******[!UICONTROL 「顯示]** 」下拉式清單中選取「依名稱」。
1. 尋找 **Silverpop Engagement2.0** 圖示並將它拖曳至Analytics報表套裝中的空白外掛程式槽，以啓動Data Connectors整合精靈。
1. 在Silverpop整合簡介頁面上，檢閱文字，然後選取核取方塊以接受與整合相關聯的費用。
1. 選取您要用於此整合的報表套裝。
1. 提供好記名稱以識別此整合，然後按一下 **[!UICONTROL 「建立並設定此整合]**」。

   此頁面會提供整合的概述，以及實用的相關資訊連結。與此整合相關的Adobe和Silverpop費用都有。請連絡這兩個組織的適當銷售代表，並確定您瞭解費用結構。
1. 在「資料連接器整合精靈」的每個頁面上，提供必要資訊，如下表所述：

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
   <td colname="col03"> <p>(1)整合設定 </p> </td> 
   <td colname="col3"> <p>指定資料連接器在報表套裝的作用中整合清單中顯示的整合名稱。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>下載檔案 </p> </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p> 用於檔案下載再行銷。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> Email Address </p> </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p>用於將訪客轉換為無已知Silverpop ID的訪客。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>帳戶ID </p> </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p>指定Silverpop帳戶ID(Silverpop指派給您組織的唯一識別碼)，然後按一下 <b>「下一步」</b> 繼續精靈的步驟3。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>表單名稱 </p> </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p>用於表單放棄再行銷。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Mailing ID </p> </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p>(必填) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Silverpop ID </p> </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p>(必填) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> 彈回數 </p> </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p>(必要)指定Analytics事件，以儲存從電子郵件系統匯入的電子郵件總彈回數。 </p> <p>「總計」事件可讓您查看由於傳送問題而未傳送給收件者的電子郵件訊息數量。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>點按 </p> </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p>(必要)指定Analytics事件，以儲存從電子郵件系統匯入的點按資料。 </p> <p>點擊的事件可讓您查看點擊電子郵件訊息的訪客人數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> 檔案已下載 </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p> 用於檔案下載再行銷。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> 表單填寫 </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p>用於表單放棄再行銷。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> 表單已開始 </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p>用於表單放棄再行銷。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>已開啓 </p> </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p>(必要)指定Analytics事件，以儲存從電子郵件系統匯入的已開啓資料。 </p> <p>「開啓的事件」可讓您查看開啓電子郵件訊息的訪客人數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>已傳送 </p> </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p>(必要)指定Analytics事件，以儲存從電子郵件系統匯入的傳送資料。 </p> <p>「傳送」事件可讓您查看傳送的電子郵件訊息數目。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>取消訂閱 </p> </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p>(必要)指定儲存從電子郵件系統匯入之「取消訂閱」資料的Analytics事件。 </p> <p>「取消訂閱」事件可讓您查看開啓電子郵件訊息但按一下「取消訂閱」連結，以取消組織未來電子郵件訊息的訪客數量。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>區段 </p> </td> 
   <td colname="col03"> <p>(3)資料設定 </p> </td> 
   <td colname="col3"> <p>此整合會建立合作夥伴定義區段中顯示的合作夥伴定義區段。 </p> <p>此外，您還可以選取要納入整合的現有報表套裝層級區段。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>存取要求 </p> </td> 
   <td colname="col03"> <p>(3)資料設定 </p> </td> 
   <td colname="col3"> <p> (必要)啓用 <span class="uicontrol"> 此整合以下載產品資料</span>。 </p> <p>可選：允許此項整合以下載收入、訂購和件數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>資料彙集 </p> </td> 
   <td colname="col03"> <p>(3)資料設定 </p> </td> 
   <td colname="col3"> <p><b></b> 如果您要使用s_ code. js外掛程式作為此整合的系列模型(請參閱 <a href="../silverpop-overview/silverpop-analytics-code.md#concept-28e7c834a6804a949aa9306f8896b36e" format="dita" scope="local"> Analytics外掛程式程式碼</a>)，請選取JavaScript外掛程式。 </p> <p>如果您想要針對此整合使用自動化收集模型，請選取 <b>「自動化解決方案</b> 」，然後指定用於此整合的唯一識別碼。 </p> <p>如果您選取此選項，請指定用於此整合的唯一識別碼： </p> <p> <b>訊息ID查詢字串參數：</b>此值代表電子郵件合作夥伴附加至著陸頁面URL的訊息ID。 </p> <p> <b>收件者ID查詢字串參數：</b> 此值代表電子郵件合作夥伴附加至著陸頁面URL的收件者ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>控制面板和書簽產生 </p> </td> 
   <td colname="col03"> <p>(4)報表設定 </p> </td> 
   <td colname="col3"> <p>自動產生整合的控制面板和書簽。 </p> </td> 
  </tr> 
 </tbody> 
</table>

