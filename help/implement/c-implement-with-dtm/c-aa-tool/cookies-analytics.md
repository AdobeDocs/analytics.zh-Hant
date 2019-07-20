---
description: 在 Adobe Analytics 中部署動態標籤管理時，所用「Cookie」全域設定的欄位說明。
keywords: 動態標籤管理；Cookie；訪客ID；訪客命名空間；網域期間；fp網域句點；交易ID；Cookie期限
seo-description: 在 Adobe Analytics 中部署動態標籤管理時，所用「Cookie」全域設定的欄位說明。
seo-title: Cookie
solution: Marketing Cloud，Analytics，動態標籤管理
title: Cookie
uuid: 9c81ecb -f02-4c1a-a5 a5-426cdea57 f38
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Cookie

Field descriptions for the Cookies global settings used for deploying [!UICONTROL Dynamic Tag Management] in Adobe Analytics.

**[!UICONTROL *`Property`*]** &gt;**[！UICONTRL ![](assets/settings_gear.png)

Edit Tool]** &gt; **[!UICONTROL Cookies]**

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
   <td colname="col2"> <p>決定頁面 URL 網域中的句號數後，要在其中設定 Analytics Cookie <code>s_cc</code> 和 <code>s_sq</code> 的網域。有些外掛程式也會使用此變數來決定用以設定外掛程式 Cookie 的正確網域。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> FP 網域句號 </td> 
   <td colname="col2"> <p>此<span class="term"> pdookieDomainPeriods</span> 變數適用於由JavaScript(<code> s_ sq</code>、 <code> s_ cc</code>、外掛程式)設定的Cookie(s_ sq、s_ cc、外掛程式)，即使您的實施使用第三方 <span class="filepath"> 2o7.net</span> 或 <span class="filepath"> omtrdc. net</span> 網域亦然。 </p> <p>See <a href="../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00" format="dita" scope="local"> s.fpCookieDomainPeriods</a>. </p> </td> 
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

