---
description: earsys的Data Connectors整合使用Analytics變數來追蹤各種emarsys量度。
seo-description: earsys的Data Connectors整合使用Analytics變數來追蹤各種emarsys量度。
seo-title: Analytics 變數
title: Analytics 變數
uuid: 4d5e087c-f495-4aab-9ad1-9b901 d34 a254
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Analytics 變數{#analytics-variables}

earsys的Data Connectors整合使用Analytics變數來追蹤各種emarsys量度。

識別要與emarsys整合搭配使用的Event和eVar後，請在 [「管理控制台](https://microsite.omniture.com/t2/help/en_US/reference/index.html?f=conversion_var_admin)」中啓用它們。

**必要變數**

<table id="table_5B8F3A1EB55D4BB48F669FB84C857256"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 變數類型 </th> 
   <th colname="col2" class="entry"> 名稱 </th> 
   <th colname="col3" class="entry"> 填入方法 </th> 
   <th colname="col4" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> event(數值) </td> 
   <td colname="col2"> 彈回數總計 </td> 
   <td colname="col3"> <p>自動從emarsys匯入 </p> </td> 
   <td colname="col4"> <p>「彈回數總計」事件可讓您查看由於傳送問題而未傳送給收件者的電子郵件訊息數量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event(數值) </td> 
   <td colname="col2"> 點按 </td> 
   <td colname="col3"> <p>自動從emarsys匯入 </p> </td> 
   <td colname="col4"> <p>點擊的事件可讓您查看點擊電子郵件訊息的訪客人數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event(數值) </td> 
   <td colname="col2"> 已開啓 </td> 
   <td colname="col3"> <p>自動從emarsys匯入 </p> </td> 
   <td colname="col4"> <p>「開啓的事件」可讓您查看開啓電子郵件訊息的訪客人數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event(數值) </td> 
   <td colname="col2"> 已傳送 </td> 
   <td colname="col3"> <p>自動從emarsys匯入 </p> </td> 
   <td colname="col4"> <p>「傳送」事件可讓您查看傳送的電子郵件訊息數目。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event(數值) </td> 
   <td colname="col2"> 取消訂閱 </td> 
   <td colname="col3"> <p>自動從emarsys匯入 </p> </td> 
   <td colname="col4"> <p>「取消訂閱」事件可讓您查看開啓電子郵件但按一下「取消訂閱」連結，以取消組織未來電子郵件訊息的訪客數量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> <p>透過自動化收集方法或JavaScript外掛程式，從電子郵件連結中的查詢參數收集。 </p> </td> 
   <td colname="col4"> Recipient ID </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar或s. campaign </td> 
   <td colname="col2"> 訊息ID </td> 
   <td colname="col3"> <p>透過自動化收集方法或JavaScript外掛程式，從電子郵件連結中的查詢參數收集。 </p> </td> 
   <td colname="col4"> 此值通常儲存在促銷活動變數中。 </td> 
  </tr> 
 </tbody> 
</table>

