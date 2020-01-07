---
description: Android 行動程式庫的累積發行說明。
solution: Analytics,Experience Cloud
subtopic: Release notes
title: Android
topic: Developer and implementation
uuid: 32232d28-3459-4f78-bb00-ca3163c63461
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Android{#android}

Android 行動程式庫的累積發行說明。

> [!NOTE]若要尋找目前的程式庫版本，請開啟偵錯記錄功能。

您可在 [GitHub](https://github.com/Adobe-Marketing-Cloud/mobile-services) 和 [Developer Connection](https://marketing.adobe.com/developer/gallery/app-measurement-for-android-1) 中下載行動程式庫。

## 版本 4.13.4 {#section_E4743079D8E64B9C890180A025C94B44}

[!DNL Android] SDK 4.13.4 版 (2017 年 2 月 16 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_C0197701CB9B45E596818AF0BE5AC4F2"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 應用程式內傳訊 </p> </td> 
   <td colname="2"> <p> 修正在確定對象時無法使用正確應用程式版本的問題。當使用者有應用程式版本升級但未啟動新的 Lifecycle 時，就會發生此問題。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Lifecycle </p> </td> 
   <td colname="2"> <p> 修正可能無法正確回報應用程式版本升級的問題。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>贏取 </p> </td> 
   <td colname="2"> <p> 修正導致延遲深層連結無法在第一次啟動時觸發的錯誤。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.13.3 {#section_1C235192E9FB46E2A651017C1CF24A7F}

[!DNL Android] SDK 4.13.3 版 (2017 年 1 月 19 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_5E744C8C9D064E999EB5055A8E3A99C5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 應用程式內傳訊 </p> </td> 
   <td colname="2"> <p> 修正無點進按鈕的警報訊息無法顯示的問題。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Analytics</span> </p> </td> 
   <td colname="2"> <p> 改善唯讀資料庫存取的處理方式。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>通用連結 </p> </td> 
   <td colname="2"> <p> 修正導致附加至贏取資料的延遲深層連結連續啟動的錯誤。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.13.2 {#section_CEA2FF01EA414A32A8D164D981FBE71F}

[!DNL Android] SDK 4.13.2 版 (2016 年 11 月 10 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_812CAB7DDC364DAABB7CDEDE55532E39"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 訪客 ID服務 </p> </td> 
   <td colname="2"> <p>在 <code> adobe_mc</code>   參數中新增時間戳記和 Experience Cloud 組織 ID。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 深層連結 </p> </td> 
   <td colname="2"> <p>在呼叫 <code> trackAdobeDeepLink</code> 時，系統已能適當處理帶有「<code> adb</code>」和「<code> ctx</code>」首碼的變數。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.13.1 {#section_647C43BA95A3485381AC2E8DEAA6D2E4}

[!DNL Android] SDK 4.13.1 版 (2016 年 10 月 20 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_1D1AFD90F8BB4F59869FD417ED9C45AB"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>贏取 </p> </td> 
   <td colname="2"> SDK 現在支援讓 <code> AdobeDataCallback</code> 叫用適當地處理自訂贏取資料。 </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>贏取 </p> </td> 
   <td colname="2"> SDK 現在能儲存 Google Play 反向連結變數和自訂變數，並在 <code> AdobeDataCallback</code> 叫用中將它們適當地傳回。 </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>目標 </p> </td> 
   <td colname="2"> 訪客 ID 服務參數現在可以透過 <span class="keyword"></span> 的<code> mboxParams</code>目標請求傳送。 </td> 
  </tr> 
 </tbody> 
</table>

**錯誤修正**

* 修正傳送給電話的資料請求有時候會逾時的錯誤。

## 版本 4.13.0 {#section_03370D8F93AE4B7A81C4B03910086556}

[!DNL Android] SDK 4.13.0 版 (2016 年 9 月 15 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_AACF8B9BE89A4057B0396F487F82CF99"> 
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
  <tr rowsep="1"> 
   <td colname="1"> <p>追蹤深層連結 </p> </td> 
   <td colname="2"> <p>新功能: 已新增可追蹤第三方延遲深度連結的功能。 </p> <p> 
     <ul id="ul_DA54F09098A546B6A320E6B9F2937DAD"> 
      <li id="li_B483AEBE02F34E21B2CC731FC77448E8"><code> processAdobeDeepLink</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.12.0 {#section_3FBC1C24267141C08A60E288662160D8}

[!DNL Android] SDK 4.12.0 版 (2016 年 8 月 18 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_3BDD15254859475CBE5E27870619FF3A"> 
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
 </tbody> 
</table>

## 版本 4.11.0 {#section_34B295F3697F4AD6B6A6B8DD70AD1ECA}

[!DNL Android] SDK 4.11.0 版 (2016 年 6 月 22 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_C3DC3890E81744828DE8946AE8067E1A"> 
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
      <li id="li_A4B0ECDF200C438BB1AB24D613453A68"><code> loadRequest</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.10.0 {#section_262928ABA971490EA6B8E277E17BDD89}

[!DNL Android] SDK 4.10.0 版 (2016 年 5 月 20 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_E6B19BD9903A41D9AAF0035CD66756B5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Target 方法 </td> 
   <td colname="2"> <p>已新增 <code> loadRequest</code> 方法的新語法和範例。 </p> <p>已新增下列新 <span class="keyword">Target</span> 方法: </p> <p> 
     <ul id="ul_B32C3B3931764F21948E36384B775642"> 
      <li id="li_3421E7F78F3A4DDA8FF004903FC8C75E">setThirdPartyID </li> 
      <li id="li_0836075699C5480EB3D6B742FCF6D508">getThirdPartyID </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.9.0 {#section_7393D3A5EA61431D9E7C07ECE176D17C}

[!DNL Android] SDK 4.9.0 版 (2016 年 5 月 5 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_7D893A6E12554E9CA9AF2B03DA4C1A4B"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> 退出與隱私權設定 </td> 
   <td colname="2"> <p>您可以在應用程式中實施深層連結，將使用者導向應用程式或網頁連結目標。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.8.3 {#section_9BB3DFBECC434AC6B3D7C18AA9BC895C}

[!DNL Android] SDK 4.8.3 版 (2016 年 2 月 18 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_6DE145BC30154B9FADCE584A9737018D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> 退出與隱私權設定 </td> 
   <td colname="2"> <p>從 <span class="keyword">Android</span> SDK 4.8.3 版開始，透過 <code> setPrivacyStatus</code> 方法設定隱私權設定，將影響 <span class="keyword">Analytics</span>、<span class="keyword">Target</span> 和 <span class="keyword">Audience Manager</span> 中的活動。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.8.0 {#section_18FA091344644B43AA0E226241FF90DC}

[!DNL Android] SDK 4.8.0 版 (2015 年 11 月 2 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_C47B9AEB2BB649CFA1D5CF04093B497B"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> 新的 Experience Cloud 訪客 ID 服務方法 </td> 
   <td colname="2"> <p>已新增下列方法:  </p> 
    <ul id="ul_6B85F8A4826642BEB373225CA760D799"> 
     <li id="li_72B94B8CECB94229827BFCB06671DFC9"><code> syncIdentifer</code> </li> 
     <li id="li_CD0C6B6CEA064FDD8B109E01AEC63F5C"><code> syncIdentifiers</code> </li> 
     <li id="li_620A2D94F97A4451919F0867CA82B25D"><code> getIdentifiers</code> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> 新的 ADBMobile JSON Config 變數 </td> 
   <td colname="2"> <p>已新增下列變數:  </p> 
    <ul id="ul_7FF76521C59343A4ABC9573C3CD5DC38"> 
     <li id="li_1381E3EF082B4D7DBD131D8EC62F94D2"><code> analyticsForwardingEnabled</code> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"><span class="keyword"> PhoneGap 外掛程式方法</span> </td> 
   <td colname="2"> <p>已新增下列新方法 </p> <p><b>設定方法</b> </p> <p> 
     <ul id="ul_98C5E7B5C79446EEA00F0E7CBC213301"> 
      <li id="li_B403C06E57A0450CBB4ABAD45170C681">setPushIdentifier </li> 
      <li id="li_6D76C40601544D4FA13FD44F390C83CE">setAdvertisingIndentifier </li> 
      <li id="li_7D03005DBD9E4AC7BB78BA162CDC8153">keepLifecycleSessionAlive </li> 
      <li id="li_3DDE07508B764E679AF2ACECC4D935CB">trackingSendQueuedHits </li> 
     </ul> </p> <p><b>Target 方法</b> </p> <p> 
     <ul id="ul_9B6002F5642B4D888FBD0A8D44EF32DB"> 
      <li id="li_5C1C9EA770E048E48723528F346712B4">targetClearCookies </li> 
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
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.6.1 {#section_98CC97CF0F0C48F7855130044386845A}

[!DNL Android] SDK 4.6.1 版 (2015 年 9 月 24 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_80693083398F472F8A4E7861606E602D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Android SDK 版本 4.6.1</span> </p> </td> 
   <td colname="2"> <p>SDK 4.6.0 或較舊版本支援 <span class="keyword">Android</span> 2.2 (API 8) - <span class="keyword">Android</span> 5.1.1 (API 22) </p> <p>SDK 4.6.1 或更新版本支援 <span class="keyword">Android</span> 2.3 (API 9) 或更新版本 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.6 {#section_ADF6F871CF3C4E2381464D62DA6E1EB1}

[!DNL Android] SDK 4.6 版 (2015 年 9 月 17 日) 包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_35D0692698EF49AE8204F2AEB57CABD7"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>推送訊息至 <span class="keyword">Analytics</span> 區段 </p> </td> 
   <td colname="2"> <p><span class="keyword">Adobe Mobile Services</span> 與 <span class="keyword">Adobe Mobile</span> SDK 允許您傳送推送訊息至 <span class="keyword">Analytics</span> 區段。SDK 也允許您輕鬆報告已開啟您應用程式的使用者，作為開啟推送訊息的結果。 </p> </td> 
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
     <ul id="ul_84AD959FC65C445BB119F69657AB4AF8"> 
      <li id="li_418FD9EE570F491F9704F72AC70EEE8D"><code> setPushIdentifier</code> </li> 
      <li id="li_B350606A504449E5AAE208B1E590E2CA"> <code> submitAdvertisingIdentifierTask</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.5 {#section_6E7614D4AEA24B7E81C4FC094882F062}

[!DNL Android] SDK 4.5 版包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_BF98A1E904EB4314828AC58A2A6E7016"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Android 穿戴式延伸功能</span> </p> </td> 
   <td colname="2"> <p>在 <span class="keyword">Android</span> SDK 4.5 版中啟動新的 <span class="keyword">Android</span> 擴充功能可讓您透過 <span class="keyword">Android</span> 穿戴式應用程式中收集資料。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.4 {#section_8D7FC183081E4BCFA8ADC33FB55E057C}

[!DNL Android] SDK 4.4 版包含下列變更:

<table frame="all" colsep="1" rowsep="1" id="table_E8628F3806E24A0FB7157847D97C7B7A"> 
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

## 版本 4.3 {#section_789F3DA3DD3146CAA126B303F62D1A1A}

發行日期: **2014 年 11 月 24 日**

* 新增 - Adobe Experience Cloud ID 整合
* 已清楚描述除錯記錄
* 已解決在查看應用程式內訊息時可能會當機的問題

## 版本 4.2 {#section_EDF95BA0301C4B54AAE839768917D439}

發行日期: **2014 年 10 月 16 日**

* 新增 - 應用程式內訊息功能。
* 新增 - 現在啟動應用程式時可指定設定檔的位置。
* 新增 - 現在不必使用新的設定檔，興趣點就能自動更新。
* 新增 - 現在會以 HTTP POST 要求的形式傳送 [!DNL Analytics] 呼叫。
* 已解決在特定情況下可能導致應用程式當機且無法追蹤的問題。
* 已清除 debugLogging 啟用後的記錄訊息，且已新增更多的詳細記錄功能。
* 多項效能與穩定性增強功能。

## 版本 4.1.7 {#section_DD98F9A4F00A457AA79D223CB1113A06}

發行日期: **2014 年 8 月 4 日**

* 已解決當反向連結逾時大於/等於 5 秒，且離線追蹤無法啟用時，可能導致「生命週期」點擊無法傳送的問題。

## 版本 4.1.6 {#section_B665DF1A4FB249539D73569B52FA8786}

發行日期: **2014 年 7 月 17 日**

* 已新增保護功能，以解決資料庫已損毀或無法建立時所產生的例外狀況。
* 已新增保護功能，以解決無法載入設定 (一般是因為無內容) 時可能發生的問題。
* 已新增保護功能，以解決更新逾時動作的內容資料時可能發生的例外狀況。

## 版本 4.1.1 {#section_E5EFA05CEE9D486BA6B5C12B1102C117}

發行日期: **2014 年 4 月 23 日**

* 已修正當反向連結追蹤功能已啟用，且在生命週期開始前呼叫追蹤功能時所可能發生的問題。

## 版本 4.1.0 {#section_266B62F5B6A44F5F8E6AB8ED1870C4A3}

發行日期: **2014 年 4 月 17 日**

* 新增 - 藍牙信標追蹤功能。
* 新增 - 對於啟用時間戳記的應用程式，其當機點擊可追溯至正確的工作階段。
* 新增 - 對於啟用時間戳記的應用程式，其在點擊內所傳送的先前作業可追溯至正確的工作階段(而不再是先前的作業)。
* 新增 - 點擊批次處理。
* 使用可設定的逾時修正 Google Play 反向連結追蹤功能，以允許延遲的 Google 反向連結資料。
* 解決可能在特定情況下出現的 StrictMode 警告。
* 解決某些方法依特定順序呼叫時極少導致程式庫鎖定的問題。

## 版本 4.0.4 {#section_DCFAC758872D42F0BF0CCFCDDEA05E41}

發行日期: **2014 年 2 月 24 日**

* 已解決若已呼叫停止，稍後再呼叫關閉，且之間並無任何呼叫時，可能導致媒體播放時間延續的問題。
* 已解決即使媒體一段時間不播放仍會傳送媒體關閉點擊的問題。

## 版本 4.0.3 {#section_FCC3D7D22EBF4A2FA949A4E88AD89F5C}

發行日期: **2014 年 2 月 20 日**

* 新增網路程式碼安全，以防止由 [!DNL Android] 錯誤所導致的當機: https://code.google.com/p/android/issues/detail?id=54072

## 版本 4.0.2 {#section_5A7F4D5D9CBD4B79B3B590A2C3F4D0F9}

發行日期: **2014 年 1 月 30 日**

* 已解決資料庫已損毀時可能導致傳送多次點擊的問題。
* 已解決裝置的時間設定若不正確時，可能導致作業長度平均較長的問題。

## 版本 3.2.5 {#section_A6E60DB42241481DA62F660344128F53}

發行日期: **2014 年 1 月 30 日**

* 已新增保護功能，防止已損毀的資料庫導致重複點擊。
* 已新增作業長度的上限，以免裝置時間不正確時作業時間極長。

## 版本 4.0.1 {#section_5F58DBABDAA049FE9070E46989B2E9A9}

發行日期: **2013 年 11 月 14 日**

* 已解決 trackLocation 資料在特定地區中格式不正確的問題。

## 版本 4.0.0 {#section_79DCFAAF1DCB404898E3BE389AC835A6}

發行日期: **2013 年 9 月 27 日**

Experience Cloud 解決方案適用的 [!DNL Android] SDK 4.x 現已提供下列新功能:

* 大幅增強效能。所有處理作業均在背景執行緒中執行，SDK 執行緒完全安全。
* 地域位置與興趣點
* 期限值
* 計時事件
* 加入/退出管理
* Audience Manager 支援
* 生命週期量度傳遞給 [!DNL Target] 做為 mbox 參數
* 標準化內容資料與處理規則

## 版本 3.2.3 {#section_E3464DDC3B4844CF9CC5FC3E35C5C785}

發行日期: **2013 年 9 月 23 日**

* 已修正 Audience Manager 中不允許參數中有空值或空密鑰的錯誤。

## 版本 3.2.2 {#section_7D631AA2474F4DBAA043703629E3ECC6}

發行日期: **2013 年 9 月 12 日**

* 已修正 linkTrackEvents 中的媒體事件未新增至請求的錯誤。
* 已修正 ContextData 在傳遞至追蹤呼叫後經過修改時，可能發生與其相關的例外狀況。

## 版本 3.2.1 {#section_D269F9145B2844B6855423A30B125D5C}

發行日期: **2013 年 8 月 16 日**

* SSL 連線現已採用嚴格主機驗證
* 已修正網路斷線且離線追蹤已啟用時，數秒後會快速重試點擊的錯誤。

## 3.2 版 {#section_ABD4D192E3FF4240B1451262EAEE4F17}

發行日期: **2013 年 8 月 6 日**

* 已新增對 Adobe Audience Manager 的支援。
* 現在當生命週期追蹤啟用時，生命週期資料會與「目標 Mbox」請求一同傳送。
* 已解決可能導致 SQLite 強制關閉游標而產生不必要記錄項目的問題。

## 3.1.0 版 {#section_836B4F580B1C436FABD524A91857F882}

發行日期: **2013 年 6 月 13 日**

* 已更新離線儲存以使用 SQLite。
* 已修正離線限制可重設為預設值 (1000) 的錯誤。
* 已更新 startActivity，現已接受活動或應用程式內容。
* 已修正設定 lifcycleSessionTimeout 為 0 會導致整個應用程式發生多組啟動事件的錯誤。

## 版本 3.0.8 {#section_51F50CD81C6A40C8BCF62F6F332A0800}

發行日期: **2013 年 4 月 18 日**

* 已修正部分 UTF8 字元的編碼問題。

## 版本 3.0.7 {#section_0F3FEE2886EB4AB7BA288891FF6B6BCD}

發行日期: **2013 年 4 月 18 日**

* 已修正導致先前作業長度有時會計算錯誤的問題。
* 新訪客 ID 將不再依 deviceID 或 subscriberID 為根據。
* 已修正對變數中的特殊字元進行編碼時可能發生當機的問題。

## 版本 3.0.6 {#section_72F3F9CB95BF4076AD882B3270F77B87}

發行日期: **2013 年 3 月 21 日**

* 已修正未事先設定 visitorID 前即無法讀取的問題。
* 已變更部分錯誤記錄訊息中的命名規則，以詳細說明。
* 已變更多個基底類別的存取性，以避免造成混淆。
* 多項效能增強功能

## 版本 3.0.5 {#section_0540FF6477D74D1F8274E9340EDE7E16}

發行日期: **2013 年 2 月 21 日**

* 已取代 `offlineThrottleDelay`，因為此設定由於執行緒最佳化而不再需要。此設定仍然存在，以保留回溯相容性，但不再有任何作用。
* 修正離線點擊快取的潛在同步問題。
* 闡明設定超過 5 個階層變數時的警告訊息。
* 修正可能導致在 [!DNL Android] 4.0 以上的版本誤報 OSVersion 的問題。
* 增強多項效能。
* 解決可能由格式錯誤的 url 所造成的潛在例外狀況。

## 版本 3.0.4 {#section_69ADA2ACD9DE436692152C3836B14EEF}

發行日期: **2012 年 11 月**

* 新增 `lifecycleSessionTimeout` 組態變數，該變數可讓您指定在兩次應用程式啟動之間需經過的時間長度 (單位為秒)，超過該秒數後，該次啟動即視同新的作業階段。
* 新增使用 `lifecycleSessionTimeout` 組態設定來設定作業長度計算逾時值的功能。
* 修正安全性問題。

## 版本 3.0.3 {#section_F16E1A36AE3F4CBC92E4925D6DCCFADE}

發行日期: **2012 年 10 月**

* 新增對 [Google Play 促銷活動追蹤](https://marketing.adobe.com/resources/help/zh_TW/sc/appmeasurement/android/referrer.html)的支援。

## 版本 3.0.2 {#section_CB24859B34804F9391BA1BF8DF29CC86}

發行日期: **2012 年 9 月**

* 已解決關閉點擊有時導致媒體監視器出現迴圈狀況的問題。

## 版本 3.0.1 {#section_541CE15B340E414AA018A0EFAEE459F0}

發行日期: **2012 年 8 月**

* 內容覆蓋參數現在是以 `Hashmap<String, Object>` (`Hashmap<String, String>`) 的形式傳送。

## 3.0 版 {#section_2955C0AF3A23476B8CF06C469DE3284C}

發行日期: **2012 年 7 月**

首次發行。

## 舊版 Android (1.x){#section_F2CC015616184D55AC6D6529DFC9A18B}

下列發行說明適用於 [!DNL Android] 適用的 [!DNL AppMeasurement] 的 1.x 版。建議客戶盡可能升級至 3.x 版。

## 版本 1.2.3 {#section_5189CCE11EEF4350844B1490D0A9F534}

發行日期: **2012 年 3 月**

* 修正在使用「上下文資料」傳遞資料時，有時會出現例外的問題。

## 版本 1.2.2 {#section_C42925D94F3A429EB1299B96A6EEF6DF}

發行日期: **2012 年 2 月**

修正連結追蹤呼叫對 pev1 - pev3 值進行雙重 URL 編碼的問題。

新增時間戳記至搭配光源追蹤呼叫 (trackLight) 的變數。

## 版本 1.2.1 {#section_21845E8A7D0C48B38CB90F0D4C5696AF}

發行日期: **2012 年 1 月**

* 新增 [!DNL Android] 3.x 和 4.x 相容性。
* 在沒有 SIM 卡的 [!DNL Android] 裝置上 (例如 Kindle Fire)，實作訪客 ID 的 UUID。

## 版本 1.2 {#section_EC83BE1F00BF481EA1C74A63E4B90F65}

發行日期: **2011 年 6 月**

* 更新程式庫，當裝置中未插入 SIM 卡時，使用裝置 ID 作為 訪客 ID 值。根據預設，若未插入 SIM 卡，程式庫使用訂閱者 ID 作為未顯示的訪客 ID。

## 版本 1.1.4 {#section_C602EC5C11594669A8797B736D240D2C}

發行日期: **2011 年 4 月**

* 支援所有表格 (包含 Xoom)。
* 在執行報表時搜尋報表套裝和量度的功能。
* 支援可提升伺服器端處理規則的 contextData (僅限 v15)。
* 支援輕伺服器呼叫 (目前測試中)。
