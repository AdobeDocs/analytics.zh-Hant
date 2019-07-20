---
description: 檔案下載和退出連結可根據「JavaScript 適用的 AppMeasurement」檔案中設定的參數自動受到追蹤。
keywords: Analytics 實施
seo-description: 檔案下載和退出連結可根據「JavaScript 適用的 AppMeasurement」檔案中設定的參數自動受到追蹤。
seo-title: s.tl() 函數 - 連結追蹤
solution: Analytics
subtopic: 連結追蹤
title: s.tl() 函數 - 連結追蹤
topic: 開發人員和實施
uuid: f28f071a-8820-4f74-89cd-fd2333 a21 f22
translation-type: tm+mt
source-git-commit: acaea784c977d7ff438f84faf8af5a3c605e3cf5

---


# s.tl() 函數 - 連結追蹤

File downloads and exit links can be automatically tracked based on parameters set in the [!DNL AppMeasurement] for JavaScript file.

## s.tl() 函數 - 連結追蹤 {#concept_EA13689CB8EE4F308FC89A1293046D5E}

File downloads and exit links can be automatically tracked based on parameters set in the [!DNL AppMeasurement] for JavaScript file.

如果需要，這些類型的連結可以使用自訂連結程式碼手動追蹤，其說明如下。此外，自訂連結代碼可以用來追蹤各種用於滿足追蹤及報表需要的一般自訂連結。

## s.tl() 參數參考 {#section_DDF19EE3ACE24EFAB2D65CD4B0D7DBC4}

<!-- Meike, I converted a table within to table to this section. Please check against orginal file -Bob -->

**this**

第一個引數應一律設為 this (預設值) 或 true。此引數會參照所點按的物件；在設為 "this" 時，將會參照連結的 HREF 屬性。

如果您在沒有HREF屬性的物件上實施連結追蹤，則應一律將此引數設為「this」。

由於點按連結通常會將訪客帶離目前頁面，因此使用 500 毫秒的延遲，以確保影像要求會在使用者離開頁面之前傳送至 Adobe。只有在離開頁面時才需要此延遲，但在呼叫 s.tl() 函數時通常會出現此延遲。若您想要停用此延遲，請在呼叫 s.tl() 函數時將關鍵字 'true' 傳入為第一個參數。

**linkType**

`s.tl(this,linkType,linkName, variableOverrides, doneAction)`

linkType 有三個可能的值，視您所要擷取的連結類型而定。若連結不是下載或退出連結，您應選擇自訂連結選項。

| 類型 | linkType 值 |
|--- |--- |
| 檔案下載 | 'd' |
| 退出連結 | 'e' |
| 自訂連結 | 'o' |

**linkName**

這可以是任何自訂值，最多 100 個字元。這會決定連結在適當報表中的顯示方式。

**variableOverrides**

(選用項目，若未使用則傳入 Null) 此項目可讓您變更這一個呼叫的變數值，其過程類似於其他 [!DNL AppMeasurement] 程式庫。

**useForcedLinkTracking**

此標幟用來停用某些瀏覽器的強制連結追蹤。依預設會為 FireFox 20 (和更高版本) 與 WebKit 瀏覽器啟用強制連結追蹤。

預設值= true

範例: `s.useForcedLinkTracking& = false`

**forcedLinkTrackingTimeout**

在執行已傳入 `s.tl` 的 doneAction 之前，等待追蹤完成的毫秒數上限。此值表示等待時間上限。若追蹤連結呼叫在此逾時前完成，就會立即執行 doneAction。若您注意到追蹤連結呼叫未完成，您可能需要提高此逾時。

預設值=250

範例: `s.forcedLinkTrackingTimeout&nbsp;=&nbsp;500`

**doneAction**

一個選用參數，用以在 useForcedLinkTracking 啟用的情況下，指定追蹤連結呼叫完成後所要執行的導覽動作。

語法:

`s.tl(linkObject,linkType,linkName,variableOverrides,doneAction)`

 doneAction : (選用) 指定在連結追蹤呼叫傳送或逾時 (根據下列項目所指定的值) 之後所要採取的動作: 

`s.forcedLinkTrackingTimeout`

doneAction 變數可以是字串 navigate，該字串會使方法將 `document.location` 設為 linkObject 的 href 屬性。doneAction 變數也可以是允許進階自訂的函數。

若在錨記 onclick 事件中提供 doneAction 的值，您必須在 `s.tl` 呼叫之後傳回 false，以防止進行預設瀏覽器導覽。

若要反映預設行為並遵循 href 屬性所指定的 URL，請提供字串 navigate 作為 doneAction。

您可以視需要選擇傳入自己的函數作為 doneAction，將此函數用於處理導覽事件。

範例:

```js
<a href="..." onclick="s.tl(this,'o','MyLink',null,'navigate');return false">Click Here</a> <a href="#" onclick="s.tl(this,'o','MyLink',null,function(){if(confirm('Proceed?'))document.location=...});return false">Click Here</a>
```

**範例**

下列 [!UICONTROL s.tl()] 函數呼叫範例採用預設值 500 毫秒的延遲，以確定可在離開頁面之前收集資料。

```js
s.tl(this,'o','link name');
```

下列範例在使用者不會離開頁面，或在所要點按的物件沒有 HREF 時，會停用 500 毫秒的延遲。

```js
s.tl(true,'o','link name');
```

500 毫秒的延遲是最大值。若要求的影像在 500 毫秒以內傳回，延遲會立即停止。這可讓訪客移至下一頁，或頁面內的下一個動作。

以下是在 WebKit 瀏覽器上處理自訂連結的範例: 

```js
<a href="..." onclick="s.tl(this,'o','MyLink',null,'navigate');return false">Click Here</a>
```

```js
<a href="#"  onclick="s.tl(this,'o','MyLink',null,  
function(){if(confirm('Proceed?'))document.location=...});return false">Click Here</a>
```

>[!NOTE]
>
>自訂連結程式碼的使用通常很適合您的網站和報告需求。在實施自訂連結程式碼之前，您可以聯絡 Adobe 顧問或客戶服務，以瞭解您有哪些可行方式，以及如何根據您本身的商業需求充分運用這項功能。

使用自訂連結代碼追蹤連結的基本代碼如以下範例中所示:

```js
<a href="index.html" onClick="s.tl(this,'o','Link Name')">My Page</a>
```

>[!NOTE]
>
>[!UICONTROL s_ gi] 函數必須包含您的報表套裝ID，作為函數參數。請確實換出您唯一報表套裝 ID 的 [!DNL rsid]。

>[!NOTE]
>
>如果未定義連結名稱參數，連結的URL(由「this」物件決定)會用作連結名稱。

[!DNL Analytics] 變數可定義為自訂連結程式碼的一部分。

## 退出連結和檔案下載的自動追蹤 {#concept_DF078C5C1B004695B3B7C4536C99D4B2}

可將 JavaScript 檔案組態為基於那些定義檔案下載類型和退出連結的參數來自動追蹤檔案下載及退出連結。

<!-- 

link_automatic.xml

 -->

能控制自動追蹤的參數如下:

```js
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls" 
s.linkInternalFilters="javascript:,mysite.com,[more filters here]" 
s.linkLeaveQueryString=false 
```

參數&#x200B;*`trackDownloadLinks`**`trackExternalLinks`* 並決定是否啓用自動檔案下載和退出連結追蹤。When enabled, any link with a file type matching one of the values in *`linkDownloadFileTypes`* is automatically tracked as a file download. Any link with a URL that does not contain one of the values in *`linkInternalFilters`* is automatically tracked as an exit link.

In JavaScript H.25.4 (released February 2013), automatic exit link tracking was updated to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`.

## Example 1 {#section_504D163608E14B25A8B4CA9D615C6735}

The file types [!DNL jpg] and [!DNL aspx] are not included in *`linkDownloadFileTypes`* above, therefore no clicks on them are automatically tracked and reported as file downloads.

The parameter *`linkLeaveQueryString`* modifies the logic used to determine exit links. *`linkLeaveQueryString`*= false時，只會使用連結URL的網域、路徑和檔案部分來決定退出連結。*`linkLeaveQueryString`*&#x200B;在= true時，也會使用連結URL的查詢字串部分來決定退出連結。

## Example 2 {#section_25660B64E28248A0BC982B2AF5603C0E}

透過下列設定，下面的範例將被計為一個退出連結:

```js
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=false 
 
//HTML file 
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site!</a> 
```

## 範例 3 {#section_2A78D05162D640169844A7D1E9799BAA}

使用下列設定時，下列連結將不會計為退出連結: 

```js
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=true 
 
//HTML  
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site</a> 
```

>[!NOTE]
>
>只能將單一連結視為檔案下載或退出連結追蹤，且檔案下載優先。If a link is both an exit link and file download based on the parameters *`linkDownloadFileTypes`* and *`linkInternalFilters`*, it is tracked and reported as a file download and not an exit link. 下表總結了檔案下載及退出連結的自動追蹤.

## 使用自訂連結代碼進行手動連結追蹤 {#concept_7113B5D037BE4622B6934554C6D18F96}

自訂連結程式碼可讓您在自動追蹤不充分或不適用的情形之下追蹤檔案下載、退出連結和自訂連結。

<!-- 

link_manual.xml

 -->

自訂連結程式碼的一般實施方式，是將 [!UICONTROL onClick] 事件處理常式新增至連結，或將程式碼新增至現有常式。在本質上，此程式碼可從任何 JavaScript 事件處理常式或函數來實施。

Link Tracking consists of calling the [!DNL AppMeasurement] for JavaScript function whenever the user performs actions that generate data you want to capture. 此函數 ([!UICONTROL s.tl()]) 可直接在事件處理常式中呼叫 (例如 [!UICONTROL onClick] 或 [!UICONTROL onChange])，或從個別的函數中呼叫。此 [!UICONTROL s.tl()] 函數有 5 個引數。前 3 個為必要引數:

```js
s.tl(this,linkType,linkName, variableOverrides, doneAction)
```

## FireFox 和 WebKit 瀏覽器上的自訂連結追蹤 {#section_F2B9A2A3CC1F4BB9A64456BC39FC50B9}

JavaScript H.25 進行了更新，以確保 WebKit 瀏覽器 (Safari 和 Chrome) 上的連結追蹤能順利完成。JavaScript H.26 進行了更新，以確保 FireFox 20 (和更高版本) 上的連結追蹤能順利完成。

此項更新後，設為自動追蹤的下載和退出連結 (由 [!DNL s.trackDownloadLinks] 和 [!DNL s.trackExternalLinks] 決定) 將可成功予以追蹤。如果您使用手動 JavaScript 調用來追蹤自訂連結，則需要修改這些調用的進行方式。例如，退出和下載連結通常使用類似下列的程式碼來進行追蹤:

```js
<a href="https://anothersite.com" onclick="s.tl(this,'e','AnotherSite',null)">
```

Internet Explorer  會執行追蹤連結呼叫，並開啟新頁面。但其他瀏覽器可能會在新頁面開啟時，取消追蹤連結呼叫的執行。這常會使追蹤連結呼叫無法完成。

為了解決這個問題，H.25 (於 2012 年 7 月發行) 加入多載追蹤連結方法 ([!DNL s.tl])，強制具有此行為的瀏覽器等待追蹤連結呼叫完成。這個新方法會先執行追蹤連結呼叫，接著再處理導覽事件，而不是使用預設的瀏覽器動作。此多載方法需要其他參數 (稱為 [!UICONTROL doneAction])，用以指定追蹤連結調用完成時要執行的動作。

若要使用這個新方法，請使用類似下列的程式碼，以其他 [!DNL s.tl]doneAction[!UICONTROL  參數更新對 ] 的調用。

```js
<a href="https://anothersite.com"  
onclick="s.tl(this,'e','AnotherSite',null,'navigate');return false">
```

將 navigate 傳入作為 [!UICONTROL doneAction]，可反映預設瀏覽器行為，並在追蹤呼叫完成時開啟 href 屬性所指定的 URL。

JavaScript H.25.4 (於 2013 年 2 月發行) 針對在 `useForcedLinkTracking` 啟用時受到追蹤的連結新增了下列範圍限制。自動強制連結追蹤僅套用於:

* `<A>` 和 `<AREA>` 標籤。
* 標記必須具有 `HREF` 屬性.
* The `HREF` can't start with `#`, `about:`, or `javascript:`.
* `TARGET` 無法設定屬性，或 `TARGET` 參考目前視窗( `_self`、 `_top`或值 `window.name`)。

## 使用影像要求進行連結追蹤 {#concept_FF31C8D1B3DF483D853BF0A9D637F02F}

建立影像請求，即可不呼叫 s.tl() 函數而追蹤連結。

<!-- 

link_img.xml

 -->

影像要求可藉由將 "pe" 參數新增至影像要求 src 參數來進行硬式編碼，如下所示: 

```
pe=[type]
```

Where `[type]` is replaced with the type of link you want to track:

* lnk_d = 下載
* lnk_e = 退出
* lnk_o = 自訂

此外，也可藉由將 URL 傳入 pev1 參數中，來指定連結 URL: 

```
pev1=mylink.com
```

連結名稱可藉由將名稱傳入 pev2 參數中來指定: 

```
pev2=My%20Link
```

例如:

```
<img src="https://collectiondomain.112.2o7.net/b/ss/reportsuite/1/H.25.3--NS/0?pe=lnk_e&pev1=othersite.com&pev2=Offsite%20Link" width="1" height="1" border="0" />
```

## 設定用於檔案下載、退出連結及自訂連結的其他變數 {#concept_8DD06387D5234A52A6E361572FAA2DF6}

Two parameters (  and ) control which [!DNL Analytics] variables are set for file downloads, exit links, and custom links.

<!-- 

link_variables.xml

 -->

這兩個參數依預設會設定在 JS 檔案內，如下所示: 

```js
s.linkTrackVars="None"
```

```js
s.linkTrackEvents="None"
```

此&#x200B;*`linkTrackVars`* 參數應包含您要隨每個檔案下載、退出連結及自訂連結而追蹤的每個變數。*`linkTrackEvents`* 參數應包含您要隨每個檔案下載、退出連結和自訂連結而追蹤的每個事件。當其中一種連結類型發生時，即會追蹤每個指定變數的現行值。

例如，若要隨每個檔案下載、退出連結及自訂連結追蹤 prop1、eVar1 及 event1，請在全域 JS 檔案內使用下列設定: 

```js
s.linkTrackVars="prop1,eVar1,events"
```

```js
s.linkTrackEvents="event1"
```

>[!NOTE]
>
>The variable *`pageName`* cannot be set for a file download, exit link, or custom link, because each of the link types is not a page view and does not have an associated page name.

>[!NOTE]
>
>If *`linkTrackVars`* (or *`linkTrackEvents`*) is null (or an empty string), all [!DNL Analytics] variables (or events) that are defined for the current page are tracked. 這很可能會使每個變數的例項數不實膨脹，因此應予以避免。

## 最佳實務 {#section_DA3CA596792E4BD6B5FFE89BCE0E617D}

The settings for *`linkTrackVars`* and *`linkTrackEvents`* within the JS file affect every file download, exit link, and custom link. 若將變數 (或事件) 套用至現行頁面，而不是特定的檔案下載、退出連結或自訂連結，每個變數和事件的例項數可能會不實膨脹。

為確保能為自訂連結程式碼設定正確的變數，Adobe 建議您在自訂連結程式碼內設定 *`linkTrackVars`* 在 *`linkTrackEvents`* 自訂連結程式碼中，如下所示：

```js
<a href="index.html" onClick=" 
var s=s_gi('rsid'); 
s.linkTrackVars='prop1,prop2,eVar1,eVar2,events'; 
s.linkTrackEvents='event1'; 
s.prop1='Custom Property of Link'; 
s.events='event1'; 
s.tl(this,'o','Link Name'); 
">My Page 
```

The values of *`linkTrackVars`* and *`linkTrackEvents`* override the settings in the JS file and ensure only the variables and events specified in the custom link code are set for the specific link.

>[!NOTE]
>
>在上述範例中，prop的值設定在自訂連結程式碼本身中。prop2 的值則來自變數的現行值，如頁面上所設定。

## 使用帶有自訂連結代碼的函數呼叫 {#concept_DB662C93B3ED415DB72C80270502BE5D}

由於自訂連結程式碼的複雜性，您可以將程式碼合併成一個自封式的 JavaScript 函數 (定義於頁面上或在連結的 JavaScript 檔案中)，並呼叫 [!UICONTROL onClick] 處理常式內的函數。

<!-- 

link_functions.xml

 -->

For example, you could insert the following two functions in your `AppMeasurement.js` file, just below the `s_doPlugins()` function, and then use them throughout your site:

```js
/* Set Click Interaction values (with timeout - H25 code and higher*/ 

function trackClickInteraction(name){ 
    var s=s_gi('rsid'); 
    s.linkTrackVars='prop42,prop35'; 
    s.prop42=name; 
    s.prop35=s.pageName; 
    s.tl(true,'o','track interaction',null,'navigate'); 
}
```

```js
/* Set Click Interaction values (without timeout - pre H25 code*/ 
 
function trackClickInteraction(name){ 
    var s=s_gi('rsid'); 
    s.linkTrackVars='prop42,prop35'; 
    s.prop42=name; 
    s.prop35=s.pageName; 
    s.tl(true,'o','track interaction'); 
}
```

>[!NOTE]
>
>如有需要，您可以將連結類型和連結名稱傳遞為JavaScript函數的其他參數。

您可以使用類似下列的程式碼來呼叫這些函數:

```
<a href=”https://www.your-site.com/some_page.php” onclick=”trackClickInteraction('this.href');”>Link Text</a>
```

## 避免重複連結計數 {#section_9C3F73DE758F4727943439DED110543C}

在連結通常會被自動檔案下載或退出連結追蹤擷取的情形之下，該連結可能會被重複計數。

例如，如果您在自動追蹤  PDF 下載，下列程式碼會造成重複下載計數:

```js
function trackDownload(obj) { 
 var s=s_gi('rsid'); 
 s.linkTrackVars='None'; 
 s.linkTrackEvents='None'; 
 s.tl(obj,'d','PDF Document'); 
}
```

若要確保不發生重複計數，請使用下列已修改的 JavaScript 函數:

```js
<script language=JavaScript> 
function linkCode(obj) { 
 var s=s_gi('rsid'); 
 s.linkTrackVars='None'; 
 s.linkTrackEvents='None'; 
 var lt=obj.href!=null?s.lt(obj.href):""; 
 if (lt=="") { s.tl(obj,'d','PDF Document'); } 
}
```

上述的最後兩行程式碼會將自訂連結程式碼的行為修改成僅執行自動追蹤，以避免任何可能的重複計數。

## 使用 useForcedLinkTracking 的快顯視窗 {#concept_0AC4BA3A64B84CCB8D9A6021A022D1C3}

When `useForcedLinkTracking` is enabled, [!DNL AppMeasurement] overrides the default link behavior on some browsers to prevent the track link call from being canceled when the new page opens. [!DNL AppMeasurement] 會執行追蹤連結呼叫並手動處理導覽事件，而不是使用預設的瀏覽器動作。

<!-- 

link_popups.xml

 -->

When tracking some links that open a popup window, the Chrome built-in popup blocker might prevent [!DNL AppMeasurement] from opening a popup window that would normally be allowed. To avoid this, add a `target="_blank"` attribute to calls that open a window:

```
<a href="./popup.html" target="_blank" onClick="<a href="./popup.html" onclick="s.tl(this,'o','popup',null,'navigate');javascript:window.open('./popup.html','popup','width=550,height=450'); 
return false;">
```

如此可允許追蹤連結並讓快顯視窗如常載入。

## 來自 URL 縮短器的連結 {#concept_CD792362A8E04448B452BE9A18772024}

來自 URL 縮短器服務的連結 (例如 bit.ly) 通常不會當作頁面檢視或當作反向連結來追蹤。這些服務會將具有完整 URL 的 301/302 重新導向傳回至 Web 瀏覽器，然後將新的個別要求傳送至完整 URL。原始反向連結會保留，因為縮短器不再位於迴圈中，而且要求上沒有已重新導向的服務是用來取得 URL 的指示。

<!-- 

link_shortener.xml

 -->

由於各種可用的服務，我們建議測試您網站上使用中的特定案例，以決定服務所使用的重新導向機制。

## doPlugins 中的連結追蹤變數 {#concept_B5AC1D4372AA4A7D8C7871453A4F1215}

用以輔助管理連結追蹤；下列變數會在 `doPlugins` 函數執行前填入。

<!-- 

util_linkhandler.xml

 -->

您可以在 `doPlugins` 內使用下列值，以修改連結追蹤行為。例如，您可以中止追蹤，或將其他變數新增至追蹤要求。

<table id="table_55CCF4F2BF474FD3B703C926B896B392"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 變數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 影響 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> linkType </td> 
   <td colname="col2"> <p>包含自動決定的連結類型 (若有的話)。可設為下列其中一項:  </p> 
    <ul id="ul_81ACB5D00D774E86AFD22C61AD4D0E2C"> 
     <li id="li_52B6F2B124024DEFB422D1E9E97254C0">d (下載) </li> 
     <li id="li_E842C2E64F034181A364C639C30451FD">e (退出) </li> 
     <li id="li_3263F378CE65407E81B6C5C597CED1E8">o (自訂/其他) </li> 
    </ul> <p>這是影像請求中的 <code>pe</code> 參數。 </p> </td> 
   <td colname="col3"> <p>若與 <code>linkURL</code> 或 <code>linkName</code> 一起設定，則會傳送伺服器呼叫作為下載、自訂或退出連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkName </td> 
   <td colname="col2"> <p>會出現在自訂、下載或退出連結報表中的名稱。超過 100 個字元即開始截斷。可設為任何字串。 </p> <p>這是影像請求中的 <code>pev2</code> 參數。 </p> </td> 
   <td colname="col3"> <p> 若與 <code>linkType</code> 一起設定，則會傳送影像要求作為下載、自訂或退出連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkURL </td> 
   <td colname="col2"> <p>連結的 URL，當 linkName 不存在時將當做名稱使用。可設為任何 URL 字串。 </p> <p>這是影像請求中的 <code>pev1</code> 參數。 </p> </td> 
   <td colname="col3"> <p>若與 <code>linkType</code> 一起設定，則會傳送影像要求作為下載、自訂或退出連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkObject </td> 
   <td colname="col2"> <p>可供點按參考的物件。此為唯讀。 </p> </td> 
   <td colname="col3"> <p>對測量沒有直接影響。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**範例**

```js
function s_doPlugins(s) { 
    if (s.linkType == "d" && s.linkURL.indexOf(".aspx?f=") { 
        //special tracking for .aspx file download script 
        s.eVar11 = s.linkURL.substring(s.linkURL.lastIndexOf("?f=") + 3, s.linkURL.length); 
    } 
  
    else if (s.linkType == "o" ) { 
        // note: linkType is set to "o" only if you make a custom call 
        // to s.tl() and set the link type to "o". Automatically tracked 
        // links are set to "d" or "e" only. 
        s.eVar10 = s.LinkURL; 
    } 
}
```

## 驗證檔案下載、退出連結及自訂連結 {#concept_0B43AD582D3E470899FCCB58E44D3D49}

為完整驗證下載、退出及自訂連結，Adobe 建議使用封包分析器來即時檢查連結。

<!-- 

downloads_validate.xml

 -->

檔案下載、退出連結及自訂連結不屬於頁面檢視，因此無法使用 [!UICONTROL DigitalPulse 除錯程式]工具來驗證參數和變數設定。您必須使用[封包分析器](../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258) 檢視追蹤連結資料。
