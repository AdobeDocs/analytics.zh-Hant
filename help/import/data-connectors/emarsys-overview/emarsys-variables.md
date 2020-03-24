---
description: emarsys 的 Data Connectors 整合使用 Analytics 變數來追蹤各種 emarsys 量度。
title: Analytics 變數
uuid: 4d5e087c-f495-4aab-9ad1-9b901d34a254
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Analytics 變數{#analytics-variables}

emarsys 的 Data Connectors 整合使用 Analytics 變數來追蹤各種 emarsys 量度。

在識別要與 emarsys 整合搭配使用的事件和 eVar 之後，在 [Admin Console](https://docs.adobe.com/content/help/zh-Hant/analytics/admin/admin-tools/c-admin-tools.html) 中啟用它們。

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
   <td colname="col1"> 事件 (數值) </td> 
   <td colname="col2"> 總跳出數 </td> 
   <td colname="col3"> <p>自動從 emarsys 匯入 </p> </td> 
   <td colname="col4"> <p>「總跳出數」事件可讓您查看因發生傳遞問題而未傳遞給收件者的電子郵件訊息數目。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 (數值) </td> 
   <td colname="col2"> 已點按 </td> 
   <td colname="col3"> <p>自動從 emarsys 匯入 </p> </td> 
   <td colname="col4"> <p>「已點按」事件可讓您查看已點按電子郵件訊息的訪客數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 (數值) </td> 
   <td colname="col2"> 已開啟 </td> 
   <td colname="col3"> <p>自動從 emarsys 匯入 </p> </td> 
   <td colname="col4"> <p>「已開啟」事件可讓您查看已開啟電子郵件訊息的訪客數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 (數值) </td> 
   <td colname="col2"> 已傳送 </td> 
   <td colname="col3"> <p>自動從 emarsys 匯入 </p> </td> 
   <td colname="col4"> <p>「已傳送」事件可讓您查看已傳送的電子郵件訊息數目。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 (數值) </td> 
   <td colname="col2"> 已取消訂閱 </td> 
   <td colname="col3"> <p>自動從 emarsys 匯入 </p> </td> 
   <td colname="col4"> <p>「已取消訂閱」事件可讓您查看在開啟電子郵件後按一下「取消訂閱」連結以選擇退出貴組織未來的電子郵件訊息的訪客人數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> 收件者 ID </td> 
   <td colname="col3"> <p>透過自動收集方法或 JavaScript 外掛程式，從電子郵件連結中的查詢參數收集。 </p> </td> 
   <td colname="col4"> 收件者 ID </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar 或 s.campaign </td> 
   <td colname="col2"> 訊息 ID </td> 
   <td colname="col3"> <p>透過自動收集方法或 JavaScript 外掛程式，從電子郵件連結中的查詢參數收集。 </p> </td> 
   <td colname="col4"> 此值通常儲存在行銷活動變數中。 </td> 
  </tr> 
 </tbody> 
</table>

