---
description: emarsys的「資料連接器」整合使用Analytics變數來追蹤各種emarsys量度。
title: Analytics 變數
uuid: 4d5e087c-f495-4aab-9ad1-9b901d34a254
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Analytics 變數{#analytics-variables}

emarsys的「資料連接器」整合使用Analytics變數來追蹤各種emarsys量度。

在識別要與emarsys整合一起使用的事件和eVar後，在「管理控制台」中啟 [用它們](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/c-admin-tools.html)。

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
   <td colname="col1"> 事件（數值） </td> 
   <td colname="col2"> 總彈回數 </td> 
   <td colname="col3"> <p>自動從emarsys導入 </p> </td> 
   <td colname="col4"> <p>「總彈回數」事件可讓您查看因傳送問題而未傳送給收件者的電子郵件訊息數目。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件（數值） </td> 
   <td colname="col2"> 已點按 </td> 
   <td colname="col3"> <p>自動從emarsys導入 </p> </td> 
   <td colname="col4"> <p>「點按」事件可讓您查看點按電子郵件訊息的訪客數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件（數值） </td> 
   <td colname="col2"> 已開啟 </td> 
   <td colname="col3"> <p>自動從emarsys導入 </p> </td> 
   <td colname="col4"> <p>「已開啟」事件可讓您查看開啟電子郵件訊息的訪客人數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件（數值） </td> 
   <td colname="col2"> 已傳送 </td> 
   <td colname="col3"> <p>自動從emarsys導入 </p> </td> 
   <td colname="col4"> <p>「傳送」事件可讓您查看已傳送的電子郵件數目。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件（數值） </td> 
   <td colname="col2"> 取消訂閱 </td> 
   <td colname="col3"> <p>自動從emarsys導入 </p> </td> 
   <td colname="col4"> <p>「取消訂閱」事件可讓您查看開啟電子郵件但接著按一下「取消訂閱」連結以選擇退出您組織未來的電子郵件訊息的訪客數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> <p>透過自動收集方法或JavaScript外掛程式，從電子郵件連結中的查詢參數收集。 </p> </td> 
   <td colname="col4"> Recipient ID </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar 或s.campaign </td> 
   <td colname="col2"> 訊息ID </td> 
   <td colname="col3"> <p>透過自動收集方法或JavaScript外掛程式，從電子郵件連結中的查詢參數收集。 </p> </td> 
   <td colname="col4"> 此值通常儲存在促銷活動變數中。 </td> 
  </tr> 
 </tbody> 
</table>

