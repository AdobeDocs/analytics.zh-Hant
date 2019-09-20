---
description: 資料連接器整合精靈會逐步引導您完成資料連接器整合程式。
seo-description: 資料連接器整合精靈會逐步引導您完成資料連接器整合程式。
seo-title: 執行資料連接器整合精靈
title: 執行資料連接器整合精靈
uuid: 387ac9d0-3719-49ff-81cb-1f05accf9b6c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# 執行資料連接器整合精靈{#running-the-data-connectors-integration-wizard}

資料連接器整合精靈會逐步引導您完成資料連接器整合程式。

若要設定整合：

1. 登入 Experience Cloud。
1. 在Analytics首頁上，按一下紙輪或工具列上的「資料連接器」圖示。
1. 在「資料連接器」頁面上，選取您要設定整合的報表套裝。

   >[!NOTE]
   >
   >請務必從「資料連接器」頁面左上角的「報 **表套裝** 」下拉式清單中選取所需的報表套裝。

1. 按一 **下Data Connectors** UI左側「Partner List **」（合作夥伴清單）上方的「Pertyle** 」（字母順序）標籤，然後找到「 **Delivra** 」圖示。
1. 拖曳 **Delivra** 圖示至Analytics報表套裝中的空插件槽，以啟動「資料連接器整合精靈」。
1. 在「傳送整合簡介」頁面上，檢閱文字，然後選取核取方塊以接受與整合相關的費用，然後按一下「下 **一步**」。

   此頁面會提供整合的概述，以及實用的相關資訊連結。此整合有Adobe和Delivra的相關費用。 請連絡這兩個組織的適當銷售代表，並確定您瞭解費用結構。
1. 在「資料連接器整合精靈」的每個頁面上，提供所需資訊，如下表所述：

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" valign="top" align="left" class="entry"> <p><b>嚮導頁碼</b> </p> </th> 
   <th colname="col2" class="entry"> <p><b>欄位</b> </p> </th> 
   <th colname="col3" class="entry"> <p><b>說明</b> </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2" valign="top" align="left"> <p>整合名稱 </p> </td> 
   <td colname="col3"> <p>指定「資料連接器」在報表套裝的「作用中整合清單」中顯示的整合名稱。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>整合電子郵件地址 </p> </td> 
   <td colname="col3"> <p>指定接收與此整合相關之所有通知的電子郵件地址，然後按一下「下 <b>一步</b> 」以繼續精靈的步驟2。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>帳戶ID </p> </td> 
   <td colname="col3"> <p>指定您的傳送帳戶ID（由Delivra指派給您組織的唯一識別碼），然後按一下「 <b>Next</b> 」（下一步）以繼續精靈的步驟3。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>訊息ID </p> </td> 
   <td colname="col3"> <p>識別用於追蹤電子郵件訊息ID的Analytics eVar。 </p> <p>訊息ID用於行銷／再行銷促銷活動。 訊息ID通常稱為「追蹤代碼」。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col3"> <p>識別用於追蹤電子郵件收件者ID的Analytics eVar。 </p> <p>收件者ID用於行銷／再行銷促銷活動。 訊息ID通常稱為「訪客代碼」。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>驗收複選框 </p> </td> 
   <td colname="col3"> <p>複查「接受」(Acceptance)複選框旁顯示的資訊： </p> <p><i>我瞭解，透過啟用「收件者ID」追蹤，此功能可追蹤我們網站訪客的個人識別資訊。 這涉及隱私權問題，需要我的組織實施適當的程式，例如向網站訪客提供通知並給予同意。 </i> </p> <p>如果您同意接受聲明，請選中該複選框，然後按一下「 <b>Next</b> （下一步）」以繼續嚮導的步驟4。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>用戶端定義的報表套裝層級區段 </p> </td> 
   <td colname="col3"> <p>此整合會建立合作夥伴定義的區段，顯示在整合精靈的「整合區段」頁面的左側。 </p> <p>此外，您也可以選取現有的報表套裝層級區段，以納入整合中。 </p> <p>在頁面右側選取所需的區段，然後按一下「下 <b>一步</b> 」以繼續精靈的步驟5。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>已點按 </p> </td> 
   <td colname="col3"> <p>指定Analytics事件，以儲存從電子郵件系統匯入的電子郵件「已點按」資料。 </p> <p>「點按」事件可讓您查看點按電子郵件訊息的訪客數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>已開啟 </p> </td> 
   <td colname="col3"> <p>指定Analytics事件，以儲存從電子郵件系統匯入的電子郵件已開啟資料。 </p> <p>「已開啟」事件可讓您查看開啟電子郵件訊息的訪客人數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>已傳送 </p> </td> 
   <td colname="col3"> <p>指定Analytics事件，以儲存從電子郵件系統匯入的電子郵件已傳送資料。 </p> <p>「點按」事件可讓您查看已傳送的電子郵件數目。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>總彈回數 </p> </td> 
   <td colname="col3"> <p>指定儲存從電子郵件系統匯入之電子郵件「總彈回數」資料的Analytics事件。 </p> <p>「總彈回數」事件可讓您查看因傳送問題而未傳送給收件者的電子郵件訊息數目。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>取消訂閱 </p> </td> 
   <td colname="col3"> <p>指定儲存從電子郵件系統匯入之電子郵件取消訂閱資料的Analytics事件。 </p> <p>「取消訂閱」事件可讓您查看開啟電子郵件訊息但接著按一下「取消訂閱」連結以選擇退出您組織未來的電子郵件訊息的訪客人數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> 分享次數 </td> 
   <td colname="col3"> <p>指定電子郵件訊息分享至社交網路的次數，然後按一下「下一 <b>步</b> 」繼續精靈的步驟6。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>資料收集：JavaScript外掛程式 </p> </td> 
   <td colname="col3"> <p>如果 <b>您想要使用外掛程式做為此整合的收集模型，請選取「JavaScript外掛程式」</b><b></b> ，然後按一下「下一步」以繼續精靈的步驟7。 </p> <p> <p>注意： 自動化解決方案是預設的選擇。 </p> </p> <p>請連絡您的Adobe顧問以取得用於此整合的JavaScript外掛程式副本。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>資料收集：自動化解決方案 </p> </td> 
   <td colname="col3"> <p>如果您 <b>想要針對此整合使用自動化收集模型</b> ，請選取「自動化解決方案」，然後指定用於此整合的唯一識別碼。 </p> <p> <p>注意： 自動化解決方案是預設的選擇。 </p> </p> <p>如果您選取此選項，請指定用於此整合的唯一識別碼： </p> <p><b>訊息ID查詢字串參數：</b>此值代表您的電子郵件合作夥伴附加至著陸頁面URL的訊息ID。 </p> <p><b></b> 收件者ID查詢字串參數：此值代表您的電子郵件合作夥伴附加至著陸頁面URL的收件者ID。 </p> <p>按一下 <b>下一步</b> ，繼續執行嚮導的步驟7。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>整合摘要 </p> </td> 
   <td colname="col3"> <p>按一下每個類別旁的加號(+)，然後按一下「儲存 <b></b> 」繼續精靈的步驟8，以驗證整合參數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>整合完成 </p> </td> 
   <td colname="col3"> <p>按一 <b>下「完成</b> 」以完成整合。 </p> <p><b></b> 重要：Analytics不會儲存整合設定，直到您按一下「完 <b>成</b>」。 </p> </td> 
  </tr> 
 </tbody> 
</table>

