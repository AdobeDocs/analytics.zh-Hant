---
description: 舊版 JavaScript H 代碼的累積發行說明。
subtopic: Release notes
title: JavaScript H 代碼 (舊版)
topic: Developer and implementation
uuid: 4586b250-0f1b-45b8-829c-18dc1201956f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# JavaScript H 代碼 (舊版){#javascript-h-code-legacy}

舊版 JavaScript H 代碼的累積發行說明。

> [!NOTE] 若要尋找目前的程式庫版本，請使 [用DigitalPulse除錯程式](https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger_about.html)。

<!-- 

https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=omtrcache&title=AppMeasurement+Change+Log

 -->

## H.27.5 - 更新 {#section_DB9535C7EC4A4DDE9BA56B6C02BE8327}

發行日期: **2016 年 6 月 16 日**

納入 Visitor API 1.5.7。

## H.25.5 - 更新 {#section_B10151D7718F4568AE523BE1553FCCB7}

發行日期: **2016 年 5 月 19 日**

納入 Visitor API 1.5.5。

## H.27.5 - 更新 {#section_AD73ECD5CDAB4E158B509BA7B4B8CC1F}

發行日期: **2015 年 11 月 5 日**

* 納入 Visitor API 1.5.3。

## H.27.5 - 更新 {#section_8A94D8A74A39486AAE248A22D661A261}

發行日期: **2015 年 9 月 17 日**

* 納入 Visitor API 1.5.2。

## H.27.5 - 更新 {#section_62D1787F90FB4730B5F0C79EC1EF84B1}

發行日期: **2015 年 8 月 20 日**

* 納入 Visitor API 1.5.1。

## H.27.5 - 更新 {#section_F58AF8B7FAE9470ABCBF2AAD9E7AF881}

發行日期: **2015 年 6 月 18 日**

* 納入 Visitor API 1.5。

## H.27.5 - 更新 {#section_B3E310AFF909480BAD59A7F87D298348}

發行日期: **2015 年 5 月 21 日**

* 納入 Visitor API 1.4

## H.27.5 - 更新 {#section_E7006FC903064376A85D3EC2AC1D2544}

發行日期: **2015 年 4 月 16 日**

* 在舊版 [!DNL JavaScript] 適用的 [!DNL AppMeasurement] 的 H.X ZIP 檔案中，新增 Integrate 模組至 s_code.js。(AN-101001)

## H.27.5 {#section_22DCF43169614B28BC17F46426C5D5B6}

發行日期: **2015 年 2 月 19 日**

* 納入 Visitor API 1.3.5。
* 已變更為第一個追蹤呼叫後不再執行自動反向連結追蹤，以在第一個追蹤呼叫前手動設定  *`s.referrer`*&#x200B;時，以免第二個、第三個...追蹤呼叫 (通常是連結追蹤) 重複計算反向連結。(AN-92647)

## H.27.4 - 更新 {#section_ED38D59E83B4417180877F7C10BE4582}

發行日期: **2015 年 1 月 15 日**

* 已更新分送 Zip 檔，現在包含 Visitor API 1.3.4。

發行日期: **2014 年 9 月 18 日**

* 新增 `tagContainerMarker` 變數，讓實施可指定最多 4 個字元附加至版本字串與其他破折號分隔字元。此功能可用於動態標籤管理。

```js
  //  
<keyword>
  JavaScript 
</keyword> 
  s.tagContainerMarker = "D1.0"; 
    
  // Data Collection request 
  //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
```

## H.27.3 {#section_B38C61EE3BEA49CAA7A664395C85E4CF}

發行日期: **2014 年 8 月 21 日**

* 進行內部變更，支援未來功能。

## H.27.2 {#section_402A4142C4B846DE945FD59DAD9D9298}

發行日期: **2014 年 6 月 19 日**

* 修正處理訪客 API 欄位 (如舊版 [!DNL Analytics] 訪客 ID) 的完成和等待標幟時會發生錯誤的問題。
* 支援訪客 ID 服務 1.3 的新功能。

## H.27.1 {#section_CC2556C734EE4BAAB71D6A93095DB38F}

發行日期: **2014 年 6 月 11 日**

* 修正在 [!DNL Target] 適用的 [!DNL Analytics] 整合中，導致部分點擊會不正確合併的問題。

## H.27 {#section_023B6267C0DB424F99A23EBB732B8C69}

發行日期: **2014 年 5 月 22 日**

* 支援 [Experience Cloud訪客ID服務](https://marketing.adobe.com/resources/help/en_US/mcvid/)。
* 支援 [Analytics for Target 整合](https://marketing.adobe.com/resources/help/en_US/target/a4t/)。

## H.26.2 {#section_DE82C8BC7645400785E5B136565616F1}

發行日期: **2013 年 10 月 17 日**

* 新增 `alt=""` 至所有影像物件，以遵循「視訊與通訊無障礙法」(Accessible Video and Communications Act)。

## H.26.1 {#section_C3BDD9A19EF84467A8FDC283AEAE2DB5}

發行日期: **2013 年 7 月 18 日**

* 自動連結追蹤現在會忽略雜湊/片段。以前由於下列 URL 的整個 `.pdf` 結尾為 `href`，所以會自動加以追蹤:

```js
  <a href="index.htm#anchor.pdf">Test Link</a>
```

現在會忽略雜湊/片段，所以只在檔案名稱結尾為符合的副檔名時才會追蹤連結。

## H.26 {#section_E25814ACC21E41718EE1741A85AE567B}

發行日期: **2013 年 4 月 29 日**

* `useForcedLinkTracking`使用自訂連結程式碼進行手動連結追蹤[中說明的 ](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_manuallinktrackcustomlink.html) 選項現已適用於 Firefox 20+ (之前此功能僅適用於 WebKit 瀏覽器)。

* 例項之間的影像物件 ID 產生現在是獨特的。如此可預防在同一頁面上有多個例項時會發生衝突。

## H.25.5 {#section_A528D1D5E84146F9A56680E4427B2750}

發行日期: **2013 年 4 月 19 日**

* 修正強制連結 [!DNL Windows] 追蹤導致某些 [!DNL Android] 2.2 版裝置發生 [!DNL JavaScript] 錯誤的問題。

* 在 Media Player 的視訊自動追蹤中，修正因終止而導致無法正確追蹤時間的問題。

## H.25.4 {#section_009AF895C8DD47CABC9A3776D27E8300}

發行日期: **2013 年 2 月**

* 變更自動退出連結追蹤，一律忽略具有以 `#`、`about:` 或 `javascript:` 開頭之 `HREF` 屬性的連結。

* 優化受 `useForcedLinkTracking` 影響的點按事件範圍。自動強制連結追蹤僅套用於:

   * `<A>` 和 `<AREA>` 標籤

   * 標記必須具有 `HREF` 屬性
   * `HREF` 開頭不能為 `#`、`about:` 或 `javascript:`

   * 不可設定 `TARGET` 屬性，或 `TARGET` 必須參考現行視窗 (`_self`、`_top` 或 `window.name` 的值)

## H.25.3 {#section_FA6A6F9F5D64455DA5A54C007081341A}

發行日期: **2013 年 1 月**

* 新增傳送長度超過 255 個位元組之 URL 的支援，進而在 Adobe Data Collection 伺服器中支援「頁面 URL」欄位的擴充。長度超過 255 個位元組的頁面 URL 會被切割，前 255 個位元組出現在 `g=` 參數，其餘位元組出現在 `-g=` 查詢參數的查詢字串中。這麼一來，在瀏覽器切截字串的情況下，可以避免長 URL 佔據其他資料，但仍可擷取長 URL。

* 針對混合使用 `escape` 和 `encodeURIComponent` 來編碼的字串，已經修正處理 URL 編碼的問題。

* 修正在頁面上的首次伺服器呼叫逾時，而導致網路套件瀏覽器中的連結追蹤失敗的問題。
* 新增後援訪客識別方法。請參閱[識別獨特訪客](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_identifying_unique_visitors.html)。
* 新增可以在 `doPlugins` 內設定的新 `abort` 標幟。若將此標幟設為 true，會使得 [!DNL AppMeasurement] 庫不再繼續使用該追蹤呼叫。中止標幟皆會隨每個追蹤呼叫重設，因此若後續的追蹤呼叫也需要被中止，就必須在 `doPlugins` 中再次設定此標幟。

```js
  s.doPlugins = function(s) { 
       s.campaign = s.getQueryParam("cid"); 
       if ((!s.campaign) && (!s.events)) { 
            s.abort = true; 
       } 
  };
```

這讓您可以集中邏輯，用於識別不想追蹤的活動，例如自訂連結或顯示廣告中的外部連結。

## H25.2 {#section_647D7638D0C04019B8C9986CD124914E}

發行日期: **2012 年 10 月**

* 新增在 [!DNL JavaScript] 版本報表中多報告一個版本號碼的支援。以前此版本只顯示 2 個字元 (如 1.8)，現在支援 3 個字元版本號碼 (如 1.8.5)。
* 修正[!DNL Tag Manager] 中的相依程式碼區塊無法傳送重複值的問題。

## H.25.1 {#section_680CE31CFA9945978F42612B684DB831}

發行日期: **2012 年 9 月**

* 強制 URL 編碼下列字元:

```
  ~ 
  ! 
  * 
  ( 
  ) 
  '
```

如此可解決 [!DNL ClickMap] `s_sq` Cookie 中儲存未逸出字元的問題。

* 修正當使用自訂 `media.monitor` 方法來追蹤媒體關閉事件時，可能無法傳送視訊結束事件的問題。

```
  If(media.event=="CLOSE") { 
  … 
  } 
  
```

## H.25 {#section_BE76FEDFE03B44658808B0BDF779DE97}

發行日期: **2012 年 7 月**

進行了更新，確保 WebKit 瀏覽器 (Safari 和 Chrome) 上的連結追蹤成功完成。此項更新後，設為自動追蹤的下載和退出連結 (由 `s.trackDownloadLinks` 和 `s.trackExternalLinks` 決定) 將可成功予以追蹤。如果您使用手動 [!DNL JavaScript] 呼叫來追蹤自訂連結，則需要修改這些呼叫的進行方式。

例如，退出和下載連結通常使用類似下列的程式碼來進行追蹤:

```js
  <a href="http://anothersite.com" onclick="s.tl(this,'o','link name',null)">
```

Firefox 和 Internet Explorer 會執行追蹤連結調用，並開啟新頁面。但是，WebKit 瀏覽器可能會在新頁面開啟時，取消追蹤連結調用的執行。因此在使用 WebKit 瀏覽器時，常會導致追蹤連結調用無法完成。

為了解決這個問題，H.25 加入多載追蹤連結方法 (`s.tl`)，強制 WebKit 瀏覽器等候追蹤連結調用完成。這個新方法會先執行追蹤連結調用，接著再處理導覽事件，而不是使用預設的瀏覽器動作。此多載方法需要其他參數 (稱為 `doneAction`)，用以指定追蹤連結調用完成時要執行的動作。

若要使用這個新方法，請使用類似下列的程式碼，以其他 `s.tl` 參數更新對 `doneAction` 的調用。

```js
  <a href="http://anothersite.com" onclick="s.tl(this,'o','link name',null 
  <codeph outputclass="syntax"> ,'navigate');return false"> 
  </codeph outputclass="syntax">
```

將 'navigate' 傳遞為 `doneAction`，鏡射預設瀏覽器行為並在追蹤調用完成時開啟 `href` 屬性指定的 URL。

下表彙整 H.25 的組態變數與更新，以支援此功能。

<table id="table_E67157D710874146B26EFB7D84762542"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>變數 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>useForcedLinkTracking </p> </td> 
   <td colname="col2"> <p>此旗標用來停用 WebKit 瀏覽器的強制連結追蹤。WebKit 瀏覽器預設會啟用強制連結追蹤，但其他瀏覽器會忽略這項功能。 </p> <p> <b>預設值</b> </p> <p> <code> true </code> </p> <p> <b>範例</b> </p> 
    <code class="syntax javascript">
      s.useForcedLinkTracking&amp;nbsp;=&amp;nbsp;false 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>forcedLinkTrackingTimeout </p> </td> 
   <td colname="col2"> <p>在執行已傳入 <code> doneAction </code> 的 <code> s.tl </code> 之前，等待追蹤完成的毫秒數上限。此值表示等待時間上限。如果追蹤連結呼叫在此逾時前完成，就會立即執行 <code> doneAction </code>。如果您注意到追蹤連結呼叫未完成，您可能需要提高此逾時。 </p> <p> <b>預設值</b> </p> <p>250 </p> <p> <b>範例</b> </p> 
    <code class="syntax javascript">
      s.forcedLinkTrackingTimeout&amp;nbsp;=&amp;nbsp;500 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackLink ( <code> s.tl </code>) </td> 
   <td colname="col2"> <p>追蹤退出、下載及自訂連結。提供選用參數，指定在 WebKit 瀏覽器上完成追蹤連結呼叫後執行導覽動作。 </p> <p> <b>語法</b> </p> 
    <code class="syntax javascript">
      s.tl(linkObject,linkType,linkName,variableOverrides,doneAction) 
    </code> <p> <b>doneAction</b>: (選用) 指定在傳送連結追蹤呼叫或逾時 (根據 <code> s.forcedLinkTrackingTimeout </code> 所指定的值) 之後所要採取的動作。The <code> doneAction </code> can be the string 'navigate', which causes the method to set <code> document.location </code> to the <code> href </code> attribute of <code> linkObject </code>. <code> doneAction</code> 也可以是一個允許進階自訂的函數。 </p> <p>若在錨點 <code> onclick </code> 事件中提供 <code> false </code> 的值，您必須在 <code> s.tl </code> 呼叫之後傳回 <code> href </code>，以防止進行預設瀏覽器導覽。 </p> <p> 若要反映預設行為並遵循 <code> doneAction </code> 屬性所指定的 URL，請提供字串「navigate」做為 <code> doneAction </code>。 </p> <p>您可以視需要選擇傳入自己的函數作為 <code>$1</code>，將此函數用於處理導覽事件。 </p> <p> <b>範例</b> </p> 
    <code class="syntax javascript">
      &lt;a&amp;nbsp;href="..."&amp;nbsp;onclick="s.tl(this,'o','MyLink',null,'navigate');return&amp;nbsp;false"&gt;Click&amp;nbsp;Here&lt;/a&gt; 
    </code> 
    <code class="syntax javascript">
      &lt;a&amp;nbsp;href="#"&amp;nbsp;onclick="s.tl(this,'o','MyLink',null,function(){if(confirm('Proceed?'))document.location=...});return&amp;nbsp;false"&gt;Click&amp;nbsp;Here&lt;/a&gt; 
    </code> </td> 
  </tr> 
 </tbody> 
</table>

## H.24.4 {#section_1989179F10A34E88968CA5A5290CF17C}

發行日期: **2012 年 4 月**

建議所有客戶都套用此更新。

* 增強對於使用 Google Chrome Prerender 預先轉譯之頁面的偵測能力 ([https://developers.google.com/chrome/whitepapers/prerender](https://developers.google.com/chrome/whitepapers/prerender))。Prerender 載入並執行 [!DNL JavaScript] 和其他程式碼後，可能導致在使用者點按以存取您的網站前，就先行傳送頁面檢視。[!DNL JavaScript] 程式庫現在會等到使用者存取您的網站，才傳送這些已預先轉譯之頁面的伺服器呼叫。
* 針對要將類似其他 程式庫的時間戳記資料加以自訂的客戶，將 `timestamp`[!DNL JavaScript] 變數新增到 程式庫。[!DNL AppMeasurement]

```js
  s.timestamp=Math.round((new Date()).getTime()/1000); 
  s.timestamp="2012-04-20T12:49:31-0700";
```

## H.24.3 {#section_F3D471B201F54C089320D3CE6D441DC0}

發行日期: **2012 年 2 月**

* 修正使用 Javascript `Object.prototype` 覆蓋之客戶的影像請求中包含多餘資料的問題。現在處理上下文資料變數時，會略過所有的 `Object.prototype` 用法。
* 修正有時候會以相同值傳遞兩次 `pe` 查詢參數的問題。
* 修正 中的 [!DNL ClickMap][!DNL JavaScript] 追蹤，忽略對 Body 標記的點按次數，即使標記帶有 `onClick` 事件控制碼亦同。
* 新增時間戳記至搭配光源追蹤呼叫 (`trackLight`) 的變數。

## H.24.2 {#section_91CF07C2BC9B4C8BA0235DFDFB95A4D9}

發行日期: **2012 年 1 月**

* 以新方式更新視訊追蹤，現可追蹤完整的視訊檢視次數。
* 針對 IE 中 VML 元素的 `OnClick` 事件，修正導致「屬性僅對 v:image 有效」[!DNL JavaScript] 錯誤的問題。
* 修正儘管在 `linkTrackVars` 中參考上下文資料變數，但變數仍未納入連結伺服器呼叫的錯誤。上下文資料變數適用於處理規則。

## H.24.1 {#section_967356D219FE4E9CAA110D03EDF4C8B1}

發行日期: **2011 年 11 月**

* 更新視訊追蹤，現在合併同時發生的區段和里程碑之點擊。

## H.24 {#section_78FF9B245643406BB7E9967E784A90AE}

發行日期: **2011 年 11 月**

* 進行內部更新，以支援 [!DNL Adobe Tag Manager]。

## H.23.9 {#section_3834625A639A47428683E08A472359C7}

發行日期: **2011 年 11 月**

* 進行內部更新，以支援 [!DNL Adobe Tag Manager]。

## H.23.8 {#section_FF3CEEAB6C6744D6B5EE314A0B5841CA}

發行日期: **2011 年 10 月**

* 修正當使用自動退出連結追蹤時，不會套用 `linkTrackVars=none` 和 `linkTrackEvents=none` 設定的問題。這些設定現在可套用至自動退出連結，因此退出連結影像請求不會傳送 prop、eVar 和事件。

## H.23.7 {#section_D9D0CF343EBF49D9844C6BDA0C3C7A2E}

發行日期: **2011 年 9 月**

* 從行動裝置的影像標記中移除邊框屬性，以符合無線傳輸標記語言 (WML) 標準。這修正某些行動裝置的呈現問題。

## H.23.6 {#section_461A208BE1B64EDDA87A8D7C4FD5456C}

發行日期: **2011 年 8 月**

修正視訊追蹤的百分比測量準確度。

## H.23.5 {#section_FCE48EE33C9A42F08386FA30037BF4E0}

發行日期: **2011 年 7 月**

* 新增依區段劃分 [!DNL Adobe Tag Manager]。

## H.23.4 {#section_E9152B4437C24107A68D264F70361930}

發行日期: **2011 年 6 月**

* 修正會在存取 Vector Markup Language (VML) 形狀元素的特定屬性時導致 [!DNL JavaScript] 錯誤的問題。
* 現在已透過縮短路徑而非查詢字串，截斷超過 255 個字元的轉接連結字串。這修正查詢字串參數遭截斷且未收集的問題。

## H.23.3 {#section_EAB0602E07EE4A5CA6521351F461D22D}

發行日期: **2011 年 5 月**

* 修正致使視訊追蹤 (pev3) 變數無法傳送的問題。
* 修正致使 `s_gi` 呼叫無法讓程式碼與 G 和 H 程式碼相容的問題。當您傳遞 1 作為此呼叫的第二個參數時，程式碼現在已設定為與兩個版本相容。

## H.23.2 {#section_274143E83A8D42F1AD40CAE4326E99CE}

發行日期: **2011 年 4 月**

* 支援可提升伺服器端處理規則的 contextData (僅限 v15)。
* 支援輕伺服器呼叫 (僅限 v15)。
* 支援將 1 以外的值指派給事件清單中的計數器事件。
* 支援使用轉換 eVars 和事件追蹤視訊的新方法 (目前測試中)。
* 移除將 Media.trackWhilePlaying 設定為 false 的支援。此屬性一律設定為 true。
* 新增 debugTracking 旗標，讓要求記錄能傳送至 Firebug 主控台 (就如同其他平台)。
* 不論瀏覽器為何，確定 "+" 始終使用 URL 編碼。
