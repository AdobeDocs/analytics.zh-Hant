---
description: 資料連接器整合精靈會逐步引導您完成資料連接器整合程式。
seo-description: 資料連接器整合精靈會逐步引導您完成資料連接器整合程式。
seo-title: Silverpop整合
title: Silverpop整合
uuid: dc5e6a09-3238-412d-9980-4a105ce14819
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Silverpop整合{#silverpop-integration}

資料連接器整合精靈會逐步引導您完成資料連接器整合程式。

若要設定整合：

1. 在Adobe Experience cloud中，從產品下拉式清單中選取「資料連接器」。
1. 按一 **[!UICONTROL 下「新增]** 」，並在「顯示」下拉式清單中選取「依名稱 **[!UICONTROL 」(By Name]****** )。
1. 尋找 **Silverpop Engage 2.0** 圖示，並將其拖曳至Analytics報表套裝中的空插件槽，以啟動「資料連接器整合精靈」。
1. 在Silverpop整合簡介頁面上，檢閱文字，然後選取核取方塊以接受與整合相關的費用。
1. 選取您要用於此整合的報表套裝。
1. 提供好記的名稱以識別此整合，然後按一下「 **[!UICONTROL 建立並設定此整合」]**。

   此頁面會提供整合的概述，以及實用的相關資訊連結。此整合有Adobe和Silverpop費用。 請連絡這兩個組織的適當銷售代表，並確定您瞭解費用結構。
1. 在「資料連接器整合精靈」的每個頁面上，提供所需資訊，如下表所述：

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col2" class="entry"> <p> <b>欄位</b> </p> </th> 
   <th colname="col03" valign="top" align="left" class="entry"> <p> <b>配置部分</b> </p> </th> 
   <th colname="col3" class="entry"> <p> <b>說明</b> </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>整合名稱 </p> </td> 
   <td colname="col03"> <p>(1)整合設定 </p> </td> 
   <td colname="col3"> <p>指定「資料連接器」在報表套裝的「作用中整合清單」中顯示的整合名稱。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>下載檔案 </p> </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p> 用於檔案下載再行銷。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> Email Address </p> </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p>用於向沒有已知Silverpop ID的訪客進行再行銷。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>帳戶ID </p> </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p>指定您的Silverpop帳戶ID（由Silverpop指派給您組織的唯一識別碼），然後按一下「 <b>Next</b> 」（下一步）以繼續精靈的步驟3。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>表單名稱 </p> </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p>用於表單放棄再行銷。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>郵寄ID </p> </td> 
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
   <td colname="col3"> <p>（必要）指定儲存從電子郵件系統匯入之電子郵件「總彈回數」資料的Analytics事件。 </p> <p>「總彈回數」事件可讓您查看因傳送問題而未傳送給收件者的電子郵件訊息數目。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>已點按 </p> </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p>（必要）指定Analytics事件，用以儲存從電子郵件系統匯入的電子郵件「點按」資料。 </p> <p>「點按」事件可讓您查看點按電子郵件訊息的訪客數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> 檔案已下載 </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p> 用於檔案下載再行銷。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> 表單已完成 </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p>用於表單放棄再行銷。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> 表單已開始 </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p>用於表單放棄再行銷。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>已開啟 </p> </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p>（必要）指定Analytics事件，以儲存從電子郵件系統匯入的已開啟電子郵件資料。 </p> <p>「已開啟」事件可讓您查看開啟電子郵件訊息的訪客人數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>已傳送 </p> </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p>（必要）指定Analytics事件，用以儲存從電子郵件系統匯入的電子郵件「已傳送」資料。 </p> <p>「已傳送」事件可讓您查看已傳送的電子郵件數目。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>取消訂閱 </p> </td> 
   <td colname="col03"> <p>(2)變數映射 </p> </td> 
   <td colname="col3"> <p>（必要）指定Analytics事件，用以儲存從電子郵件系統匯入的電子郵件取消訂閱資料。 </p> <p>「取消訂閱」事件可讓您查看開啟電子郵件訊息但接著按一下「取消訂閱」連結以選擇退出您組織未來的電子郵件訊息的訪客人數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>區段 </p> </td> 
   <td colname="col03"> <p>(3)資料設定 </p> </td> 
   <td colname="col3"> <p>此整合會建立顯示在「合作夥伴區段」區段中的合作夥伴定義區段。 </p> <p>此外，您也可以選取現有的報表套裝層級區段，以納入整合中。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> 存取要求 </p> </td> 
   <td colname="col03"> <p>(3)資料設定 </p> </td> 
   <td colname="col3"> <p> （必要）啟用 <span class="uicontrol"> 允許此整合以下載產品資料</span>。 </p> <p>可選：允許此整合下載收入、訂購和件數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>資料彙集 </p> </td> 
   <td colname="col03"> <p>(3)資料設定 </p> </td> 
   <td colname="col3"> <p>如果 <b>您想要使用s_code.js外掛程式做為此整合的收集模型，請選取</b> JavaScript外掛程式(請參閱 <a href="../silverpop-overview/silverpop-analytics-code.md#concept-28e7c834a6804a949aa9306f8896b36e" format="dita" scope="local"></a>Analytics外掛程式程式碼)。 </p> <p>如果您 <b>想要針對此整合使用自動化收集模型</b> ，請選取「自動化解決方案」，然後指定用於此整合的唯一識別碼。 </p> <p>如果您選取此選項，請指定用於此整合的唯一識別碼： </p> <p> <b>訊息ID查詢字串參數：</b>此值代表您的電子郵件合作夥伴附加至著陸頁面URL的訊息ID。 </p> <p> <b></b> 收件者ID查詢字串參數：此值代表您的電子郵件合作夥伴附加至著陸頁面URL的收件者ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>產生控制面板和書籤 </p> </td> 
   <td colname="col03"> <p>（四）報告設定 </p> </td> 
   <td colname="col3"> <p>自動產生整合的控制面板和書籤。 </p> </td> 
  </tr> 
 </tbody> 
</table>

