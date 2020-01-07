---
description: iOS 的累積發行說明。
solution: Analytics,Experience Cloud
subtopic: Release notes
title: iOS 應用程式
topic: Developer and implementation
uuid: cc98f8f2-f619-4b31-abf9-e43f4deac64f
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# iOS{#ios}

iOS 的累積發行說明。

> [!NOTE]若要尋找目前的程式庫版本，請開啟偵錯記錄功能。

您可在 [GitHub](https://github.com/Adobe-Marketing-Cloud/mobile-services) 和 [Developer Connection](https://marketing.adobe.com/developer/gallery/app-measurement-for-ios) 中下載行動程式庫。

[4.x 文件](https://marketing.adobe.com/resources/help/zh_TW/mobile/ios/)

[3.x 文件](https://marketing.adobe.com/resources/help/zh_TW/sc/appmeasurement/ios/)

## 版本 4.13.4 {#section_BF05D33CEF6E42358C8089441449449B}

[!DNL iOS] SDK 4.13.4 版 (2017 年 2 月 16 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_657D643E874D47C099F2F43519C9C1C7"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>應用程式內傳訊 </p> </td> 
   <td colname="2"> <p> 修正在確定對象時無法使用正確應用程式版本的問題。當使用者有應用程式版本升級但未啟動新的 Lifecycle 時，就會發生此問題。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 贏取 </p> </td> 
   <td colname="2"> <p> 新增三秒鐘的延遲，接著才會在應用程式安裝時進行 API 呼叫以取得 Apple Search 廣告資料 (根據文件建議)。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.13.3 {#section_39618D2B29F942FCBF37E4F5507AA131}

[!DNL iOS] SDK 4.13.3 版 (2017 年 1 月 19 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_341D35BF18714139A95CA5491899185D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>應用程式內傳訊 </p> </td> 
   <td colname="2"> <p> 您現在可以在 VoiceOver 執行中停用全螢幕訊息。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Analytics</span> </p> </td> 
   <td colname="2"> <p> 改善唯讀資料庫存取的處理方式。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>一般 </p> </td> 
   <td colname="2"> <p> 修正在使用應用程式群組從背景呼叫追蹤方法時有時會導致當機的問題。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.13.2 {#section_CB0DFFDB38FE4D14A84423DF40BF8FD3}

[!DNL iOS] SDK 4.13.2 版 (2016 年 11 月 10 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_AA26B14D271948FFBA44D4D06E3B71AA"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 訪客 ID服務 </p> </td> 
   <td colname="2"> <p> 在 <code> adobe_mc</code>   參數中新增時間戳記和 Experience Cloud 組織 ID。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 設定 </p> </td> 
   <td colname="2"> <p> 透過 <code> setAdvertisingIdentifier:</code> 傳遞至 SDK 的無效 IDFA (00000000-0000-0000-0000-000000000000) 將會被忽略。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 深層連結 </p> </td> 
   <td colname="2"> <p>在呼叫 <code> trackAdobeDeepLink</code> 時，系統已能適當處理帶有「<code> adb</code>」和「<code> ctx</code>」首碼的變數。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 贏取 </p> </td> 
   <td colname="2"> <p>系統現在會連同您的贏取資料與 Apple Search Ads 資料一併傳送。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.13.1 {#section_18C8A7166EFD4E67AC0F7C06DFBBFE6A}

[!DNL iOS] SDK 4.13.1 版 (2016 年 10 月 20 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_5B67A6B8B79D4783BA8DCDA7C2ACA765"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 贏取 </p> </td> 
   <td colname="2"> <p> SDK 現在支援讓 <code> AdobeDataCallback</code> 叫用適當地處理自訂贏取資料。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>目標 </p> </td> 
   <td colname="2"> <p><span class="keyword"></span>訪客 ID 服務參數現在可以透過 <span class="keyword"></span> 的<code> mboxParams</code>目標請求傳送。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**錯誤修正**

* 修正在將新 ID 同步到 VisitorID 服務，同時將追蹤點擊傳送到 [!DNL Adobe Analytics] 時，可能會導致當機的問題。
* 修正當目標 [!DNL iOS] 版本比 8 還舊時會引發組建警告的問題。

## 版本 4.13.0 {#section_F72A3357994E4887A9F3967F0FBFFCDD}

[!DNL iOS] SDK 4.13.0 版 (2016 年 9 月 15 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_FD6156E58FF54BA2BEED7398BC780C46"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>應用程式內傳訊 </p> </td> 
   <td colname="2"> <p>新增可開啟深層連結 URI 的新訊息類型。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.12.0 {#section_2AD26AABBB434833AE961C8D71C9AFE8}

[!DNL iOS] SDK 4.12.0 版 (2016 年 8 月 18 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_CC3CD01203ED4BDA9BC26427E925C70D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>訪客 ID服務 </p> </td> 
   <td colname="2"> <p> 新增可將訪客身分新增至指定 URL 的新方法，以將身分傳送給以網路為基礎的實作。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>應用程式內傳訊 </p> </td> 
   <td colname="2"> <p>修正為自訂全螢幕訊息的 HTML 標籤將「target」屬性設為「_blank」時，會造成當機的問題。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.11.0 {#section_3ABABE0F0B964EB48BD482CCE260A13D}

[!DNL iOS] SDK 4.11.0 版 (2016 年 6 月 22 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_14B23402BA3B41238F419CA57341B8F5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Target 方法 </p> </td> 
   <td colname="2"> <p>您現在可以使用以下新 <span class="keyword">Target</span> 方法:· </p> <p> 
     <ul id="ul_93CDE46E39C9431DA9104664F175708B"> 
      <li id="li_903FAC68526B4B7CB6555DC577CE493A"><code> targetLoadRequestWithName:defaultContent:profileParameters:orderParameters:mboxParameters:requestLocationParameters:callback:</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.10.0 {#section_F0D6D7FD89DE4DF5A121B05FA093CC5B}

[!DNL iOS] SDK 4.10.0 版 (2016 年 5 月 20 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_AC447B6E4D55489F803923BF5D1D6653"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Target 方法 </p> </td> 
   <td colname="2"> <p>您現在可以使用以下新 <span class="keyword">Target</span> 方法:· </p> <p> 
     <ul id="ul_D0594A9ABFD8448186DED87599A0E50E"> 
      <li id="li_A4B0ECDF200C438BB1AB24D613453A68"><code> targetLoadRequestWithName:defaultContent:profileParameters:orderParameters:mboxParameters:callback:</code> </li> 
      <li id="li_C0FADBB3CEE141AE951CBD49F3A52642"><code> targetThirdPartyID</code> </li> 
      <li id="li_3E1B3725D9EE4ECE9DB0EB1A9E7682A4"><code> targetSetThirdPartyID:</code> </li> 
      <li id="li_659E295610F541819DD7486FC5177012"><code> targetPcID</code> </li> 
      <li id="li_B00ADCF98B6D4694BB7664DB42CDFF99"><code> targetSessionID</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>TVJS 方法 </p> </td> 
   <td colname="2"> <p>您現在可以使用以下新 <span class="keyword">Target</span> TVJS 方法: </p> <p> 
     <ul id="ul_AED76A2B99534CF3A472AC0381B2618C"> 
      <li id="li_AA731652996C4A19A8E02D5D6B8BDC93"><code> targetThirdPartyID</code> </li> 
      <li id="li_744A63A62A8045E49C75F9D7AED5D75E"><code> targetSetThirdPartyID</code> </li> 
      <li id="li_72BC8D96FE0549A695D90B924FA80A02"> <code> targetPcID</code> </li> 
      <li id="li_FB7A9435B9994DB89FA80C2B2218C047"> <code> targetSessionID</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>適用於 TVML/TVJS 的 Adobe Target </p> </td> 
   <td colname="2"> <p>現在當您設定 <code> ADBTarget</code> 元素時，可以使用以下屬性名稱: </p> <p> 
     <ul id="ul_A0CEE891AE644B47ABD6F7425ACD464D"> 
      <li id="li_2EB0C3CA52014F45BA1EC07703E821B8"><code> id</code> </li> 
      <li id="li_069D996CED534EE88A1EC82684E470D5"><code> total</code> </li> 
      <li id="li_97F290C03FFD46B8A1E78B7BF2021F55"> <code> purchasedProductIds</code> </li> 
      <li id="li_FAAC4BB12DF9491DA21F161711A7707D"> <code> mboxParameters</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.9.0 {#section_DA97D7294B214067A4904B9738450759}

[!DNL iOS] SDK 4.9.0 版 (2016 年 5 月 5 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_0B3A0F44549C4DA48C7639048C030065"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>深層連結 </p> </td> 
   <td colname="2"> <p>您可以在應用程式中實施深層連結，將使用者導向應用程式或網頁連結目標。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.8.6 {#section_0150641B44CF4F6CBE2B21002F8EAB30}

[!DNL iOS] SDK 4.8.6 版 (2016 年 3 月 9 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_5175CFFCA30B4DDBACFB23532111CB8A"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>追蹤應用程式當機 </p> </td> 
   <td colname="2"> <p><span class="keyword">iOS</span> SDK 4.8.6 版包含無法回報錯誤當機的重要變更。我們強烈建議您更新至 4.8.6 版。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.8.5 {#section_F42EB64F91024748893E89575F2E4487}

[!DNL iOS] SDK 4.8.5 版 (2016 年 2 月 18 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_AB225AF04A374421BDD8A972506ACD06"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>退出與隱私權設定 </p> </td> 
   <td colname="2"> <p>從 <span class="keyword">iOS</span> SDK 4.8.5 開始，透過 <code> setPrivacyStatus</code> 方法設定隱私權設定，將影響 <span class="keyword">Analytics</span>、<span class="keyword">Target</span> 和 <span class="keyword">Audience Manager</span> 中的活動。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.8.0 {#section_2CF142C8C2D24B529559DAF76F851BBF}

[!DNL iOS] SDK 4.8.0 版 (2015 年 11 月 2 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_9DB41F070D66498FACF1A9C135603C7A"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> 新的 Experience Cloud 訪客 ID 服務方法 </td> 
   <td colname="2"> <p>已新增下列新方法: </p> 
    <ul id="ul_55D8F29ADE3746C484FEC7893FA9EF23"> 
     <li id="li_19F8AF546EEB45EBB5849EA6EB3CE6A3"><code> visitorSyncIdentifiers:authenticationState:</code> </li> 
     <li id="li_1AF1CF62B3ED442D81B438ECBF981583"><code> visitorSyncIdentifierWithType:identifier:authenticationState: </code> </li> 
     <li id="li_C116F0DA8E2A449A8B76637961C2100C"><code> visitorGetIDs</code> </li> 
    </ul> <p>將 <code> visitorSyncIdentifiers:identifiers</code> 方法變更為 <code> visitorSyncIdentifiers:</code> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> 新的 TVJS 方法 </td> 
   <td colname="2"> <p>已新增下列新方法: </p> 
    <ul id="ul_4C7F4BB1CF744444ABAA9F13BA98749E"> 
     <li id="li_5DAB089D115843CCA0A53873D6D676F0"><code> visitorSyncIdentifiersAuthenticationState</code> </li> 
     <li id="li_EDE2D1301E8648DB88A18D8C9F6A22C5"><code> visitorSyncIdentifierWithTypeIdentifierAuthenticationState</code> </li> 
     <li id="li_2CCED3C707774597934A2F08BC690B15"><code> visitorGetIDsJs</code> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> 新的 ADBMobile JSON Config 變數 </td> 
   <td colname="2"> <p>已新增下列變數:  </p> 
    <ul id="ul_95065BC06FD540D2937D11111799F77F"> 
     <li id="li_7C8C68A41FBA4D098D6803E71D4CCF7A"><code> analyticsForwardingEnabled</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.7.0 {#section_B37B1CAF065346E9A2073A06AB7AFEC2}

[!DNL iOS] SDK 4.7.0 版 (2015 年 10 月 15 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_3CCA327B859B498D828B2E056A075BEC"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> tvOS 支援 </td> 
   <td colname="2"> <p>Apple TV 支援 tvOS。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> App Transport Security 支援 </td> 
   <td colname="2"> <p>Apple 自 <span class="keyword">iOS</span> 9 開始導入 App Transport Security，這是一套符合安全連線最佳實務的規範。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> PhoneGap 外掛程式方法</span> </p> </td> 
   <td colname="2"> <p>已新增下列新方法: </p> <p><b>設定方法</b> </p> <p> 
     <ul id="ul_98C5E7B5C79446EEA00F0E7CBC213301"> 
      <li id="li_B403C06E57A0450CBB4ABAD45170C681">setPushIdentifier </li> 
      <li id="li_6D76C40601544D4FA13FD44F390C83CE">setAdvertisingIndentifier </li> 
      <li id="li_7D03005DBD9E4AC7BB78BA162CDC8153">keepLifecycleSessionAlive </li> 
      <li id="li_3DDE07508B764E679AF2ACECC4D935CB">trackingSendQueuedHits </li> 
     </ul> </p> <p><b>追蹤方法</b> </p> <p> 
     <ul id="ul_9B6002F5642B4D888FBD0A8D44EF32DB"> 
      <li id="li_5C1C9EA770E048E48723528F346712B4">trackPushMessageClickthrough </li> 
     </ul> </p> <p>新 Target 方法: </p> <p> 
     <ul id="ul_E6A481FCD49D4CF48A4B0636312FCD19"> 
      <li id="li_6604FBB05C4E4988A04CB376D6667C79">targetClearCookies </li> 
     </ul> </p> <p><b>贏取方法</b> </p> <p> 
     <ul id="ul_2015BFF019E64D5685A25E20D4B4A79B"> 
      <li id="li_D450F60189904C43BDAC5D658324AEAA">acquisitionCampaignStartForApp </li> 
     </ul> </p> <p><b>Audience Manager 方法</b> </p> <p> 
     <ul id="ul_7D5F339A1A004593AE1D5C26A5A495C5"> 
      <li id="li_2F44037A508D49308F42961FDFB6486C">audienceGetVisitorProfile </li> 
      <li id="li_4F8F43C875384A74ADD48D4197C2ACFD">audienceGetDpuuid </li> 
      <li id="li_B38B6700AF2F4B9FA80CC6774B5B14E7">audienceGetDpid </li> 
      <li id="li_12579B472B404ABAA12DFBDBB22A0C30">audienceSetDpidAndDpuuid </li> 
      <li id="li_2CA997AF9FE241FD961BB0A9B50E14D9">audienceSignalWithData </li> 
      <li id="li_3545CB51B6B7409D8CE2B97E291267E6">audienceReset </li> 
     </ul> </p> <p><b>訪客 ID 服務方法</b> </p> <p> 
     <ul id="ul_746B8A36715D4075B11C42F9FE82F538"> 
      <li id="li_A15AFA632E8C4C8D931CAB48B9A29ADB">visitorGetMarketingCloudId </li> 
      <li id="li_D80DD8DDE6AB4CB6BEE37DAA9BB28A98">visitorSyncIdentifiers </li> 
     </ul> </p> <p><b>應用程式延伸模組和 Apple Watch 方法</b> </p> <p> 
     <ul id="ul_66B1E1AC4A6D4970B0C77A46EA14ABA7"> 
      <li id="li_1EA7A063FED04E0585D463837A7555CE">setAppGroup </li> 
      <li id="li_5869EAB018C94EE4AC28B3EE62D9F0EF">syncSettings </li> 
      <li id="li_983A98CAEBAD404EBCE1D70CB0B52BA3">initializeWatch </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.6 {#section_D091872501DA49C1A18CDC33C84B8256}

[!DNL iOS] SDK 4.6 版 (2015 年 9 月 17 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_084C27B1A75A4A2EB84822242E37ED35"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>推送訊息至 <span class="keyword">Analytics</span> 區段 </p> </td> 
   <td colname="2"> <p> <span class="keyword">Adobe Mobile Services</span> 與 <span class="keyword">Adobe Mobile</span> SDK 允許您傳送推送訊息至 <span class="keyword">Analytics</span> 區段。SDK 也允許您輕鬆報告已開啟您應用程式的使用者，作為開啟推送訊息的結果。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>贏取方法 </p> </td> 
   <td colname="2"> <p>就像使用者已按一下連結，讓開發者得以展開應用程式贏取促銷活動。此方法有助於建立手動贏取連結，並且可由您親自將應用程式商店重新導向。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>回傳 </p> </td> 
   <td colname="2"> <p>回傳可讓您將 SDK 所收集的資料傳送至個別的第三方伺服器。運用相同的觸發器和您使用的特性來顯示應用程式內訊息，您便可以設定 SDK 將自訂資料傳送至第三方目的地。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>識別碼 </p> </td> 
   <td colname="2"> <p>新增以下新識別碼: </p> <p> 
     <ul id="ul_22EF89556F6B481ABE0D1B9C5EE70B55"> 
      <li id="li_C41F6FAC0B334B89B8B5D1A517CA2301"> <code> setPushIdentifier</code> </li> 
      <li id="li_B7893FB0453340EDB4290BC0B47BF096"><code> setAdvertisingIdentifier</code> </li> 
      <li id="li_85EF5F2B8837497B90F782946283622E">此  <code> trackPushMessageClickThrough</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>適用於 WatchOS 2 的 WatchKit 支援 </p> </td> 
   <td colname="2"> <p>新增適用於 WatchOS 2 的 WatchKit 支援。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.5 {#section_53DFAF8CFD614F69B3168014EF84DE9F}

[!DNL iOS] SDK 4.5 版包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_A69D0B8DA45348B8A5D6A014126F97C2"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> iOS 延伸功能</span> </p> </td> 
   <td colname="2"> <p>在 <span class="keyword">iOS</span> SDK 4.5 版中啟動新的 <span class="keyword">iOS</span> 擴充功能，可讓您從 Apple Watch 應用程式、Today Widget、Photo Editing Widget 和所有其他 <span class="keyword">iOS</span> 擴充應用程式上收集使用資料。 </p> <p>我們強烈建議您使用 <span class="keyword"> iOS</span> SDK，避免使用您自己的包裝函式。 </p> <p>Apple 提供一組讓 Watch 應用程式與容納應用程式通訊的 API (將請求傳送給容納應用程式，然後再接收回應)。 </p> <p>雖然您可以將追蹤資料當做字典，從 Watch 應用程式傳送到容納應用程式，然後再呼叫容納應用程式上的任何追蹤方法來傳送資料，不過這個解決方案有其限制。 </p> <p>在大部分的情況下，當使用者使用 Watch 應用程式時，容納應用程式會在背景執行，此時唯有呼叫 <code> TrackActionInBackground</code>、<code> TrackLocation</code> 及 <code> TrackBeacon</code> 是安全的。呼叫其他追蹤方法會干擾生命週期資料，所以若要從 Watch 應用程式傳送資料，您應該只使用這三個方法。 </p> <p>即使這三個追蹤方法已能滿足您的需求，我們仍建議您使用 <span class="keyword">iOS</span> SDK，因為適用於 Watch 應用程式的 SDK 包含應用程式內傳訊之外的所有 <span class="keyword">Mobile</span> 功能。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.4 {#section_0B7A98761BF0400986C368E154A3B00B}

<table frame="all" colsep="1" rowsep="1" id="table_812CAB7DDC364DAABB7CDEDE55532E39"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 使用生命週期量度的自訂資料 </p> </td> 
   <td colname="2"> <p>您現在可使用生命週期量度來納入自訂內容資料的變數。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> PhoneGap</span> 支援信標追蹤功能 </p> </td> 
   <td colname="2"> <p>您現在可在 <span class="keyword">PhoneGap</span> 中使用 <code> trackBeacon</code> 和 <code> clearCurrentBeacon</code> 呼叫。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.3 {#section_0FD2B2C4F54E4A9E8C6D0CD2F103BB9A}

發行日期: **2014 年 11 月 24 日**

* 新增 - Adobe Experience Cloud ID 整合
* 已清楚描述除錯記錄

## 版本 4.2 {#section_806710F7720C410DAB46376C0A7A283E}

發行日期: **2014 年 10 月 16 日**

* 新增 - 應用程式內訊息功能。
* 新增 - 現在啟動應用程式時可指定設定檔的位置。
* 新增 - 現在不必使用新的設定檔，興趣點就能自動更新。
* 新增 - 現在會以 HTTP POST 要求的形式傳送 [!DNL Analytics] 呼叫。
* 已清除 debugLogging 啟用後的記錄訊息，且已新增更多的詳細記錄功能。
* 多項效能與穩定性增強功能。

## 版本 4.1.3 {#section_8D679B676F604E0B9A64748569185368}

發行日期: **2014 年 9 月 18 日**

* 解決 Audience Manager 提交信號呼叫或 [!DNL Target] 載入要求呼叫，若因未知的網路錯誤而失敗所可能發生當機的問題。

## 版本 4.1.2 {#section_6128902E5AE142C4A95D2FB3053188F8}

發行日期: **2014 年 8 月 5 日**

* 已解決 privacyStatus:optunknown 和 offlineEnabled:false 的特定設定可能鎖死的問題。

發行日期: **2014 年 8 月 4 日**

* 已解決當反向連結逾時大於/等於 5 秒，且離線追蹤無法啟用時，可能導致「生命週期」點擊無法傳送的問題。

發行日期: **2014 年 4 月 17 日**

* 藍牙信標追蹤功能。
* 應用程式收購分析.
* 對於啟用時間戳記的應用程式，其當機點擊可追溯至正確的作業。
* 對於啟用時間戳記的應用程式，其在點擊內所傳送的先前作業可追溯至正確的作業(而不再是先前的作業)。
* 點擊批次處理程序。

## 版本 4.0.2 {#section_B78AE82CDFAD44DCAC6D61E0B80BF4C8}

發行日期: **2014 年 2 月 20 日**

* 已解決相同的媒體項目依序開啟，且不事先關閉先前項目時，可能導致不正確行為的問題。

## 版本 4.0.1 {#section_A6D017015BC742F69B6EE4A461D00FD7}

發行日期: **2014 年 1 月 30 日**

* 已解決資料庫已損毀時可能導致傳送多次點擊的問題。
* 已解決裝置的時間設定若不正確時，可能導致作業長度平均較長的問題。

## 版本 3.3.2 {#section_6D12768F20C44BA4A0D1EA607D367147}

發行日期: **2014 年 1 月 30 日**

* 已解決裝置的時間設定若不正確時，可能導致作業長度平均較長的問題。

## 版本 4.0.0 {#section_79DCFAAF1DCB404898E3BE389AC835A6}

發行日期: **2013 年 9 月 27 日**

Experience Cloud 解決方案適用的 [!DNL iOS] SDK 4.x 現已提供下列新功能:

* 大幅增強效能。所有處理作業均在背景執行緒中執行，SDK 執行緒完全安全。
* 地域位置與興趣點
* 期限值
* 計時事件
* 加入/退出管理
* Audience Manager 支援
* 生命週期量度傳遞給 [!DNL Target] 做為 mbox 參數
* 標準化內容資料與處理規則

## 版本 3.3.0 {#section_28FB7CD64D6C49BF93E321587F1E8950}

發行日期: **2013 年 9 月 23 日**

* 已新增對 ARM64 和 X64 模擬器架構 (iPhone 5s) 的支援

## 版本 3.2.1 {#section_3E73A76401664C54B32C7F3BE8BE36E3}

發行日期: **2013 年 8 月 16 日**

* 已移除未使用的代碼以進行最佳化
* 已修正 clearVars 在執行緒的環境下使用時可能會發生當機的問題。

## 3.2 版 {#section_A51E0EB26EF246DABE27234C77598D99}

發行日期: **2013 年 8 月 6 日**

* 已新增對 Adobe Audience Manager 的支援。
* 現在當生命週期追蹤啟用時，生命週期資料會與 [!DNL Target] Mbox 要求一同傳送。

## 版本 3.1.8 {#section_849BCD1D4379433D874B8A0E0099E2B1}

發行日期: **2013 年 6 月 20 日**

* 修正在 [!DNL iOS] 5.0 以下的裝置中使用 3.1.7 版會導致生命週期問題的錯誤。

## 版本 3.1.7 {#section_EC59B76EE3A343D5921E906EB0A8DB49}

發行日期: **2013 年 5 月 23 日**

* 已新增代碼，以免過多的生命週期點擊透過位置通知及啟動應用程式的「書報攤」通知傳送。

## 版本 3.1.6 {#section_4617D7A41D0841BEBD5829001DC74854}

發行日期: **2013 年 4 月 18 日**

* 已修正導致先前作業長度有時會計算錯誤的問題。

## 版本 3.1.5 {#section_620AA594868F47619A514AF3C1EAC93B}

發行日期: **2013 年 3 月 21 日**

* `ADMS_Measurement.visitorID` 現在會預先填入預設值。

## 版本 3.1.4 {#section_B04D1A4858A84A19AA65A57609C9F53F}

發行日期: **2013 年 2 月 21 日**

* 已取代 `offlineThrottleDelay`，因為此設定由於執行緒最佳化而不再需要。此設定仍然存在，以保留回溯相容性，但不再有任何作用。

## 版本 3.1.3 {#section_CCFAE5A29FB14DAD9A9F14FE8EE09B75}

發行日期: **2012 年 11 月**

* 已修正手動設定「產品」變數時，可能發生 EXEC_BAD_Access 的問題。
* 已修正 mbox 逾時可能發生無效選擇器當機的問題。
* 已對媒體測量新增廣告追蹤支援。

## 3.1.2 版 {#section_25C8A6B67AB9487BA5DEB4DB196AE4BC}

發行日期: **2012 年 10 月**

* 新增 `lifecycleSessionTimeout` 組態變數，該變數可讓您指定在兩次應用程式啟動之間需經過的時間長度 (單位為秒)，超過該秒數後，該次啟動即視同新的作業階段。
* 修正媒體模組問題，該問題會導致在測量物件上設定的事件覆寫媒體模組所設定的事件。
* 修正會導致透過 [!DNL Target] 整合配置 mbox 時發生例外狀況的問題。

## 3.1.0 版 {#section_0F3E939885DE4DF1B7430DF5F5749AD2}

發行日期: **2012 年 9 月**

* 新增 armv7s 架構的支援。
* 移除 armv6 架構的支援。
* 目前支援的最低 [!DNL iOS] SDK 為 4.3

## 版本 3.0.2 {#section_1224693620524D6C8CCAB7707483536E}

發行日期: **2012 年 8 月**

* 使用媒體監視器委派的客戶無法再看見兩個關閉事件。
* 解決關閉點擊有時導致媒體監視器出現迴路狀況的問題。

## 3.0 版 {#section_D28F56359EC04EDC8521BE93750AE90D}

發行日期: **2012 年 7 月**

首次發行。

**增強功能**

* 新增「自動追蹤」功能。
* 將最終組建的程式庫大小縮小為大約 90k。
* 新增 "trackEvents" 和 "trackAppState" 方法。
* 改進上下文資料支援和功能。(建議對所有傳送的資訊使用上下文資料)。
* 簡化追蹤作業，以便在 5 分鐘內完成基本追蹤實施。

**變更**

* [!DNL AppMeasurement] 類別現在稱為 ADMS_Measurement。
* ADMS_Measurement 現在作為適當的單例。
* 變更 eVars、props、lists、hiers、pevs 的 getter 和 setter。
* 傳入 "track" 呼叫的所有變數都只會針對該呼叫而持續存在。

**已修改下列變數**

| 舊版 (2.x 版) | 目前 (3.x 版) |
|---|---|
| account | reportSuiteIDs |
| dc | dataCenter |
| pageName | appState |
| contextData | persistentContextData |
| state | geoState |
| zip | geoZip |
| server | appSection |
| debugTracking | debugLogging |
| trackOffline | offlineTrackingEnabled |
| offlineLimit | offlineHitLimit |
| OfflineThrottleDelay | offlineThrottleDelay |

**已重新規劃下列變數:**

* linkURL (與 trackLinkURL 一起傳送:)
* linkName (與 trackLinkURL 一起傳送:)
* linkType (與 trackLinkURL 一起傳送:)
* lightProfileID (與 trackLight 一起傳送:)
* lightStoreForSeconds (與 trackLight 一起傳送:)
* lightIncrementBy (與 trackLight 一起傳送:)
* trackingServerSecure (trackingServer 使用於開啟 ssl 時)

**已移除下列變數:**

* timestamp
* userAgent
* dynamicVariablePrefix
* visitorNamespace
* pageURL
* pageType
* referrer
* linkLeaveQueryString
* usePlugins
* useBestPractices (由「自動追蹤」處理)
* delegate
* retrieveLightData
* deleteLightProfiles
* retrieveLightProfiles

## 舊版 iOS (2.x){#section_5F76C3DA854D4BAEA636A68B3811142B}

下列發行說明適用於 [!DNL iOS] 適用的 [!DNL AppMeasurement] 的 2.x 版。建議客戶盡可能升級至 3.x 版。

## 版本 2.1.12 {#section_85C073B86B684D52A14E8038379F56DD}

發行日期: **2012 年 4 月**

* 新增支援 視訊測量。
* 解決 linktrackvars 和上下文資料相關問題。
* 增強其他幾項效能。

## 版本 2.1.11 {#section_F0AF2D4E5F504D798EEB95BE8FE61B4C}

發行日期: **2012 年 3 月**

* 修正離線追蹤在某些情況下會停止傳送資料的問題。

## 版本 2.1.10 {#section_07C24EC83AA94A6AA6AB3DE7E8D6227F}

發行日期: **2012 年 2 月**

* 修正當多個執行緒嘗試同時進行追蹤呼叫時，有時候會發生 EXC_BAD_ACCESS 例外的問題。
* 新增時間戳記至搭配光源追蹤呼叫 (trackLight) 的變數。

## 版本 2.1.8 {#section_ACC6974CE3F741E58786CA8048F04521}

發行日期: **2012 年 1 月**

* 大幅增加追蹤執行緒的效能。
* 將離線點擊儲存位置移至不與 iCloud 同步的位置，以符合 iCloud 最佳實務。
* 將程式庫更新為 Apple Fat Binary 格式，因此您不須再為建置架構包含特定的程式庫。

## 版本 2.1.6 {#section_63B4967C537847C28D33EBB92CC15695}

發行日期: **2011 年 11 月**

* 新增對 [!DNL iOS] 5 的支援。
* [!DNL iOS] 的 [!DNL AppMeasurement] 現已更新，不再使用已遭取代的 UDID 值作為訪客 ID 的預設值。如果您在應用程式中設定了自訂訪客 ID，(例如：`s.visitorID = @12345`)，那麼您將不會受此變更影響。如果您沒有設定自訂訪客 ID，而是使用 UDID 作為訪客 ID 的值，那麼初次啟動時即會產生隨機的訪客 ID，並將其儲存於使用者預設金鑰中。此後 [!DNL AppMeasurement] 就會沿用此金鑰。標準應用程式進行備用程序時，也會儲存及還原該金鑰。

* 更新未關聯至頁面檢視的 [!DNL iOS] Best Practices 外掛程式呼叫，以使用 trackLink 傳送點擊。如此可防止這些點擊以「應用程式名稱/版本」名稱的預設值來記錄頁面檢視。

## 版本 2.1.3 {#section_E39666D780554B7398900C39C285CDB8}

發行日期: **2011 年 10 月**

* 改進委派處理。這可修正 [!DNL iOS] Best Practices 外掛程式將應用程式帶出背景時當機的問題。

## 版本 2.1.2 {#section_21014073AF804EFC8231047D8847485C}

發行日期: **2011 年 9 月**

* 更新標題以便使用 prop 和 eVar 51-75。

## 版本 2.1.1 {#section_8FB3D7C77C884E2AB982103BF7E3312A}

發行日期: **2011 年 8 月**

* 在執行報表時搜尋報表套裝和量度的功能。
* 支援可提升伺服器端處理規則的上下文資料 (僅限 v15)。
* 支援輕伺服器呼叫 (目前測試中)。

