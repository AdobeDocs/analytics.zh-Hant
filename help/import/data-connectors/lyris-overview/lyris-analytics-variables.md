---
description: 說明要針對每個報表套裝實施保留的eVar和事件。
seo-description: 說明要針對每個報表套裝實施保留的eVar和事件。
seo-title: 為Lynris設定Adobe Analytics變數
solution: Analytics
title: 為Lynris設定Adobe Analytics變數
uuid: 12e150c4-052a-481c-8c27-ef45 ee8019777
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 為Lynris設定Adobe Analytics變數{#configure-adobe-analytics-variables-for-lyris}

說明要針對每個報表套裝實施保留的eVar和事件。

此項整合至少需要個eVar，才能保留每個報表套裝實施。除了這些eVar之外，您也可以根據您要在Analytics中查看的Lynris資料來保留少數活動。下表說明這些eVar和事件：

<table id="table_43E32344E9E54FED8491F28047249329"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 變數類型 </th> 
   <th colname="col2" class="entry"> 變數名稱 </th> 
   <th colname="col3" class="entry"> 變數的使用方式 </th> 
   <th colname="col4" class="entry"> 設定 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> 訊息ID </td> 
   <td colname="col3"> 若要擷取個別電子郵件訊息促銷活動識別 </td> 
   <td colname="col4"> <p>狀態：已啓用 </p> <p>配置：最近 </p> <p>過期時間：「商業決策」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Email Recipient ID </td> 
   <td colname="col3"> 為點擊電子郵件促銷活動的客戶擷取匿名識別碼 </td> 
   <td colname="col4"> <p>狀態：已啓用 </p> <p>配置：最近 </p> <p>過期時間：「商業決策」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris-傳送的電子郵件 </td> 
   <td colname="col3"> 不要儲存。來自Lyris的電子郵件 </td> 
   <td colname="col4">類型：數值數值 <p>參與率：已啓用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris-開啓的電子郵件 </td> 
   <td colname="col3"> 不要儲存。已開啓的電子郵件 </td> 
   <td colname="col4">類型：數值數值 <p>參與率：已啓用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris-開啓的獨特電子郵件 </td> 
   <td colname="col3"> 不要儲存。開啓的唯一電子郵件 </td> 
   <td colname="col4">類型：數值數值 <p>參與率：已啓用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris-電子郵件點進次數 </td> 
   <td colname="col3"> 不要儲存。任何電子郵件被點按的時間 </td> 
   <td colname="col4">類型：數值數值 <p>參與率：已啓用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris-電子郵件彈回數 </td> 
   <td colname="col3"> 儲存否。被反彈的電子郵件 </td> 
   <td colname="col4">類型：數值數值 <p>參與率：已啓用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris-取消訂閱電子郵件 </td> 
   <td colname="col3"> 儲存否。已停用的電子郵件訂閱 </td> 
   <td colname="col4">類型：數值數值 <p>參與率：已啓用 </p> </td> 
  </tr> 
 </tbody> 
</table>

