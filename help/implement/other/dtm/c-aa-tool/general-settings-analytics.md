---
description: 用於部署 Adobe Analytics 之動態標籤管理員「一般」設定的欄位描述。
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;general settings;eu compliance;character set;currency code;tracking server;ssl tracking server
title: 一般
topic: Developer and implementation
uuid: 93008719-6fb6-4e39-9a75-c937fe3247b9
translation-type: tm+mt
source-git-commit: ebf149df7974f9f2889b6fe938088eda90c84051

---


# 一般

用於部署 Adobe Analytics 之 DTM 一般設定的欄位描述。

**[!UICONTROL &lt;屬性>]**>編![](assets/settings_gear.png)輯工**[!UICONTROL &#x200B;具]** >一般 **[!UICONTROL 資訊]**

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
     <li id="li_227CB14326344AA3980F20C7EACF2AD2"> <p> 如果此 Cookie 不存在，或 Cookie 存在但設定為<span class="term">true</span> 以外的任何值，則會在啟用此設定時跳過工具的載入。其效果是，如果某規則使用工具，則不會套用該規則的任何部分。 </p> <p>如果規則具有啟用了 EU 規範的分析以及第三方代碼，且 Cookie 設定為<span class="term">false</span>，則第三方程式碼仍會執行。不過，將不會設定分析變數。 </p> </li> 
     <li id="li_1E74E02D7E4646ACA86D862A1D3C6679"> 如果此 Cookie 存在，但設定為<span class="term">true</span>，則工具會正常載入。 </li> 
    </ul> <p>如果訪客選擇退出，您要負責將 <span class="filepath"> sat_track </span> (或自訂名稱) Cookie 設為 <span class="term">false</span>。您可以使用自訂代碼來達到此目標: </p> <p> 
     <code>
       _satellite.setCookie("sat_track",&amp;nbsp;"false"); 
     </code> </p> <p> 若要讓訪客能在之後選擇加入，您也必須有能將 Cookie 設為 <span class="term">true</span> 的機制: </p> <p> 
     <code>
       _satellite.setCookie("sat_track",&amp;nbsp;"true"); 
     </code> </p> </td> 
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
   <td colname="col2"> <p>在其中寫入影像請求和 Cookie 的網域。用於安全頁面。若未定義，則 SSL 資料會傳送至<span class="term"> trackingServer </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>資料中心 </p> </td> 
   <td colname="col2"> <p>用來收集資料的 Adobe 資料中心。 </p> </td> 
  </tr> 
 </tbody> 
</table>

