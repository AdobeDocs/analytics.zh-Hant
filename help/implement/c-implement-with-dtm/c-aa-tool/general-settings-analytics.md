---
description: 用於部署 Adobe Analytics 之動態標籤管理員「一般」設定的欄位描述。
keywords: Analytics實作；實施方法；動態標籤管理；dtm；一般設定；eu合規性；字元集；貨幣代碼；追蹤伺服器；ssl追蹤伺服器
seo-description: 用於部署 Adobe Analytics 之動態標籤管理員「一般」設定的欄位描述。
seo-title: 一般
solution: Analytics
title: 一般
topic: 開發人員和實施
uuid: 93008719-6fb6-4e39-9a75-c937 fe3247 b9
translation-type: tm+mt
source-git-commit: 49c81e50ff10060ef7a3debe82132d1099e25118

---


# 一般

DTM中「一般」設定的欄位描述，用於部署Adobe Analytics。

**[!UICONTROL &lt;屬性&gt;]** &gt; ![](assets/settings_gear.png)**[!UICONTROL 編輯工具]** &gt; **[!UICONTROL 一般]**

<table id="table_DD8DA303698041D296DD5DB080AF7971"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>對 <span class="keyword">Adobe Analytics</span> 啟用 EU 規範  </p> </td> 
   <td colname="col2"> <p> 根據 EU 隱私權 Cookie 來啟用或停用追蹤。 </p> <p>載入頁面時，系統會檢查名為 <span class="filepath">sat_track</span> 的 Cookie 是否已受到設定 (或<span class="wintitle">「編輯屬性」</span>頁面上所指定的自訂 Cookie 名稱)。請考量下列資訊: </p> 
    <ul id="ul_42A6D728F0BC4FBABB0069EFB66DCB01"> 
     <li id="li_227CB14326344AA3980F20C7EACF2AD2"> <p> 如果此 Cookie 不存在，或 Cookie 存在但設定為<span class="term"> true </span>，則會在啓用此設定時跳過工具的載入。其效果是，如果某規則使用工具，則不會套用該規則的任何部分。 </p> <p>如果規則具有啟用了 EU 規範的分析以及第三方代碼，且 Cookie 設定為<span class="term"> false </span>，第三方代碼仍會執行。不過，將不會設定分析變數。 </p> </li> 
     <li id="li_1E74E02D7E4646ACA86D862A1D3C6679"> 如果此 Cookie 存在，但設定為<span class="term"> true </span>，工具會正常載入。 </li> 
    </ul> <p>You are responsible for setting the <span class="filepath"> sat_track </span> (or custom named) cookie to <span class="term"> false </span> if a visitor opts out. 您可以使用自訂代碼來達到此目標: </p> <p> 
     <code>_ satellite. setCookie(「sat_ track」，&amp; amp；nbsp；「false」)； </code>
  </p> <p> You must also have a mechanism to set that cookie to <span class="term"> true </span> if you want a visitor to be able to opt in later: </p> <p> 
     <code>_ satellite. setCookie(「sat_ track」，&amp; amp；nbsp；「true」)； </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>字元集 </p> </td> 
   <td colname="col2"> <p>顯示可用的字元編碼集。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>貨幣代碼 </p> </td> 
   <td colname="col2"> <p>顯示可供選擇的支援貨幣代碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>追蹤伺服器 </p> </td> 
   <td colname="col2"> <p>在其中寫入影像請求和 Cookie 的網域。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL 追蹤伺服器 </p> </td> 
   <td colname="col2"> <p>在其中寫入影像請求和 Cookie 的網域。用於安全頁面。若未定義，則 SSL 資料會傳送至 <span class="term"> trackingServer </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>資料中心 </p> </td> 
   <td colname="col2"> <p>用來收集資料的 Adobe 資料中心。 </p> </td> 
  </tr> 
 </tbody> 
</table>

