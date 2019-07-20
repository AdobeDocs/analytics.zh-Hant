---
description: 'null'
seo-description: 'null'
seo-title: 實作Digital Sasants的Analytics
title: 實作Digital Sasants的Analytics
uuid: c61e6a1a-ec08-4936-9053-5f57223 f57 ff
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 實作Digital Sasants的Analytics

<!-- 

<p>https://wiki.corp.adobe.com/display/mobileanalytics/Analytics+for+Digital+Assistants+Whitepaper </p> 
<p>https://marketing.adobe.com/resources/help/en_US/sc/implement/digital-assistants-white-paper.html </p> 
<p>Ticket: https://jira.corp.adobe.com/browse/AN-157750 </p>

 -->

由於近期雲端運算、機器學習和自然語言處理等領域突飛猛進，數位助理已走出 Office 小幫手那樣的黑暗時代，成為日常生活的一部分。消費者開始與裝置對話，希望裝置可以自然、與人類相似的方式，傾聽、理解與回應像是「Alexa，請打開客廳燈光」或「OK Google，現在外面天氣如何啊？」等語句。

隨著這些平台變得愈加成熟，品牌便可以同樣真實與擬真的方式，向消費者展現其服務。舉例來說，消費者可能問這樣問:

* 「Alexa，我的車什麼時候需要換機油。」
* 「Cortana，我的支票帳戶餘額多少?」
* 「Siri，從我的銀行應用程式轉給小明 20 美元，付昨晚的晚餐錢。」

本白皮書提供如何充分利用 Adobe Analytics Cloud 的概述，以測量和最佳化這類型的體驗。

## 數位體驗架構概述 {#concept_26AC08D291724223A943C80B1C6F2333}

![](assets/Digital-Assitants.png)

當今大多數的數位助理都按照類似的高階架構:

1. **裝置:** 配備麥克風的裝置 (例如 Amazon Echo 或手機)，可讓使用者詢問問題。
1. **數位助理:** 這個裝置再與提供數位助理技術支援的服務互動。這個服務正是一展魔力的所在。這裡，語音被轉換成可為機器理解的意圖，進而剖析要求的詳細內容。只要理解了使用者的意圖，數位助理便將意圖和要求詳情傳遞給負責處理要求的應用程式。
1. **「應用程式」:** 應用程式可指手機應用程式或語音應用程式。應用程式負責回應要求。應用程式向數位助理回應，而數位助理再向使用者回應。

## 適合實施 Analytics 的位置 {#concept_F53A0566589042658DEA5B86B22C10CB}

其中一個最適合實施 Analytics 的位置是在應用程式內部。應用程式從數位助理接收[意圖](../../implement/c-analytics-digital-assistants/digital-assistants-white-paper.md#section_BB339BDB5C3D40C6B5C426B0E092B48A)以及意圖的相關詳細資料，並決定回應方式。

在要求的生命週期中有兩個時間點，若呼叫 Analytics Cloud，會很有幫助。

1. 一是要求傳送至「應用程式」時。如果在回應要求前需要關於使用者的額外內容，應利用 Audience Manager 的功能來取得所屬區段。
1. 一是應用程式傳回回應後。如果您只對記錄客戶行為感興趣，以便未來的最佳化作業，則在傳回回應後將要求傳送至 Adobe Analytics。這樣一來，您便擁有要求詳情和系統回應方式的完整內容。

## 全新安裝 {#section_FD63267479DB47C2A081244A3E65A0CC}

部分數位助理會在有人安裝技能時通知您，特別是在需要授權時。這時您應將內容資料設為&#x200B;*`Install`*`a.InstallEvent=1`，以傳送「安裝」事件給 Adobe。請注意，並非所有平台皆提供此功能，不過若有此功能，對於查看保留率很有幫助。下列程式碼範例會傳送&#x200B;*`Install`**`Install Date`*&#x200B;和 *`AppID`*。

**程式碼範例**

```
GET 
/b/ss/[rsid]/0?vid=[UserID]&c.a.InstallEvent=1&amp;c.a.InstallDate=2017-04-24&c.a.AppID=Spoofify1.0&c .OSType=Alexa&pageName=install 
HTTP/1.1 
Host:  
<xref href="https: sc.omtrdc.net="" " format="http"  scope="external">
  sc.omtrdc.net 
 Cache-Control: no-cache 
</xref href="https:>
```

## 多助理或多應用程式 {#section_81740741752E4142BE42DA4C9DDEEDF5}

您很有可能會為多個平台開發應用程式。最佳作法是在每個要求中納入應用程式 ID。可在 `a.AppID` 內容資料中加以設定。Follow the format of `[AppName] [BundleVersion]`, for example, BigMac for Alexa 1.2

**程式碼範例**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.Launches=1&c.Product=AmazonEcho&c.OSType=Alexa&pageName=install  HTTP/1.1 
Host: [prefix].sc.omtrdc.net 
Cache-Control: no-cache
```

```
 GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Spoofify2.0&c.a.Launches=1&c.Product=GoogleHome&c.OSType=Android&pageName=install  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## 使用者/訪客身分識別 {#section_7CE70FEB43C44B90954702CA30F87D58}

The Analytics Cloud uses the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/) (ECID) service to tie interactions across time to the same person. Most of the digital assistants will return a *`userID`* that you can use to keep the activity for different users separate in the ECID service. 在大部分情況下，這是您應傳入 ECID 服務的項目。部分平台傳回的&#x200B;*`userID`*&#x200B;會多於 100 個字元，超過 Analytics 允許的上限。If that is the case, Adobe recommends that you hash the *`userId`* to a fixed-length value using a standard hashing algorithm, such as MD5 or Sha1.

雖然您可如此使用 ECID 服務，但只有在您嘗試對應不同裝置間的 ECID 時 (例如 Web 對上數位助理) 才會提供值。若為行動應用程式 (像是深層連結)，您應照常使用 SDK，一併傳送資訊。The *`userID`*&#x200B;可附加至 ECID 服務 (使用 setCustomerID 方法)，獲得更好的裝置拼接結果。However, if your app is a service, use the *`userID`* provided by the service as the ECID, as well as setting it in the setCustomerID. 這能讓您查看對象隨時間使用數位助理的情形。

**程式碼範例**

```
GET /b/ss/[rsid]/0?vid=[UserID]&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## 作業階段 {#section_BA4F996F976043B8993F2F7D24FE27FB}

因為數位助理採對話方式運作，故通常具備作業階段的概念。例如:

**消費者:**「Ok Google，幫我叫台計程車」

**Google:**「沒問題，您希望在什麼時間搭車呢?」

**消費者:**「晚上八點半」

**Google:**「好主意，司機八點半會準時到達」

這些作業階段對於融入情境至關重要。這些階段會收集更多詳細資料，讓數位助理可以表現得更為自然。

若以對話形式實施 Analytics，您應該在新作業階段開始時執行兩項作業:

1. **存取 Audience Manager:** 取得包含使用者的相關區段，這樣您便可自訂回應。(舉例來說，此人目前符合多管道折扣資格。)
1. **傳入新作業階段或啟動事件:** 請在首次將回應傳入 Analytics 時納入啟動事件。通常可透過設定 `a.LaunchEvent=1` 的內容資料來傳送。

**程式碼範例[!DNL Launch, by Adobe]**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.LaunchEvent=1&c.Intent=[intent]&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## 意圖 {#section_BB339BDB5C3D40C6B5C426B0E092B48A}

每個數位助理都有演算法可偵測意圖，再將意圖傳遞至「應用程式」，讓應用程式知道要做哪些工作。這些意圖都以精簡方式表示要求。

舉例來說，若使用者說「從我的銀行應用程式轉給小明 20 美元，付昨晚的晚餐錢」，則意圖可能會表示為&#x200B;*另存`sendMoney`。*

以 eVar 形式傳入各個要求，便能為對話行應用程式產生各意圖的路徑報表。您也會希望確定「應用程式」可在沒有意圖的情況下處理要求。建議您傳入&#x200B;*`No Intent Specified`*，而不要將此值留白。

**程式碼範例**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

或 

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=No_Intent_Specified&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## 參數/槽/實體 {#section_041CD1730F9E4096BE75DFF2CC810852}

除了意圖之外，數位助理經常會具備一組索引鍵值配對，提供意圖的詳細資料。這些配對稱為槽、實體或參數。例如:

「Siri，從我的銀行應用程式轉給小明 20 美元，付昨晚的晚餐錢。」可能會具備下列參數:

* 人物 = 小明
* 數量 = 20
* 原因 = 晚餐

應用程式的這些配對數量通常有限。若要在 Analytics 追蹤這些配對，請將其傳入內容資料，然後將各參數對應到 eVar。

**程式碼範例**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Penmo1.0=1&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## 作業階段 {#section_17D69D6B298E46E88E175F62F1ACD831}

雖然並非所有的應用程式都能夠營利，若能試想成功的樣貌，並納入一些測量指標，仍非常重要。Adobe Analytics 除了可以測量使用者行為，亦能測量收入、廣告印象以及其他的成功形式。

## 錯誤狀態 {#section_E8EFF8D610B24DC899C34E50B058864D}

有時數位助理會提供讓應用程式不確定要如何處理的輸入給應用程式。例如，

「Siri，從我的銀行應用程式轉給小明 20 袋煤，付昨晚的晚餐錢。」

若發生這種情形，應用程式應釐清問題。此外，當應用程式回應這類要求時，您應傳送事件給 Analytics，指出應用程式產生錯誤狀態，並連同 eVar 一併傳送，指明所發生的錯誤類型。

務必納入輸入有誤的錯誤以及應用程式發生問題的錯誤。

**程式碼範例**

```
GET /b/ss/[rsid]/0/?vid=[UserID]&c.a.AppID=Penmo1.0&c.Error=1&c.ErrorName=InvalidCurrency&pageName=[intent] HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## 裝置功能 {#section_6770D82A3B0E4AD5A2172A7E67B0DF20}

在大部分的平台上，使用者對話的實際裝置並不會外露。裝置功能則會以可用介面 (例如音訊、螢幕、視訊等) 的形式外露。這項資訊很有幫助，因為這定義了與使用者互動時可以利用的內容類型。測量介面時，最好互相串連 (按字母排序)。

範例: `:Audio:Camera:Screen:Video:`

請留意開頭和結尾的冒號。These help when creating segments (for example, give me all interactions with `:Audio:` capabilities).

Amazon 功能: [https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference)

Google 功能: [https://developers.google.com/actions/assistant/surface-capabilities](https://developers.google.com/actions/assistant/surface-capabilities)

## 適用於數位助理的 Analytics 報表 {#concept_265BC8E99C5545D0A9B9412C11EE58CC}

在您實施數位助理應用程式之後，便可透過應用程式來充分利用 Adobe Analytics 的完整能力。下面列出幾個您可以利用 Analytics 來完成的範例。

## 監控意圖 {#section_6632D9F2EF9045A7A1A4263D3561C78F}

大部分應用程式具備多種意圖以及您可以完成的不同工作。You could easily use [!UICONTROL Analysis Workspace] to keep track of the top intents by instances and by users

<!-- 

<p>--- Image of Intents --- </p>

 -->

這可讓您檢視哪些是最常使用的功能，並可給您採用新功能的參考。

## 有錯誤的要求 {#section_CF1A79003E784F88A03F4EEF6CDC7A7C}

您將能夠監控錯誤，查看是否有常見位置是使用者可能會發生問題之處。

<!-- 

<p>--- Image of Errors --- </p>

 -->

## 事件之間流量 {#section_08FA8EBD384D41ED8CA52EFE438C8CD2}

在最強大的功能中，其中一件是查看意圖的流量。這有兩點好處。首先，您可在作業階段中，得知對象在對話中的意圖之間是如何流動。其次，您可查看對象長期的意圖間流量情形，得知其應用程式使用情形如何演進。

## 範例 {#concept_2B13D5E7A8E042D1A4B7BB80BBAACD12}

**預先安裝的應用程式**

<table id="table_70BF4E41D0BE4482BD925FB3A1768CE0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 「人」 </th> 
   <th colname="col2" class="entry"> 裝置回應 </th> 
   <th colname="col3" class="entry"> 動作/意圖 </th> 
   <th colname="col4" class="entry"> GET 要求 </th> 
   <th colname="col5" class="entry"> Analytics 資料 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 播放 Spoofify </p> </td> 
   <td colname="col2"> <p> 「OK，播放 Spoofify」 </p> </td> 
   <td colname="col3"> <p> 播放 </p> </td> 
   <td colname="col4"> <p> 
     <code>取得/b/ss/[rsid]/0？vid=[userId]&amp; c. a. appID= SpooofFy1.0&amp; c. a. launchEvent= Play&amp; pageName= Play&amp; pageName= PlayApp HTTP/1.1
主機：sc. omtrdc. net
快取控制項：no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_E80B0BBEBE764023BB9B49FE5F15B918"> 
      <li id="li_9BC2CCABB0ED4246A57C37633666CDE2">訪客 ID </li> 
      <li id="li_1E7F9E979A3D49CE90899CE82C70BCD0">應用程式版本 </li> 
      <li id="li_C4BD7653B0FA47F6A3E4F1FF18138F10">啟動次數 </li> 
      <li id="li_B7FA47CBD75747E8A8A25E228C90E524">意圖 </li> 
      <li id="li_48274BA200704730A22C85FD682AE3B0">回應 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 變換曲目 </p> </td> 
   <td colname="col2"> <p> 「OK，您要聽哪首歌?」 </p> </td> 
   <td colname="col3"> <p> ChangeSong </p> </td> 
   <td colname="col4"> <p> 
     <code>取得/b/ss/[rsid]/0？vid=[userId]&amp; c. a. appID= SpooofFy1.0&amp; c. Intent= ChangeSong&amp; pageName= AsKForsong HTTP/1.1
主機：sc. omtrdc. net
快取控制項：no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_AE8CF669F06547FDA68801F20BD8CBCE"> 
      <li id="li_5A03E41891AF4F37A3BE05BC11F197BC">訪客 ID </li> 
      <li id="li_435FF7DEB169466E8C3F9258C91315D1">應用程式版本 </li> 
      <li id="li_AB2B602D9DC74B3D951A0942B6CF8B39">意圖 </li> 
      <li id="li_C9F87F3BB7104C9C978BB046C5DB9092">*空白播放清單 </li> 
      <li id="li_FB762962468A44A18DF93488EC2CB848">回應 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 播放席琳狄翁的「My Heart Will Go On」 </p> </td> 
   <td colname="col2"> <p> 「OK，播放席琳狄翁的『My Heart Will Go On』」 </p> </td> 
   <td colname="col3"> <p> ChangeSong </p> </td> 
   <td colname="col4"> <p> 
     <code>取得/b/ss/[rsid]/0？vid=[userId]&amp; c. a. appID= SpooofFy1.0&amp; c. Intent= ChangePlaylist&amp; pageName= ActionPlaySong&amp; c. SongId=[012345] HTTP/1.1
主機：sc. omtrdc. net
快取控制項：no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_2AFEE1E928A8499E96B1BC6C5CC21F81"> 
      <li id="li_4BDF8093373A4DA1BB24A608FAC5B7CF">訪客 ID </li> 
      <li id="li_79B4FACCD333472EB9FC1F94B904AFB4">應用程式版本 </li> 
      <li id="li_3EDAB6208CB24213A934167BD08BD1AE">意圖 </li> 
      <li id="li_C8E6609F9E0A45A8AED15F73374F40B2">歌曲 ID </li> 
      <li id="li_C4D99387C4D748189E15476F5E03BB76">回應 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 變換播放清單 </p> </td> 
   <td colname="col2"> <p> 「OK，您要聽哪個播放清單?」 </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> <p> 
     <code>取得/b/ss/[rsid]/0？vid=[userId]&amp; c. a. appID= SpooofFy1.0&amp; c. Intent= ChangePlaylist&amp; pageName= AskForPlayList HTTP/1.1
主機：sc. omtrdc. net
快取控制項：no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_913CF31C3EB34BDB819AD54D28F9DE5D"> 
      <li id="li_93036A142FB34A73A95B8AB114EA99C3">訪客 ID </li> 
      <li id="li_F699CDD7866C4EB4BECFF0FAA4689736">應用程式版本 </li> 
      <li id="li_6AB1FF7ED6A247FAA8922390410F2F5F">意圖 </li> 
      <li id="li_9DF30E2E1958468783FF753D014F1A5F">*空白播放清單 </li> 
      <li id="li_B1106A51B8CD49DD8B566B946176F854">回應 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 播放亞瑟小子的歌 </p> </td> 
   <td colname="col2"> <p> 「OK，播放亞瑟小子的歌」 </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> <p> 
     <code>取得/b/ss/[rsid]/0？vid=[userId]&amp; c. a. appID= SpooofFy1.0&amp; c. Intent= ChangePlaylist&amp; pageName= ActionPlayPlaylist&amp; c. Playlist= UTarget HTTP/1.1
主機：sc. omtrdc. net
快取控制項：no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_B70E7C9BEFA54C2FA8B7485F9BC7CEE7"> 
      <li id="li_2B0319D20189497D8C9981F871D4FBC4">訪客 ID </li> 
      <li id="li_78C28F34FC7C41589EB111ADCC5A0D66">應用程式版本 </li> 
      <li id="li_8ACF819CF80E4E8F942E0903DF75AE33">意圖 </li> 
      <li id="li_49F407E43F474356A5F131F82B6C4EB9">播放清單 </li> 
      <li id="li_7380EC51B0DE420EB5DD48BCE21B0567">回應 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 關閉音樂 </p> </td> 
   <td colname="col2"> <p> *無回應，音樂關閉 </p> </td> 
   <td colname="col3"> <p> 關閉 </p> </td> 
   <td colname="col4"> <p> 
     <code>取得/b/ss/[rsid]/0？vid=[userId]&amp; c. a. appID= SpooofFy1.0&amp; c. Intent=關閉&amp; pageName= TurnsOffMusic HTTP/1.1
主機：sc. omtrdc. net
快取控制項：no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_BCA19F2A98CC42788A23E668B260F553"> 
      <li id="li_12A9DA8684B2479D90F3C357AE4F1D15">訪客 ID </li> 
      <li id="li_9E543F7F12D247D0900E5B1BE8EB0F61">應用程式版本 </li> 
      <li id="li_9627816FE3594C418EC52DAD42501BCA">意圖 </li> 
      <li id="li_5D59C5D8D0F34F5193F592A867AE5639">回應 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**需要使用者安裝應用程式**

<table id="table_C178E3A2C87043A0A2B8C365869102A3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 「人」 </th> 
   <th colname="col2" class="entry"> 裝置回應 </th> 
   <th colname="col3" class="entry"> 動作/意圖 </th> 
   <th colname="col4" class="entry"> GET 要求 </th> 
   <th colname="col5" class="entry"> Analytics 資料 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 安裝 Spoofify </p> </td> 
   <td colname="col2"> <p> *無回應 </p> </td> 
   <td colname="col3"> <p> 安裝 </p> </td> 
   <td colname="col4"> <p> 
     <code>取得/b/ss/[rsid]/0？vid=[userId]&amp; amp；amp；c. a. SocialEvent=&amp; c. a. InstallDate=2017-04-24&amp; c. a. appID= Spooffy1.0&amp; c. OstType= Alexa&amp; c. Intent= Install&amp; pageName= Install HTTP/1.1
主機：sc. omtrdc. net
快取控制項：no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_83A7731E5EA84477906AF4BFB3B50F48"> 
      <li id="li_A23A342B0D5745B3854B90ADFDD15EB2">訪客 ID </li> 
      <li id="li_E2F89B771B5F445B995E30C7E76BF2D2">日期 </li> 
      <li id="li_03378BC9365F4020B7E28461AFDCB160">意圖 </li> 
      <li id="li_6E1ECC9AF55141D1857688DA6A33DEEA">OS 版本 </li> 
      <li id="li_A4D06A0DFBC247499D9586F6B76571C4">回應 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 播放 Spoofify </p> </td> 
   <td colname="col2"> <p> 「OK，播放 Spoofify」 </p> </td> 
   <td colname="col3"> <p> 播放 </p> </td> 
   <td colname="col4"> <p> 
     <code>取得/b/ss/[rsid]/0？vid=[userId]&amp; c. a. appID= SpooofFy1.0&amp; c. a. launchEvent= Play&amp; pageName= Play&amp; pageName= PlayApp HTTP/1.1
主機：sc. omtrdc. net
快取控制項：no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_8FCA2B1357A8496DAF563775F019404F"> 
      <li id="li_78E84586A5284164B5B577B68A113394">訪客 ID </li> 
      <li id="li_977915DC425A43BDA69D9F76ADFBAB0C">應用程式版本 </li> 
      <li id="li_12725E1D4540485B8A3DB2EC82C6AD4C">啟動次數 </li> 
      <li id="li_5B7F4487682241C38071A7037157F473">意圖 </li> 
      <li id="li_A6AC81D56BF44E07B2FC0F2740CAB237">回應 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 變換曲目 </p> </td> 
   <td colname="col2"> <p> 「OK，您要聽哪首歌?」 </p> </td> 
   <td colname="col3"> <p>ChangeSong </p> </td> 
   <td colname="col4"> 
    <code>取得/b/ss/[rsid]/0？vid=[userId]&amp; c. a. appID= SpooofFy1.0&amp; c. Intent= ChangeSong&amp; pageName= AsKForsong HTTP/1.1
主機：sc. omtrdc. net
快取控制項：no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_C0FCB407A1344527A532A1EAEF0387E4"> 
      <li id="li_8905BCF15F0F493D90B5F1135AEC149C">訪客 ID </li> 
      <li id="li_2D1FAAF35CE24CE49D1AE3F24E4A5A86">應用程式版本 </li> 
      <li id="li_A7D11680A9554414878E6CBD03B66DC4">意圖 </li> 
      <li id="li_64308721D00441FBB7E6EA6EDF93C100">*空白播放清單 </li> 
      <li id="li_A1B2C4E27F9E4B61AAA6373DA8CEB8F2">回應 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 播放席琳狄翁的「My Heart Will Go On」 </p> </td> 
   <td colname="col2"> <p> 「OK，播放席琳狄翁的『My Heart Will Go On』」 </p> </td> 
   <td colname="col3"> <p> ChangeSong </p> </td> 
   <td colname="col4"> 
    <code>取得/b/ss/[rsid]/0？vid=[userId]&amp; c. a. appID= SpooofFy1.0&amp; c. Intent= ChangePlaylist&amp; pageName= ActionPlaySong&amp; c. SongId=[012345] HTTP/1.1
主機：sc. omtrdc. net
快取控制項：no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_5D782E44875144BF96877897E1180D18"> 
      <li id="li_CB5009ED407A4D4ABF3AAFE73133CC66">訪客 ID </li> 
      <li id="li_D15D65E315964E0CBF75A87CF3FCF9B5">應用程式版本 </li> 
      <li id="li_055D7621BE1D44BA8B8C50E2E45DA6DF">意圖 </li> 
      <li id="li_1D52C0AB9C12483E9CD7DC216D809E44">歌曲 ID </li> 
      <li id="li_5CFB748D02E84050AE216FDC55C680E2">回應 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 變換播放清單 </p> </td> 
   <td colname="col2"> <p> 「OK，您要聽哪個播放清單?」 </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> 
    <code>取得/b/ss/[rsid]/0？vid=[userId]&amp; c. a. appID= SpooofFy1.0&amp; c. Intent= ChangePlaylist&amp; pageName= AskForPlayList HTTP/1.1
主機：sc. omtrdc. net
快取控制項：no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_7167AE13BBC64CC99E4A81B1FF6C9208"> 
      <li id="li_15554F7C8AC3487797A2FB65C8C1E636">訪客 ID </li> 
      <li id="li_11254FBCFA60436FB705D5FE4C313CC5">應用程式版本 </li> 
      <li id="li_4F3AE5B191DB4E73A2C08065A3D75188">意圖 </li> 
      <li id="li_7F03D76A26254E65AAEB8E7D647895CA">*空白播放清單 </li> 
      <li id="li_DFB50E6BCEAF440D942B30A56CDD1503">回應 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 播放亞瑟小子的歌 </p> </td> 
   <td colname="col2"> <p> 「OK，播放亞瑟小子的歌」 </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> 
    <code>取得/b/ss/[rsid]/0？vid=[userId]&amp; c. a. appID= SpooofFy1.0&amp; c. Intent= ChangePlaylist&amp; pageName= ActionPlayPlaylist&amp; c. Playlist= UTarget HTTP/1.1
主機：sc. omtrdc. net
快取控制項：no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_BE5815D13CFA48408B4612D220356518"> 
      <li id="li_716EA824A56241A282FD1774A51CF52C">訪客 ID </li> 
      <li id="li_02CC3C2A66E44BB4BA865893F3206A6C">應用程式版本 </li> 
      <li id="li_558B15EC8605495B8DC01E644602FC4F">意圖 </li> 
      <li id="li_21599097A3B14E368693C77CC7BA8ADD">播放清單 </li> 
      <li id="li_70F4254A33704DA18D4D22028A1656E4">回應 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 關閉音樂 </p> </td> 
   <td colname="col2"> <p> *無回應，音樂關閉 </p> </td> 
   <td colname="col3"> <p> 關閉 </p> </td> 
   <td colname="col4"> 
    <code>取得/b/ss/[rsid]/0？vid=[userId]&amp; c. a. appID= SpooofFy1.0&amp; c. Intent=關閉&amp; pageName= TurnsOffMusic HTTP/1.1
主機：sc. omtrdc. net
快取控制項：no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_C623E19496DD466DA299AD610CE5ED1D"> 
      <li id="li_6A7AEF89A74C431C84D107E4F23AE223">訪客 ID </li> 
      <li id="li_B8CFF6AAB2E2476786026A98337589AF">應用程式版本 </li> 
      <li id="li_534596CB56B24B729AAA801A7B4D9D31">意圖 </li> 
      <li id="li_CA3328E5FFF442BAA0F11C51DF2ED53F">回應 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

