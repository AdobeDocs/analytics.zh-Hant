---
description: 此項整合需要每個報表套裝實施保留個eVar。
seo-description: 此項整合需要每個報表套裝實施保留個eVar。
seo-title: 設定適用於Seligent的Analytics變數
solution: Analytics
title: 設定適用於Seligent的Analytics變數
uuid: 3b7b8b4b-7614-4439-bcc0-ddb5304844
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Configure Analytics Variables for Selligent{#configure-analytics-variables-for-selligent}

此項整合需要每個報表套裝實施保留個eVar。

除了這些eVar之外，有些事件可能會保留下來，視您想在Analytics中查看的Seririgent資料而定。這些eVar和事件如下所述：

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 變數類型 </th> 
   <th colname="col2" class="entry"> 變數名稱 </th> 
   <th colname="col3" class="entry"> 如何使用 </th> 
   <th colname="col4" class="entry"> 設定 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> 訊息ID </td> 
   <td colname="col3"> 擷取個別電子郵件訊息促銷活動識別。 </td> 
   <td colname="col4"> <p><b>狀態</b>：已啓用 </p> <p><b>配置</b>：最近 </p> <p><b>過期</b>時間：「商業決策」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eV ar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> 擷取點擊電子郵件促銷活動之客戶的匿名識別。 </td> 
   <td colname="col4"> <p><b>狀態</b>：已啓用 </p> <p><b>配置</b>：最近 </p> <p><b>過期</b>時間：「商業決策」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 已傳送 </td> 
   <td colname="col3"> 儲存從Seligent傳送的電子郵件數目。 </td> 
   <td colname="col4"> <p><b>類型</b>：數值數值 </p> <p><b>參與率</b>：已啓用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 遞送內容 </td> 
   <td colname="col3"> 儲存傳遞的電子郵件數目。 </td> 
   <td colname="col4"> <p><b>類型</b>：數值數值 </p> <p><b>參與率</b>：已啓用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 檢視 </td> 
   <td colname="col3"> 儲存已檢視的唯一電子郵件數目。 </td> 
   <td colname="col4"> <p><b>類型</b>：數值數值 </p> <p><b>參與率</b>：已啓用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 點擊次數 </td> 
   <td colname="col3"> 儲存任何電子郵件的點按次數。 </td> 
   <td colname="col4"> <p><b>類型</b>：數值數值 </p> <p><b>參與率</b>：已啓用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 彈回間 </td> 
   <td colname="col3"> 儲存被反彈的電子郵件數目。 </td> 
   <td colname="col4"> <p><b>類型</b>：數值數值 </p> <p><b>參與率</b>：已啓用 </p> </td> 
  </tr> 
 </tbody> 
</table>

