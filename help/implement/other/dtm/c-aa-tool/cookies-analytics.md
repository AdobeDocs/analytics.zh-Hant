---
description: 在 Adobe Analytics 中部署動態標籤管理時，所用「Cookie」全域設定的欄位說明。
keywords: Dynamic Tag Management;Cookie;訪客 ID;訪客命名空間;網域句號;FP 網域句號;交易 ID;Cookie 期限
solution: Experience Cloud,Analytics
title: Cookie
uuid: 9c81ecbb-0f02-4c1a-a5a5-426cdea57f38
exl-id: 37e707b0-c42e-4226-82b1-0b63cbff46fb
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '189'
ht-degree: 100%

---

# Cookie

在 Adobe Analytics 中部署 [!UICONTROL Dynamic Tag Management] 時，所用 Cookie 全域設定的欄位說明。

*`Property`* > 編輯工具 >  Cookie

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
   <td colname="col2"> <p>不重複值，代表離線和線上系統的客戶。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪客命名空間 </td> 
   <td colname="col2"> <p>識別 Cookie 設定所在網域的變數。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> 網域句號 </td> 
   <td colname="col2"> <p>決定頁面 URL 網域中的句號數後，要在其中設定 Analytics Cookie <code> s_cc</code> 和 <code> s_sq</code> 的網域。有些外掛程式也會使用此變數來判斷設定外掛程式 Cookie 所需的正確網域。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> FP 網域句號 </td> 
   <td colname="col2"> <p>此 <span class="term"> fpCookieDomainPeriods</span> 變數會用於由 JavaScript (<code> s_sq</code>，<code> s_cc</code>，外掛程式) 設定且原本就是第一方的 Cookie，即使您在實施時使用協力廠商 <span class="filepath"> adobedc.net</span> 網域或舊版的 (但仍有效) <span class="filepath"> 2o7.net</span> 或 <span class="filepath"> omtrdc.net</span> 網域也一樣。 </p> <p>請參閱 <a href="/help/implement/vars/config-vars/fpcookiedomainperiods.md"  >s.fpCookieDomainPeriods</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 交易 ID </td> 
   <td colname="col2"> <p>獨特值，代表導致離線活動的線上交易。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cookie 期限 </td> 
   <td colname="col2"> <p>決定 Cookie 的存留時間。 </p> </td> 
  </tr> 
 </tbody> 
</table>
