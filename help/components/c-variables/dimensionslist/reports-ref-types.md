---
description: 透過追蹤並記錄每次造訪的訪客反向連結位置，您可以瞭解每次造訪中訪客找到您網站的方式。
title: 反向連結類型
topic: Reports
uuid: 7f63d327-d223-4537-a722-4780aae05c2b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 反向連結類型

透過追蹤並記錄每次造訪的訪客反向連結位置，您可以瞭解每次造訪中訪客找到您網站的方式。

下列清單定義反向連結的各種類型:

**其他網站**: 訪客點按其他網站上網頁 (未定義為您網站的一部分) 上的連結進入您的網站時，會記錄反向連結。

**搜尋引擎**: 訪客使用搜尋引擎存取您的網站時，會記錄搜尋引擎反向連結。Adobe 必須將該反向連結值視為搜尋引擎，而且不能是不被視為搜尋引擎的子網域 (例如 [!DNL mail.yahoo.com] 不是搜尋引擎，因為此網域用於電子郵件)。

**[!UICONTROL 社交網路]**: 反向連結值必須被 Adobe 視為社交網路。請參閱[社交網路清單](https://helpx.adobe.com/analytics/kb/list-social-networks.html)。

**電子郵件**: 當訪客點按包含通訊協定 [!DNL imap://] 或 [!DNL mail://] 的電子郵件連結而進入您的網站時，會將反向連結網域視為電子郵件反向連結網域。例如，來自 [!DNL https://mail.yahoo.com] 的任何點按不會被計算為電子郵件反向連結，因為通訊協定為 [!DNL https://]。來自 Outlook 的電子郵件會報告到「分類/建立書籤」明細項目，而任何已知搜尋引擎網域處的 HTTP 通訊協定反向連結會報告到「搜尋引擎」明細項目。

**分類/建立書籤**: 當訪客在瀏覽器中直接鍵入您的網站 URL 或透過選擇書籤存取您的網站時，會記錄反向連結。當造訪的第一個點擊沒有任何反向連結時，行動裝置現在便會將 *`typed/bookmarked`* 的一個反向連結類型列入報表中。

**[!UICONTROL 網站內]**: 這些項目是指被內部 URL 篩選器加上標記的 URL。這些項目不會計為 *`referrer instances`*，但可在報告其他量度時顯示。

## 根據介面的反向連結類型 {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Marketing Reports &amp; Analytics (SiteCatalyst) </th> 
   <th colname="col3" class="entry"> Ad hoc analytics </th> 
   <th colname="col4" class="entry"> Data warehouse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 報告的反向連結類型 </td> 
   <td colname="col2"> 
    <ul id="ul_EFC8E81EC6DF4CC2AC0E290244FD5859"> 
     <li id="li_686FCAEB04054B9F8A7D2434E8C49F04">其他網站 </li> 
     <li id="li_C232868230AA4A54958B524F3D8FDA35"> 搜尋引擎 </li> 
     <li id="li_A89BFD0468F74ED7822F64BE4A7332AE"> 社交 </li> 
     <li id="li_C824E6F7F6E748DD827A95B105ADBADD"> 分類/建立書籤 </li> 
    </ul> <p> 此報告只顯示兩個預先定義的量度: 例項和獨特訪客。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_FD81EB3C1BD949A39C5A9E9688D25271"> 
     <li id="li_6099E7E03F3843D484808258A332BBE9">其他網站 </li> 
     <li id="li_5AABC02DA7964D578BF8404DA819245D"> 搜尋引擎 </li> 
     <li id="li_B18907AC7FA1429A893B57634EB7DC6F"> 社交 </li> 
     <li id="li_7674B67897994E1FA99BCD9B604BCB6E"> 分類/建立書籤 </li> 
    </ul> </td> 
   <td colname="col4"> 
    <ul id="ul_C37ADBEC31D04295BF5CDEA25DB5191A"> 
     <li id="li_81A642C96C674669BA00B2DACA534B8A">其他網站 </li> 
     <li id="li_29B9DA9F2AAD46A69886D34D5E6E43D4"> 搜尋引擎 </li> 
     <li id="li_E381EEF111F248F99EE39600D616B7C2"> 社交 </li> 
     <li id="li_596377F4D3C248BEA5191EE2985A2B13"> 分類/建立書籤 </li> 
     <li id="li_A7A72D3D6B9A4CCFB43EDA77ABFDEDBC"> 網站內 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 附註 {#section_B83A3571D64E4E7792712FAF740D7955}

* 反向連結、反向連結類型和反向連結網域設定於瀏覽的第一次點擊，或是在反向連結為外部的瀏覽期間 (例如，假設訪客離開您的網站、使用搜尋引擎，然後在第一次瀏覽過期前返回您的網站)。這些值會同時設定，且持續存在於瀏覽期間。
* 並非所有反向連結類型都會列在此報告中。這表示全網站瀏覽值不符合此報告的瀏覽值。

## 報告歷史記錄 {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

| 日期 | 變更 |
|---|---|
| 2014 年 1 月 16 日 | Data Warehouse 已更新為符合 Marketing Reports &amp; Analytics 使用的邏輯。在此日期前，反向連結類型不會持續存在於瀏覽期間。 |

