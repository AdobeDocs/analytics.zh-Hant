---
description: 在 Adobe Analytics 中部署動態標籤管理時，所用「Cookie」全域設定的欄位說明。
keywords: Dynamic Tag Management;cookies;visitor id;visitor namespace;domain periods;fp domain periods;transaction id;cookie lifetime
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Cookie
uuid: 9c81ecbb-0f02-4c1a-a5a5-426cdea57f38
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Cookie

在 Adobe Analytics 中部署 [!UICONTROL Dynamic Tag Management] 時，所用 Cookie 全域設定的欄位說明。

*`Property`* &gt; 編輯工具 &gt;  Cookie

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 訪客 ID </td> 
   <td colname="col2"> <p>獨特值，代表客戶在線上和離線系統的身分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪客命名空間 </td> 
   <td colname="col2"> <p>變數用來識別 Cookie 設定所在的網域。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> 網域句號 </td> 
   <td colname="col2"> <p>決定頁面 URL 網域中的句號數後，要在其中設定 Analytics Cookie <code> s_cc</code> 和 <code> s_sq</code> 的網域。有些外掛程式也會使用此變數來判斷設定外掛程式 Cookie 所需的正確網域。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> FP 網域句號 </td> 
   <td colname="col2"> <p>此 <span class="term"> fpCookieDomainPeriods</span> variable is for cookies set by JavaScript (<code> s_sq</code>, <code> s_cc</code>, plug-ins) that are inherently first-party cookies, even if your implementation uses the third-party <span class="filepath"> 2o7.net</span> or <span class="filepath"> omtrdc.net</span> domains. </p> <p>請參閱 <a href="/help/implement/js-implementation/c-variables/configuration-variables.md"  >s.fpCookieDomainPeriods</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 交易 ID </td> 
   <td colname="col2"> <p>獨特值，代表導致離線活動的線上交易。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cookie 期限 </td> 
   <td colname="col2"> <p>決定 Cookie 的生命期。 </p> </td> 
  </tr> 
 </tbody> 
</table>

