---
description: 大部分行動裝置接受瀏覽器 Cookie。然而，萬一裝置不接受 Cookie，則會使用另一種方法來專門識別無線裝置。
keywords: Analytics Implementation
title: 識別行動裝置
topic: Developer and implementation
uuid: 22587dd1-cead-485b-a4d8-94dfb7cd9662
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 識別行動裝置

大部分行動裝置接受瀏覽器 Cookie。然而，萬一裝置不接受 Cookie，則會使用另一種方法來專門識別無線裝置。

Adobe 已找出數個可唯一識別大多數行動裝置的 HTTP [訂閱者 OD 標題](/help/implement/js-implementation/c-unique-visitors/visid-mobile.md#section_60D6EAC0D16945A89DD5A7ADF3B8298D)。這些標題常包含裝置電話號碼 (或號碼的雜湊版本) 或其他識別碼。目前大部分裝置具有一或多個可唯一識別裝置的標題，所有 Adobe 資料收集伺服器都會自動以這些標題代替訪客 ID。

在一般影像要求中，路徑 (`/b/ss/rsid/1`) 中的「1」會導致 Adobe 伺服器傳回 gif 影像，並嘗試設定持續的[!UICONTROL 訪客 ID] Cookie (`AMCV_` 或 `s_vi`)。然而，如果根據 HTTP 標題將裝置辨識為行動裝置，則會傳遞 '5'，取代 '1'，以指出應該傳回 wbmp 格式影像，而且我們已辨識的無線標題 (不是 Cookie) 清單應該用來識別裝置。

下表列出根據路徑中的傳回影像類型值 ('1' or '5') 所使用之 ID 方法的順序:

<table id="table_07B0E55D5DAA4552A5CBC6937D47A857"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定 </th> 
   <th colname="col2" class="entry"> ID 方法順序 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> /1/</code> </td> 
   <td colname="col2"> <p>預設值: </p> 
    <ul id="ul_E37E9919658A492C92187BAA18D33AB6"> 
     <li id="li_1A9E39C7CFB24C68AA07C8E85D33A858">自訂訪客 ID </li> 
     <li id="li_0DC8D17828C848BEB614C6E47C090064">Cookie </li> 
     <li id="li_52706792FAD14F459266E3A672F92EA1">訂閱者 ID 標題 </li> 
     <li id="li_ECAD713D22314338BB5C92167DC0BB02"> IP 位址-使用者代理-閘道 IP 位址 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> /5/ /5.1/ /5.5/</code> </td> 
   <td colname="col2"> <p>Device was identified as a wireless device, or <code> /5/</code> was manually sent in the image request: </p> 
    <ul id="ul_624BEDFA3E1243CF9B42081D8B8EFFFB"> 
     <li id="li_D65761D23B684DB59BC23E92C9098122">自訂訪客 ID </li> 
     <li id="li_ADBA806B74CA43EFA8612301E06106C6">訂閱者 ID 標題 </li> 
     <li id="li_79DFD0DEAA1242C09A03E8134A40F799">Cookie </li> 
     <li id="li_A462B9120FC6443480D62F37D456747E">IP 位址-使用者代理-閘道 IP 位址 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

您也可以在手動影像請求中傳遞 '1'或 '5'，但請注意，這些程式碼是互斥的，因此一律傳遞 '5' 並不會在支援 Cookie 時使用它。您可以合併本身的機制，判斷裝置是否支援 Cookie，若支援，則在影像中傳入 '1'，而不要傳入 '5'。在此情況下，正確性的提升會因為支援 Cookie 的行動裝置數而受到限制。

## 訂閱者 ID 標題 {#section_60D6EAC0D16945A89DD5A7ADF3B8298D}

訂閱者 ID 方法用於使用者識別，通常比 Cookie 更可靠，因為 Cookie 有刪除、接受和閘道 Cookie 管理的問題。

將您自己新增至行動訪客所使用之電信業者的白名單，可以改進識別訪客的變更。若想存取電信業者的訪客 ID，請聯絡電信業者以將您的網域新增至其白名單。如果您位於電信業者的白名單上，則也可以存取一般無權存取的訂閱者 ID 標題。

下列標題清單可用來識別無線裝置。處理標題的運算法為

1. 擷取 HTTP 標題鍵 (標題的名稱，例如 "X-Up-Calling-Line-ID")
1. 除去所有非字母 (A-Z 和 a-z) 字元
1. 將標題鍵轉換為小寫
1. 比較鍵尾與下表中的鍵尾來找出相符者:

| 標題 | 類型 | 範例 |
|---|---|---|
| callinglineid | ID | X-Up-Calling-Line-ID: 8613802423312 |
| subno | ID | x-up-subno: swm_10448371100_vmag.mycingular.net |
| clientid | ID | ClientID: eGtUpsqEO19zVHmbOkgaPVI-@sprintpcs.com |
| uid | ID | x-jphone-uid: a2V4Uh21XQH9ECNN |
| clid | ID | X-Hts_clid: 595961714786 |
| deviceid | ID | rim-device-id: 200522ae |
| forwardedfor | ID 或 IP 位址 | X-Forwarded-For: 127.0.0.1 |
| msisdn | ID 或 IP 位址 | X-Wap-msisdn: 8032618185 |
| clientip | IP 位址 | Client-ip: 10.9.41.2 |
| wapipaddr | IP 位址 | X-WAPIPADDR: 10.48.213.162 |
| huaweinasip | IP 位址 | x-huawei-NASIP: 211.139.172.70 |
| userip | IP 位址 | UserIP: 70.214.81.241 |
| ipaddress | IP 位址 | X-Nokia-ipaddress: 212.97.227.125 |
| subscriberinfo | IP 位址 | X-SUBSCRIBER-INFO: IP=10.103.132.128 |

例如，"callinglineid" 會比對出 "X-Up-Calling-Line-ID" 和 "nokia-callinglineid"。標題類型可指出標題中應有的項目。以下列出標題的優先順序 (若有 "callinglineid" 標題存在，則會以此標題取代 "subno")。

您可以使用[從標題擷取特定值的動態變數](/help/implement/js-implementation/c-variables/dynvars-overview.md)。
