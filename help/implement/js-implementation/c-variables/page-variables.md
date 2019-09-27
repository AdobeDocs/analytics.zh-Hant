---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics 實作
seo-description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
seo-title: 頁面變數
solution: Analytics
subtopic: 變數
title: 頁面變數
topic: 開發人員和實作
uuid: 2578eddd-74db-4a8a-96f2-d0289ec1826b
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# 頁面變數

頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。

## browserHeight {#concept_DB87062001824369A56AA1E7969EC02A}

 變數會顯示瀏覽器視窗的高度。

<!-- 
browserheight.xml
-->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>此變數應僅能讀取，且永遠不能設定。

您可以讀取這些值，並將其複製到 prop/eVar 中，但絕不可加以變更。此變數是隨 JavaScript 檔案的 H.11 版導入的。

**參數**

<table id="table_94598A2204CF42FF9DD14D353D5C0468"> 
 <thead> 
  <tr> 
   <th class="entry"> 查詢參數 </th> 
   <th class="entry"> 值 </th> 
   <th class="entry"> 範例 </th> 
   <th class="entry"> 受影響的報表 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>bh </p> </td> 
   <td> <p>正整數 </p> </td> 
   <td> <p>865 </p> </td> 
   <td> <p>流量 &gt; 技術 &gt; 瀏覽器高度 </p> </td> 
  </tr> 
 </tbody> 
</table>

## browserWidth {#concept_BA0C4C2D655D41A4AEF059E21E4A55A2}

 變數會顯示瀏覽器視窗的寬度。

<!-- 

browserwidth.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>此變數應僅能讀取，且永遠不能設定。

您可以讀取這些值，並將其複製到 prop/eVar 中，但絕不可加以變更。此變數是隨 JavaScript 檔案的 H.11 版導入的。

**參數**

<table id="table_B70F279A8CD240328520E5BD889806BD"> 
 <tbody> 
  <tr> 
   <td> <p> <b>查詢參數</b> </p> </td> 
   <td> <p> <b>值</b> </p> </td> 
   <td> <p> <b>範例</b> </p> </td> 
   <td> <p> <b>受影響的報表</b> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>bw </p> </td> 
   <td> <p>正整數 </p> </td> 
   <td> <p>1179 </p> </td> 
   <td> <p>流量 &gt; 技術 &gt; 瀏覽器寬度 </p> </td> 
  </tr> 
 </tbody> 
</table>

## campaign {#concept_C7BF7B8A69D048A6AB482052A98A91F8}

 變數可識別用以吸引訪客進入網站的促銷活動。 的值通常取自查詢字串參數。

<!-- 

campaign.xml

 -->

**參數**

<table id="table_A35175678B6C4D3D86287199AFBE6803"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大尺寸 </th> 
   <th class="entry"> 偵錯器參數 </th> 
   <th class="entry"> 填充報表 </th> 
   <th class="entry"> 預設值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>255 位元組 </p> </td> 
   <td> <p>v0 </p> </td> 
   <td> <p>轉換 &gt; 促銷活動 &gt; 追蹤代碼 </p> </td> 
   <td> <p>"" </p> </td> 
  </tr> 
 </tbody> 
</table>

促銷活動中的每個元素都應有一個相關聯的唯一追蹤代碼。例如，付費搜尋引擎關鍵字的追蹤代碼可能是 112233。當某人按一下追蹤代碼為 112233 的關鍵字時，將會被導向至對應的網站，而 *`campaign`*&#x200B;變數會記錄該追蹤代碼。

There are two main ways to populate the *`campaign`* variable:

* [!UICONTROL getQueryParam] 外掛程式，用於 JavaScript 檔案，可從 URL 中擷取查詢字串參數。如需 [!UICONTROL getQueryParam] 外掛程式的詳細資訊，請參閱 [實施外掛程式](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

* 為網頁上HTML *`campaign`* 中的變數指派值。

使用任一種填入變數的方 *`campaign`* 法，「上一步」按鈕流量可能會誇大促銷活動元素的實際點進次數。

例如，假設某個訪客在點選付費搜尋關鍵字後進入了您的網站。當訪客進入登陸頁面時，URL 會包含一個查詢字串參數，識別該關鍵字的追蹤代碼。接著，訪客點選了其他頁面的連結，但隨即又點選了「上一頁」按鈕，而返回登陸頁面。當訪客第二次進入登陸頁面時，含有查詢字串參數的 URL 會再次識別追蹤代碼。第二次點進也會註冊，而使點進次數不實膨脹。

為避免點進次數因此而膨脹，Adobe 建議您使用 [!UICONTROL getValOnce] 外掛程式，強制每個促銷活動點進在一個工作階段中僅計數一次。如需 [!UICONTROL getValOnce] 外掛程式的詳細資訊，請參閱 [實施外掛程式](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

**語法和可能的值** {#section_91A141841A6D4711A1EE08A6145A301D}

```js
s.campaign="112233"
```

The *`campaign`* variable has the same limitations as all other variables. Adobe 建議您將值限定為標準 ASCII 字元。

**區分大小寫** {#section_112A9A0F886148B6BEF9A7C94BE0A36F}

eVar 不區分大小寫，但會以第一次出現時的大寫格式顯示。例如，若 eVar1 的第一個例項設為 "Logged In"，但後續所有的例項皆以 "logged in" 的格式傳入，則報表一律會將 eVar 的值顯示為 "Logged In"。

**範例** {#section_705A25D05F6848E29C78320247AECB5F}

```js
s.campaign="112233"
```

```js
s.campaign=s.getQueryParam('cid');
```

**組態設定** {#section_4083F281968443169EAF8C0E8529D7BC}

每個促銷活動值在過期之前都會對使用者起作用，且會因為該使用者的活動和成功事件而獲得評價。您可以在「管理控制台」中變更促銷活動變數的到期日。

**缺陷、問題和提示** {#section_94B5C4BF9DE84BA3A16F9E9E9D197F0C}

* 若要避免點進次數不實膨脹，請使用 [!UICONTROL getValOnce] 外掛程式，使每個促銷活動點進在一個工作階段中僅計數一次。如需 [!UICONTROL getValOnce] 外掛程式的詳細資訊，請參閱 [實施外掛程式](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

* 如需追蹤促銷活動和關鍵字購買的詳細資訊，請參閱[促銷活動](https://marketing.adobe.com/resources/help/en_US/reference/campaign.html)。
* Use the [!DNL DigitalPulse Debugger] to see the actual value of campaigns (v0 in the debugger). 若除錯程式中未出現 v0，表示對於該頁面未記錄任何促銷活動資料。

## channel {#concept_C7770B8C15724A99B10F8F468AF82D0D}

 變數通常用於識別網站的某個區域。

<!-- 

channel.xml

 -->

例如，某零售商的網站擁有如電子產品、玩具或服飾等區域。媒體網站可能會有新聞、運動或商業等區段。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 100 位元組 | CH | 網站內容 &gt; 網站區域 | "" |

Adobe 建議在每個頁面上填入 channel 變數。您也可以開啟 *`channel`* 和[!UICONTROL 頁面名稱]變數之間的關聯。

When sections have one or more levels of subsections, you can show those sections in the *`channel`* variable or use separate variables to identify levels.

**語法和可能的值** {#section_ED90592730B64242A737F4090F1DCEE4}

```js
s.channel="value"
```

The *`channel`* variable has no extra limitations on its values.

**範例** {#section_2527B2BB1CFD46CB952178ABF7A9028A}

```js
s.channel="Electronics"
```

```js
s.channel="Media"
```

**缺陷、問題和提示** {#section_61941D5E4E644B59A267A4F44FD5DE8C}

If your site contains multiple levels, you can use the *`hierarchy`* or another variable to designate those levels. The *`channel`* value does not persist, but the success events fired on the same page are attributed to the *`channel`* value.

## colorDepth {#concept_756516E181F449B996DA9CC5A53FFA3D}

 變數可用來顯示畫面的每個像素上用以顯示顏色的位元數。

<!-- 

colordepth.xml

 -->

例如，32 代表畫面使用 32 位元的顏色。此變數會在頁面程式碼執行後、*`doPlugins`* 執行前填入。

>[!NOTE]
>
>此變數應僅能讀取，且永遠不能設定。

You may read these values and copy them into `props/eVars`, but you should never alter them. 此變數是隨 JavaScript 檔案的 H.11 版導入的。

| 查詢參數 | 值 | 範例 | 受影響的報表 |
|---|---|---|---|
| c | 8、16 和 32 | 32 | 流量 &gt; 技術 &gt; 螢幕色彩深度 |

## connectionType {#concept_2F98ECB8BB3D490F834F274EFF02860E}

 變數在 Internet Explorer 中會指出瀏覽器是設定於 LAN 還是數據機連線。

<!-- 

conntype.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>This variable should only be read and never set.

You may read these values and copy them into `props/eVars`, but you should never alter them. 此變數是隨 JavaScript 檔案的 H.11 版導入的。

| 查詢參數 | 值 | 範例 | 受影響的報表 |
|---|---|---|---|
| ct | LAN 或數據機 | LAN | 流量 &gt; 技術 &gt; 連線類型 |

## cookiesEnabled {#concept_DF5B37E38D0D4F6DB910F419F92467ED}

 變數會指出第一方工作階段 Cookie 是否可由 JavaScript 設定。

<!-- 

cookiesenabled.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>This variable should only be read and never set.

You may read these values and copy them into `props/eVars`, but you should never alter them. 此變數是隨 JavaScript 檔案的 H.11 版導入的。

| 查詢參數 | 值 | 範例 |
|---|---|---|
| k | Y 或 N | Y |

## dc {#concept_ECE6C83376704B3C84A920EFDD338A31}

(已過時)  變數可讓您選取您的資料所要傳送到的資料中心。

<!-- 

dc.xml

 -->

>[!NOTE]
>
>dc 變數已過時。您應將所有實施的 *`trackingServer`設為「程式碼管理員」在 s_code.js 中產生的值。*

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | 112 |

您可以在 *`dc`* 變數中識別資料中心，以比對 [!UICONTROL ActionSource]。

## eVarN {#concept_74FFDDB44B5344E18ABC6F2F99DF4649}

[!UICONTROL eVar] 變數可用來建置自訂報表。

<!-- 

eVarN.xml

 -->

當 eVar 設為某個訪客的值時，系統會記住該值，直到其過期為止。訪客在 eVar 值活動期間遇到的任何成功事件都會被計入 eVar 值。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 255 位元組 | V1-v75( [或v100或v250](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)) | 自訂轉換 | "" |

**過期** {#section_6DB5882B960D4660AE248B91B76883C4}

[!UICONTROL eVar] 會在經過您所指定的時段之後過期。eVar 過期後，即不會再獲得成功事件的評價。您也可以將 eVar 設定成隨著成功事件過期。例如，若您有某個內部促銷會在瀏覽結束時過期，此內部促銷將只會因為在購買或註冊啟動的瀏覽期間所發生的購買或註冊，而獲得評價。

有兩種方式可讓 eVar 過期: 

* 您可以將 eVar 設定成在指定的時段或事件之後過期。
* 您可以強制使 eVar 過期，這在重設變數用途時很適用。

If an eVar is used in May to reflect internal promotions and expires after 21 days, and in June it is used to capture internal search keywords, then on June 1, you should force the expiration of, or reset, the variable. 這麼做有助於將內部促銷值排除在六月的報表以外。

**區分大小寫** {#section_6E9145B7FCC2438E95BB35AAE3857412}

eVar 不區分大小寫，但會以第一次出現時的大寫格式顯示。例如，若 eVar1 的第一個例項設為 "Logged In"，但後續所有的例項皆以 "logged in" 的格式傳入，則報表一律會將 eVar 的值顯示為 "Logged In"。

**計數器**{#section_D8403F0C175E4BC9BE4F2E794B1F4D33}

eVar 通常會用來放置字串值，但也可設定作為計數器。當您嘗試計算使用者在某個事件之前所執行的動作數時，即可將 eVar 當作計數器使用。例如，您可以使用 eVar 擷取購買之前的內部搜尋次數。每次訪客搜尋時，eVar 中都應會有 '+1' 值。若訪客在購買之前做了四次搜尋，您將會看見各個總計數的例項: 1.00、2.00、3.00、4.00。但只有 4.00 會獲得購買事件的評價 (訂購和收入度量)。eVar 計數器的值必須是正數。

**子關聯** {#section_2BEABBBC735241F4BA42E74D19B5AEE0}

[!UICONTROL 「自訂 eVar」]報表的一般需求之一，是必須能夠以一個[!UICONTROL 「自訂 eVar」]報表劃分另一個。例如，若一個 eVar 包含性別，另一個包含薪資，您可以問下列問題: 就網站上的女性訪客而言，有多少收入來自於年收入達 50,000 美元以上的女性。任何具有完整子關聯的 eVar，都可在報表中用於此類型的劃分。例如，若性別 eVar 已啟用完整子關聯，則所有其他自訂 eVar 報表都將能以性別來劃分，而性別也能以所有其他 eVar 來劃分。若要檢視兩份報表之間的關聯，只要有其中一份報表啟用完整子關聯即可。根據預設，[!UICONTROL 「促銷活動」]、[!UICONTROL 「產品」]和[!UICONTROL 「類別」]等報表都具有完整子關聯 (任何 eVar 都能以促銷活動或產品來劃分)。

**語法和可能的值** {#section_BD46438B14F3488FB9AC42994C317B06}

While eVars may be renamed, they should always be referred to in the JavaScript file by eVarX, where X is a number between 1 and 75 ( [or 100, or 250](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)).

```js
s.eVarX="value"
```

eVar 在未作為計數器時，會受到與所有其他變數相同的限制。若 eVar 為「計數器」，則預期應會接收 "1" 或 "2.5" 之類的數值。若指定了兩個以上的小數位數，eVar 計數器會進位至兩個小數位數。eVar 計數器不可包含負數。

**範例** {#section_B37F4B0D56734DA3AB02BB218825BA4E}

```js
s.eVar1="logged in"
```

```js
s.eVar23="internal spring promo 4"
```

**組態設定** {#section_BD1FE63001C84D3DB69F3DEE243960B6}

eVar可以在「 [!UICONTROL Analytics &gt;管理&gt;報表套裝&gt;編輯設定&gt;轉換&gt;轉換變數」中設定]。 所有 eVar 都能以[!UICONTROL 「名稱」]、[!UICONTROL 「類型」]、[!UICONTROL 「配置」]、[!UICONTROL 「在設定之後過期」]或[!UICONTROL 「重設」]來設定。每項組態設定會分開處理。

<table id="table_5C524B71520849FA8A9A6B79A3EE77C9"> 
 <thead> 
  <tr> 
   <th class="entry"> 設定 </th> 
   <th class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 名稱  </td> 
   <td> 可讓您變更 <span class="keyword">Analytics</span> 中的 eVar 報表名稱。 <p>無論在 <span class="keyword">Analytics</span> 中為報表指定什麼名稱，eVar 在 JavaScript 程式碼中仍會參照為 s.eVarX。 </p> </td> 
  </tr> 
  <tr> 
   <td> 類型 </td> 
   <td> 可讓您說明 eVar 是文字字串還是計數器。 </td> 
  </tr> 
  <tr> 
   <td> 配置 </td> 
   <td> 用以設定哪個 eVar 值會獲得成功事件的評價。 <p>若「配置」設為「最近 (最後一個)」，則 B 會獲得評價。 </p> <p>若「配置」設為「原始值 (第一個)」，則 A 會獲得評價。 </p> <p>若「配置」設為「線性」，則 A 和 B 會各獲得購買值一半的評價。 </p> </td> 
  </tr> 
  <tr> 
   <td> 過期時間 </td> 
   <td> 可讓您決定 eVar 會在特定事件 (如購買) 發生時過期，還是在自訂或預先定義的時段之後過期。 </td> 
  </tr> 
  <tr> 
   <td> 重設 </td> 
   <td> 為 eVar 選取<span class="wintitle">「重設」</span>核取方塊，然後按一下位於頁面底部的<span class="wintitle">「儲存」</span>，該 eVar 所有的值都會隨即過期。在此之後，將只有 eVar 的新值會獲得成功事件的評價。 </td> 
  </tr> 
 </tbody> 
</table>

**缺陷、問題和提示** {#section_DA6912C802E445F986C6DE4234C6C737}

* 不同於 [!UICONTROL prop] 變數，eVar 變數不可以是分隔值清單。若您為 eVar 填入值清單 (例如 "one,two,three")，這個字串將會照原樣出現在報表中。
* eVar 計數器不可包含負數。

## 事件 {#concept_FFD115543D54401B98FE683BD7D5B3FE}

 變數可用來記錄一般購物車成功事件以及自訂成功事件。

<!-- 

events.xml

 -->

<table id="table_9EB9D08C80544CD68C4B1A2012440472"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大尺寸 </th> 
   <th class="entry"> 偵錯器參數 </th> 
   <th class="entry"> 填充報表 </th> 
   <th class="entry"> 預設值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 不限 </td> 
   <td> 事件 </td> 
   <td> <p>購物車事件 </p> <p>自訂事件 </p> </td> 
   <td> 不適用 </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL 事件]應被視為網站上的里程碑。成功事件最常會填入至程序的最終確認頁面上，例如註冊程序或商務通訊註冊。自訂事件可藉由以下面「可能的值」一節中所定義的文字值填入事件變數來定義。

根據預設，成功事件會設定為&#x200B;*計數器*&#x200B;事件。計數器事件會計算成功事件的設定次數 (x+1)。事件也可設定為&#x200B;*數值*&#x200B;事件。數值事件可讓您指定所要增加的數值 (可能會在計算動態值或任意值時用到，例如內部搜尋所傳回的結果數)。

最後一個事件類型是&#x200B;*貨幣*，可讓您定義所要增加的金額 (類似於數值事件)，但在報表中會以貨幣的形式顯示，且必須遵循以 s.*`currencyCode`* 值和報表套裝預設貨幣設定為基礎的貨幣轉換方式。For additional information on using numeric and currency events, see [Products](../../../implement/js-implementation/c-variables/page-variables.md#concept_A4007F6307E4419DAA65E1668A8FEBA2).

**設定變數** {#section_9195286C34C54B02B2598E2B856492C3}

依預設會為所有實施啟用 [!UICONTROL s.events] 變數。對於所有新的報表套裝，都會自動啟用七項預先設定的轉換事件。New custom events (event1- [event100 or event1000](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)) can be enabled by any admin-level user using the Admin Console.

**可能的值** {#section_18395A3BEFEB4E9F8D7B2ED0001FBE4E}

以下列出事件變數可使用的值: 

| 事件 | 說明 | 填充報表 |
|---|---|---|
| prodView | 產品檢視 | 產品 |
| scOpen | 開啟/初始化新的購物車 | 購物車 |
| scAdd | 將項目新增至購物車 | 購物車新增 |
| scRemove | 從購物車中移除項目 | 購物車移除 |
| scView | 檢視購物車 | 購物車檢視 |
| scCheckout | 結帳程序開始 | 結帳 |
| 購買 | 購買 (訂購) 完成 | 訂購 |
| event1 - event1000 (單點產品為 event100) | 自訂事件 | 自訂事件 |

**語法和範例** {#section_45A159DF00114066B8551DDEB15E084C}

計數器事件的設定方式，是將所需事件放入 [!UICONTROL s.events] 變數中 (若要傳送多個事件，則需使用逗號分隔清單)。

```js
s.events="scAdd"
```

```js
s.events="scAdd,event1,event7"
```

```js
s.events="event5"
```

```js
s.events="purchase,event10"
```

若是使用 H23 程式碼或更高版本，則可為計數器事件指派大於一的整數。

```js
s.events="event1=10"
```

```js
s.events="scRemove=3,event6,event2=4"
```

以指派的整數值實施計數器事件時，會將事件視為在影像要求內引發了多次。計數器事件不允許使用小數 - 如需使用此功能，建議您改用數值事件。數值和貨幣事件雖然通常會透過 [!UICONTROL s.products] 變數接收其數值 (例如 24.99)，但這些事件必須包含在 [!UICONTROL s.events] 變數中。如此可讓您將特定數值和貨幣值連結至個別的產品項目。

**事件序列化** {#section_A89488EF4471405AAFC4D6DD05E77621}

根據預設，每次在您的網站上設定事件時，都會對該事件計數。

請參閱[事件序列化](../../../implement/js-implementation/event-serialization.md#concept_092B638D7FEE423D91F8A57EA8E09705)，以瞭解詳細資訊。

**語法** {#section_8559D42D3F344AF3BB3C0125F78C4989}

```js
s.events="event1:3167fhjkah"
```

**範例** {#section_7B5B5728A59648ADB3E2548CDAD2C9D4}

```js
s.events="scAdd:003717174"
```

```js
s.events="scAdd:user228197,event1:577247280,event7:P7fhF8571"
```

## hierN。{#concept_C4475D1584D544ACB4C0A573EB60FA08}

[!UICONTROL 階層]變數會決定某個頁面在您的網站階層中的所在位置。

<!-- 

hierN.xml

 -->

此變數對於擁有超過三層結構的網站尤其實用。例如，媒體網站可能會將「運動」區段分成 4 個層級: 運動、地方運動、棒球、紅襪隊。若有人瀏覽了「棒球」頁面，則「運動」、「地方運動」和「棒球」等層級全都會反映該次瀏覽。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 255 位元組 | H1-H5 | 階層 | "" |

可用的[!UICONTROL 階層]變數共有五個，必須由 Adobe 客戶服務啟用。在啟用階層時，您應決定要用於變數的分隔字元，以及該階層的最大層級數。例如，如果分隔字元為逗點，則運動階層可能顯示如下。

```js
s.hier1="Sports,Local Sports,Baseball"
```

請確定您的區段名稱皆未包含分隔字元。例如，若您其中一個區段的名稱為 "Coach Griffin, Jim"，您即應選擇逗號以外的分隔字元。每個階層區段限定使用 255 個位元組，而變數的總限制為 255 位元組。分隔字元在選定 (在建立階層時) 後即不易變更。

請向 Adobe 客戶服務洽詢為現有階層變更分隔字元的相關事宜。分隔字元亦可由多個字元組成，如 || 或 /|\，這些字元較少出現在階層區段中。

**語法和可能的值** {#section_0739948A68A2420DAB1CBEA3115A5A66}

請不要在各個分隔字元之間放置空格。在下列範例語法中，N 是介於一與五之間的數值。

```js
s.hierN="Level 1[<delimiter>Level 2[<delimiter>Level 3[...]]]"
```

除了分隔階層的層級外，請不要使用分隔字元。分隔字元可以是您所選擇的一或多個任何字元。

**範例** {#section_38E0929F88DD45B6ACDF473DF155971D}

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub"
```

```js
s.hier4="Sports/Local Sports/Baseball"
```

**組態設定** {#section_E823FB3CAD744D2480EBCE2DF9B134CC}

無

**缺陷、問題和提示** {#section_104E5BD320764BDEA5FA8D13A70C78E3}

* 一旦設定階層後，分隔字元即不可變更。若必須變更階層的分隔字元，請與 Adobe 客戶服務連絡。
* 在設定階層後，層級的數量即不可變更。

>[!NOTE]
>
>對階層的更改可能導致服務費用。

## homepage {#concept_0A3E416F1A064BA396B5FCEABFB7B0B4}

變數在Internet explorer中會指出目前頁面是否設定為使用者的首頁。

<!-- 

homepage.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>此變數應僅能讀取，且永遠不能設定。

您可以讀取這些值，並將其複製到 prop/eVar 中，但絕不可加以變更。此變數是隨 JavaScript 檔案的 H.11 版導入的。

| 查詢參數 | 值 | 範例 | 受影響的報表 |
|---|---|---|---|
| hp | Y 或 N | Y | 流量 &gt; 技術 &gt; 首頁 |

## javaEnabled {#concept_F24A3536F1F0453DA214B16BAA5A6F67}

 變數會指出瀏覽器上是否啟用了 Java。

<!-- 

javaEnabled.xml

 -->

此變數會在頁面程式碼執行後、doPlugins 執行前填入。

>[!NOTE]
>
>此變數應僅能讀取，且永遠不能設定。

您可以讀取這些值，並將其複製到 prop/eVar 中，但絕不可加以變更。此變數是隨 JavaScript 檔案的 H.11 版導入的。

| 查詢參數 | 值 | 範例 | 受影響的報表 |
|---|---|---|---|
| v | Y 或 N | Y | 流量 &gt; 技術 &gt; Java |

## javascriptVersion {#concept_19E2C9F87BB24E69B911C0F5873CAA90}

 變數會指出瀏覽器支援的 JavaScript 版本。

<!-- 

javascriptVersion.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>此變數應僅能讀取，且永遠不能設定。

您可以讀取這些值，並將其複製到 prop/eVar 中，但絕不可加以變更。此變數是隨 JavaScript 檔案的 H.11 版導入的。

| 查詢參數 | 值 | 範例 | 受影響的報表 |
|---|---|---|---|
| j | 1.0, 1.1, 1.2, … 1.7 | 1.7 | 流量 &gt; 技術 &gt; JavaScript 版本 |

JavaScript 檔案的 H.10 版和更高版本可正確偵測到 1.7 版 (H.10 發行時的最高版本)。舊版的 JavaScript 檔案版本最高只能偵測到 1.3 版

## linkName {#concept_1B2A3F56C9AD4C23A8A4331730EC2B8F}

The  variable is an optional variable used in [!UICONTROL Link Tracking] that determines the name of a custom, download, or exit link.

<!-- 

linkName.xml

 -->

The *`linkName`* variable is not normally needed because the third parameter in the *`tl()`* function replaces it.

<table id="table_4B0D1C9AADA542A59B626E077D5FC568"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大尺寸 </th> 
   <th class="entry"> 偵錯器參數 </th> 
   <th class="entry"> 填充報表 </th> 
   <th class="entry"> 預設值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 100 位元組 </td> 
   <td> pev2 </td> 
   <td> <p>檔案下載 </p> <p>自訂連結 </p> <p>退出連結 </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL 「自訂連結」]是指傳送追蹤資料的連結。此 *`linkName`* variable (or the third parameter in the *`tl()`* function) is used to identify the value that appears in the [!UICONTROL Custom], [!UICONTROL Download], or [!UICONTROL Exit Links] report. If *`linkName`* is not populated, the URL of the link appears in the report.

**語法和可能的值** {#section_C8D89834C98B4C7A858C947293C4148E}

```js
s.linkName="Link Name"
```

There are no limitations on *`linkName`* outside of the standard variable limitations.

**範例** {#section_5F68766210184E82A23D2A6ECD80BA0B}

```js
s.linkName="Nav Bar Home Link"
```

```js
s.linkName="Partner Link to A.com"
```

**組態設定** {#section_F15FF429FC274F708D50DF79D4668EA3}

無

**缺陷、問題和提示** {#section_170A78452A7340B5B229713AC1FB71FA}

* The *`linkName`* variable is replaced by the third parameter in the *`tl()`* function.

* If the *`linkName`* variable and the third parameter in the *`tl()`* function are blank, the full URL of the link (with the exception of the query string) appears in the report (even if the link is relative).

## linkType {#concept_7695692AF5D843E3B370F6D345E32964}

 變數是一個用於連結追蹤中的可選變數，可判斷會出現連結名稱或 URL 的報表 (自訂、下載或退出連結)。

<!-- 

linkType.xml

 -->

The *`linkType`* variable is not normally needed because the second parameter in the *`tl()`* function replaces it.

<table id="table_3D1A2FC1CECD4709BE2F9E32AC2DC730"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大尺寸 </th> 
   <th class="entry"> 偵錯器參數 </th> 
   <th class="entry"> 填充報表 </th> 
   <th class="entry"> 預設值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 一個字元 </td> 
   <td> pe=[lnk_o|lnk_d|lnk_e] </td> 
   <td> <p>檔案下載 </p> <p>自訂連結 </p> <p>退出連結 </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

自訂連結會將資料傳送至 Analytics。The *`linkType`* variable (or the second parameter in the *`tl()`* function) is used to identify the report in which the link name or URL appears ( [!UICONTROL Custom], [!UICONTROL Download], or [!UICONTROL Exit Links] report).

對於退出和下載連結， *`linkType`* 會根據所點按的連結是退出或下載連結，自動填入變數。 A custom link may be configured to send data to any of the three reports with this variable or with the second parameter in the *`tl()`* function. 若設 *`linkType`* 定為'o'、'e'或'd', *`linkName`* 或連結URL會分別傳送至「自訂連結 [!UICONTROL 」、「]退出連結 [!UICONTROL 」或「檔案下載] 」報表。

**語法和可能的值** {#section_18DB3A8083FB4F75B970055ED336DA4E}

The *`linkType`* variable syntax depends on whether you use XML or a query string.

若使用 XML，變數可能僅會包含單一字元 (即「o」、「e」或「d」)。

```js
s.tl(this,’o’,’Link Name’);
```

If you are using the query-string `pe`, you need to use `lnk_d`, `lnk_e`, or `lnk_o`.

**範例** {#section_242B5DFFD1C9462A9A8EB1556B2E3160}

```js
<a href="index.html" onClick=" 
 var s=s_gi('rsid'); **see note below on the rsid** 
 s.tl(this,'o','Link Name'); 
 ">My Page</a> 
```

**組態設定** {#section_59738AD1B5E94294B8D36F4E772DEDB3}

無

**缺陷、問題和提示** {#section_F0D01DDE3FDA486C987162DA50A79C45}

* 如果 *`linkType`* 未指定，則會假設自訂連結('o')。

## 清單 Prop {#concept_83ED74232225431F83A796E22FFC75B4}

清單 prop 是一份使用分隔字元的值清單，會在傳入至變數後，以個別明細項目的形式來報告。清單 prop 最常在含有使用者可選值的頁面上實施，例如具有核取方塊或選項按鈕的清單項目。清單 prop 在任何您需要於一個變數中定義多個值，但不想傳送多個影像要求的情況下皆適用。

<!-- 

list_props.xml

 -->

**考量事項**

* 清單 prop 只能對流量變數 ([prop](../../../implement/js-implementation/c-variables/page-variables.md#concept_0F10FA2DE69B4029A31EA5E9313AA254)) 啟用。
* 您無法為清單 prop 啟用路徑分析和關聯。
* 幾乎每個報表都可獲得 Analytics 提供的瀏覽和獨特訪客資料，包括所有的清單 prop 報表在內。
* 清單 prop 支援分類功能。
* 任何自訂流量變數皆可成為清單 prop。(例外: [pageName](../../../implement/js-implementation/c-variables/page-variables.md#concept_5827B499DAC34B5D8445F9D9140CC328)、 [channel](../../../implement/js-implementation/c-variables/page-variables.md#concept_C7770B8C15724A99B10F8F468AF82D0D)和 [server](../../../implement/js-implementation/c-variables/page-variables.md#concept_BF77952603BA454BAFC9A0A81D06A7D2)。)

* 在相同的影像要求中定義重複值時，不會對例項進行重複資料刪除。

在「管理工具 &gt; 報表套裝 &gt; 流量變數」頁面上啟用「清單支援」接著選取分隔字元，即可將 Prop 變更為清單 Prop。常用的分隔字元有冒號、分號、逗號或垂直線。技術上而言，分隔字元可以是前 127 個 ASCII 字元中的任一個。

**實施範例** {#section_A3DD7293A8BB4807B42BFB1F73BE11AC}

在要求啟用清單 prop 時，請指定您要使用的分隔字元。在啟用您所選擇的 *`s.prop`* 後，您可以在此變數中設定多個值，如下列範例所示:

以垂直線分隔的清單 prop，會傳入兩個值:

```js
s.prop1="Banner ad impression|Sidebar impression"
```

以逗號分隔的清單 prop，會傳入數個值:

```js
s.prop2="cerulean,vermilion,saffron"
```

清單 prop 也可以傳送單一值:

```js
s.prop3="Single value"
```

分隔字元可隨時變更。但實施必須符合新的分隔字元。若未使用正確的分隔字元，將使清單 prop 值在報表中被視為連結的單一明細項目。

由於清單 prop 仍屬於流量變數，因此仍受流量變數限制的規範。清單 prop 限定為 100 個位元組的資料，並且會受到區分大小寫設定的影響。

## 清單變數 {#concept_AC42F2D69B674C02A484137CE5B4E687}

也稱為清單變數 (List Var)。清單變數的運作方式與清單 Prop 類似，也允許相同影像要求中可有多個值。其運作方式也類似於 eVar，可獨立存留於其定義所在之影像要求外。您可以使用這些變數來檢視單一頁面上多個元素的因果關係，例如產品清單、期望清單、進階搜尋清單或顯示廣告清單等。

<!-- 

listN.xml

 -->

**考量事項**

* 清單變數會參照訪客瀏覽器中的 VisitorID Cookie 以記憶其值。
* 每次每名訪客可儲存至多 250 個數值。如果超出每位訪客 250 個值，系統會使用最近的 250 個值。上述值的有效期會依據清單變數的有效期設定。
* 每個分隔值最多可包含 255 個字元 (若使用多位元組字元則更低)。此為單一元素的最大長度。
* 此變數中沒有字元數上限。此限制唯一的例外是在使用較舊的 Internet Explorer 瀏覽器時，此類瀏覽器會對所有的 URL 要求施加 2083 個字元的限制。
* 每個報表套裝皆可使用三個清單變數。
* 要使用清單變數，必須要使 H23 程式碼或更高版本。
* 清單變數可以分類。
* 若在相同的影像要求中定義重複值，清單變數會對這些值的所有例項進行重複資料刪除。
* 點擊 (或頁面檢視) 層級是清單變數劃分最精細的層級。若您有某個清單變數在相同的影像要求中有三個值，有任何區段規則符合其中一值時，即會將這三個值都提取到報表中。相反地，若定義的排除規則符合單一值，則會將這三個值都排除。

**設定** {#section_8CADFF581D2447518BA3F7F79B2D80A9}

您可從管理控制台存取設定並進行更新，無需連絡 Adobe 客戶服務:

1. Go to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**
1. 選取報表套裝。
1. Click  **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL List Variables]** .

* **名稱**: 每個分隔值最多可包含 255 個字元 (若使用多位元組字元則更低)。此為單一元素的最大長度。
* **值分隔字元**: 在清單變數中用來分隔值的字元。最常用的分隔字元包括逗號、冒號、垂直線或類似字元。

   >[!NOTE]
   >
   >清單變數中不支援多位元組字元做為分隔字元。 分隔字元必須是單一位元組。

* **有效期**: 此項目類似於 eVar 有效期，可決定清單變數與轉換事件之間可產生關聯的時間長度。

   * **在頁面檢視或瀏覽層級**: 頁面檢視或瀏覽以外的成功事件將不會連結回清單變數內的任何值。
   * **根據日、週、月等時段**: 指定時段以外的成功事件將不會連結回清單變數內的任何值。此外也可定義自訂天數。
   * **特定轉換事件**: 任何在指定的特定事件之後引發的其他成功事件，都不會連結回清單變數內的任何值。
   * **從不**: 清單變數與成功事件之間沒有時間上的限制。

* **配置**: 此設定會決定成功事件將評價分配給值的方式: 

   * **完整**: 所有在變數的有效期之前定義的變數值，都會獲得成功事件的完整評價。
   * **線性**: 所有在變數的有效期之前定義的變數值，都會獲得轉換事件的分配評價。
   * 一律不會覆寫變數值，而會新增至獲得成功事件之評價的值。

* **值數目上限**: 指定此清單變數允許的作用中值數目。例如，若設為 3，則只會儲存擷取到的最後 3 個值，並捨棄所有先前的值。請注意，如果同一個點擊針對相同清單變數傳送了多個值，且您使用值數目上限設定了限制，則每個值會有相同的時間戳記，且無法保證將儲存哪個值。

   每次每名訪客可儲存至多 250 個數值。如果超出每位訪客 250 個值，系統會使用最近的 250 個值。上述值的有效期會依據清單變數的有效期設定。

   「值數目上限」設定可用於限制對特定值數目的歸因。例如，如果在瀏覽的第一頁將清單變數設為 "A,B,C"，接著在第二頁設為 "X,Y,Z"，則會根據分配方法將歸因分配給這 6 個值。如果您想將歸因限制給 "X,Y,Z"，則可將值數目上限設定為 3。

To set up or edit List Vars, go to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL List Variables]** .

**實施範例** {#section_564AFE6A2F524BFEB372EC0F7FEBA656}

下列每個範例都使用逗號做為值的分隔字元。

**在清單變數內定義單一值:**

```js
s.list1="Cat";
```

**傳入多個值:**

```js
s.list2="Tabby,Persian,Siamese"; 
s.list1="Product 1,Product 2,Product 3";
```

**將收入計入清單變數中:**

```js
//Define this code on the landing page: 
s.list3="Top Banner Ad,Side Bar Ad,Internal Campaign 1"; 
 
//Have these variables fire on the purchase confirmation page: 
s.products=";Kitten;1;50" 
s.events="purchase";
```

此結果會顯示三個收入各為 50 美元的明細項目。(頂端橫幅廣告、側邊廣告與內部促銷活動 1。)請注意，此報表的總計會對收入進行去重複化，因此總計也將呈現為 50 美元。

**將收入計入在瀏覽期間設定多次的清單變數中:**

**配置**: 完整

**過期**: 瀏覽

<table id="table_09E1879B44624A858555449E2DC74E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 頁面 </th> 
   <th colname="col2" class="entry"> s.list1 </th> 
   <th colname="col3" class="entry"> s.events/s.products </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 頁面 1 </td> 
   <td colname="col2"> <code> s.list1=”value1,value2,value3”; </code> </td> 
   <td colname="col3"> (未設定) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 頁面 2 </td> 
   <td colname="col2"> <code> s.list1=”value4,value5,value6”; </code> </td> 
   <td colname="col3"> <p> <code> s.events=”purchase”; </code> </p> <p> <code> s.products=”;product;1;200” </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**結果**: 所有在瀏覽期間的任何時間點設定於清單 var1 中的值 (value1,value2,value3,value4,value5,value6)，都會獲得購買的完整評價。

## maxDelay {#concept_B355038C3B094BB68C0DC6C80F9FE5B0}

s.maxDelay 變數主要用於 Genesis DFA 整合，用以決定聯繫 DFA 主機時的逾時期間。若 Adobe 未在 變數中設定的指定期間內接收到來自 DFA 伺服器的回應，連線即會中斷，而資料會正常處理。若您對 DFA 各頁面的回應時間有所顧慮，請實施此變數。建議您先以此值進行測試，以找出最理想的逾時期間。

<!-- 

maxDelay.xml

 -->

**實施範例**

```
s.maxDelay="750";
```

**屬性**

* 此變數是會透過網站上實施的 JavaScript 而填入的選用事件度量。
* 若 DFA 主機未在指定的時間內回應，指定給「逾時」的事件即會執行 (透過 Genesis 整合精靈指派)。
* 此變數只能包含數值。
* 指定的時間長度以毫秒為單位。
* 增加等待時間可以收集到較多 DFA 資料，但也會提高 Analytics 點擊資料的遺失風險。

   Losing Analytics hit data would occur when the user navigates away from the page during the *`s.maxDelay`* period.

* 減少等待時間可降低 Analytics 點擊資料的遺失風險，但也可能減少隨點擊資料傳送的 DFA 資料量。

   當時段無法容納DFA主 *`s.maxDelay`* 機回應的足夠時間時，會遺失DFA整合資料。

>[!NOTE]
>
>Adobe does not have control over DFA's response time. 若在最大延遲時段已提高至合理的時間長度後仍持續出現問題，請洽詢組織的 DFA 帳戶管理員。

## mediaLength {#concept_F52B1670122C4461824223E525307060}

 變數會指定所要播放之媒體的總長度。

<!-- 

mediaLength.xml

 -->

<table id="table_B1AE8A9DF9D545C2965CDB2DB6C2969B"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大尺寸 </th> 
   <th class="entry"> 偵錯器參數 </th> 
   <th class="entry"> 填充報表 </th> 
   <th class="entry"> 預設值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 整個 pev3 要求沒有大小上限 - 大小會限定為瀏覽器的 URL 長度限制。 </td> 
   <td> pev3 </td> 
   <td> 視訊逗留時間; <p>已檢視的視訊分段 </p> </td> 
   <td> 無 </td> 
  </tr> 
 </tbody> 
</table>

**語法和可能的值** {#section_FEC1B01FDD234ACEB63C0558BEEB5CBC}

** autoTrack方法：**

若使用 [!UICONTROL s.Media.autoTrack]，則無須明確實施 [!UICONTROL mediaLength] 變數。這會由「JavaScript 適用的 AppMeasurement」程式碼自動決定。

**手動追蹤方法:**

語法:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

可能的值: 

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**範例** {#section_048B2D31BB584647A5D335AE94E5A599}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3= [Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**缺陷、問題和提示** {#section_1CEDC78FEF4940E9BC02A2AF1EE2FB01}

* 只有在無法使用 [!UICONTROL s.Media.autoTrack] = true 來追蹤播放器時，才須呼叫媒體追蹤方法。
* 若未使用 [!UICONTROL autoTrack] 進行追蹤，請確實設定長度 (以秒為單位)。

## mediaName {#concept_A4CB1782DE244C23BA6CBB5E806DDE6A}

此變數會指定視訊或媒體項目的名稱。

<!-- 

mediaName.xml

 -->

此變數只能透過[!UICONTROL 「資料插入 API」]和[!UICONTROL 「完整處理資料來源」]來使用。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 64KB | pev3 | 視訊、下一視訊流量、上一視訊流量、已檢視的視訊區段、視訊逗留時間 | 無 |

**語法和可能的值** {#section_F97A2253BBD24FEBBC225F233A319F5D}

**autoTrack 方法:**

若使用 [!UICONTROL s.Media.autoTrack]，則無須明確實施 *`mediaName`* 變數。這會由「JavaScript 適用的 AppMeasurement」程式碼自動決定。

**手動追蹤方法:**

語法:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

```js
s.Media.close(mediaName)
```

可能的值: 

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

**範例** {#section_4B9584265B1A47289818141B2A88021D}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 Values: 
  pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 
  11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32  
  
```

**缺陷、問題和提示** {#section_941A445BB52E4063B0F6920E61BB90DE}

* 只有在無法使用 [!UICONTROL s.Media.autoTrack] = true 來追蹤播放器時，才須呼叫媒體追蹤方法。
* 此變數儲存為 mySQL TEXT 變數，以與 VARCHAR(100) 相對照。

## mediaPlayer {#concept_1932756C093B4B2FBA0484E5A58EF927}

此變數會指定用來使用視訊或媒體項目的播放器。

<!-- 

mediaPlayer.xml

 -->

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 100 位元組 | pev3 | 視訊播放器 | 無 |

**語法和可能的值** {#section_EAA55A3A45B5405F903E3BE6ACAB143F}

**autoTrack 方法:**

```js
s.Media.playerName = "My Custom Player Name"  //configure player name in global JavaScript or ActionSource
```

**手動追蹤方法:**

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

可能的值: 

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**範例** {#section_64967E1333D542CCB6CF62F0A1E0EF88}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers] 
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**缺陷、問題和提示** {#section_0020E031338F4A4880B9AC5B9A85BEF5}

只有在無法使用 s.Media.autoTrack = true 來追蹤播放器時，才須呼叫媒體追蹤方法。

## mediaSession {#concept_19E6C850C3244CB6973140709BDCB0B9}

此變數會指定所使用的視訊或媒體資產區段。

<!-- 

mediaSession.xml

 -->

<table id="table_8681473270FE44DFBBCCC0FBA6737104"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大尺寸 </th> 
   <th class="entry"> 偵錯器參數 </th> 
   <th class="entry"> 填充報表 </th> 
   <th class="entry"> 預設值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 255 位元組 </td> 
   <td> pev3 </td> 
   <td> 視訊逗留時間 <p>已檢視的視訊分段 </p> </td> 
   <td> 無 </td> 
  </tr> 
 </tbody> 
</table>

**語法和可能的值** {#section_9A63266633C4427CB4A6549E4D887B85}

**autoTrack 方法:**

若使用 [!UICONTROL s.Media.autoTrack]，則無須明確實施 *`mediaName`*。這會由「JavaScript 適用的 AppMeasurement」程式碼自動決定。

**手動追蹤方法:**

語法:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

可能的值: 

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

**範例** {#section_3446EC37E017407FA3F43C9BDAEA0B85}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32 
```

**缺陷、問題和提示** {#section_1BCEB037AB724B6EBE87420BD3604B88}

只有在無法使用 [!UICONTROL s.Media.autoTrack] = true 來追蹤播放器時，才須呼叫媒體追蹤方法。

## Media.trackEvents {#concept_B1C5FF6C437949EBA5D52040AC6BB6D9}

 變數可識別哪些事件應隨媒體點擊而傳送。

<!-- 

media_trackEvents.xml

 -->

此變數僅適用於 JavaScript 和 [!UICONTROL ActionSource]。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | s.Media.trackEvents="None" |

**語法和可能的值** {#section_66A978EF56914BEAAE73359A268A1B4A}

事件名稱，例如 event1 或 purchase。

**範例** {#section_140A55D80EA24011954F9383CF312237}

```js
s.Media.trackEvents=”event1,purchase”
```

**缺陷、問題和提示** {#section_030B11C64EE84D46A85CA550DB732D28}

請確實在每次填入此變數時，為 [!UICONTROL trackVars] 填入「事件」。

## Media.trackVars {#concept_4350CA9A892148AE93C8133AB3B4BEA4}

 變數可識別哪些變數應隨媒體點擊而傳送。

<!-- 

media_trackVars.xml

 -->

此變數僅適用於 JavaScript 和 [!UICONTROL ActionSource]。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | s.Media.trackVars="None" |

**語法和可能的值** {#section_7374684A7EB34AE685E8C40A66CFD289}

變數名 [!UICONTROL 稱]，如 *`eVarN`* propN *`events`*、 *`channel`*、等。

**範例** {#section_48653222ABA14AB0A3C4471659971FAA}

```js
s.Media.trackVars=”prop2,events,eVar3”
```

**缺陷、問題和提示** {#section_615AE1B696124B00B78F651B03813EAB}

* 即使在 [!UICONTROL trackVars] 中指定 eVar3，它仍會隨媒體點擊傳送。

## mobile {#concept_0CEE045F57B444138C0EAA015FC7EA70}

變數會控制使用Cookie和訂閱者ID來識別訪客的順序。

<!-- 

mobile.xml

 -->

See [Mobile network protocols](../../../implement/js-implementation/c-additional-libraries/network-protocols.md#concept_2425537FC9CB45DD868B5FA2298B6CAC).

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 影像 URL 路徑中的 /5/ 或 /1/ | 不適用 | 無 |

**語法和可能的值** {#section_7F1C58090C454882BA9D3D66C9263A76}

```js
s.mobile="any_string" //subscriber id used first, produces /5/ in path of image url 
s.mobile=""  // if set to an empty string or not set at all, cookies used first, produces /1/ in path of image url 
```

**缺陷、問題和提示** {#section_06CD5CB4EF1E4B9FBE3B9D1F18AAFA30}

使用跨訪客身分識別，可降低在將變數與JavaScript cookie實作搭配使用時 *`s.mobile`* 訪客流量可能出現的尖峰。

## pageName {#concept_5827B499DAC34B5D8445F9D9140CC328}

 變數包含您的網站上各個頁面的名稱。

<!-- 

pageName.xml

 -->

<table id="table_0D09BAEC2FFD43F7905ED3649B3F8E05"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大尺寸 </th> 
   <th class="entry"> 偵錯器參數 </th> 
   <th class="entry"> 填充報表 </th> 
   <th class="entry"> 預設值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 100 位元組 </td> 
   <td> pageName </td> 
   <td> <p>頁面 </p> <p>路徑 </p> </td> 
   <td> 頁面 URL </td> 
  </tr> 
 </tbody> 
</table>

此&#x200B;*`pageName`* 變數中應填入商業使用者可辨識的值。在大多數情況 *`pageName`* 下，值不是URL或檔案的路徑。 Common *`pageName`* values include names such as "Home Page," "Checkout," "Purchase Thank you," or "Registration."

請留意勿讓新行字元、長破折號/短破折號或任何 HTML 字元出現在頁面名稱和其他變數中。有些瀏覽器會傳送新行字元，有些則否，這會使 Analytics 中的資料在兩個看似相同的頁面名稱之間出現歧異。有許多文字處理器和電子郵件用戶端會在您鍵入時自動將連字號轉換為短破折號或長破折號。由於短破折號和長破折號在 Analytics 變數中屬於非法字元 (字元碼超過 127 的 ASCII 字元)，Analytics 將不會記錄含有非法字元的頁面名稱，而會改為顯示 URL。

If *`pageName`* is left blank, the URL is used to represent the page name. Leaving *`pageName`* blank is often problematic because the URL may not always be the same for a page `www.mysite.com` and `mysite.com` are the same page with different URLs).

**語法和可能的值** {#section_7A61EE70F1A84D26B414404998C84BA8}

The *`pageName`* variable should contain a useful identifier for business users of Analytics.

```js
s.pageName="page_name"
```

There are no limitations on *`pageName`* outside of the standard variable limitations.

**範例** {#section_8BB4F86F84E246A08B72DEC47FFC0765}

```js
s.pageName="Search Results" 
```

```js
s.pageName="Standard Offer List"
```

**組態設定** {#section_58CBC68C805344A999EB47455FEBA8D5}

管理員可在 Analytics 中使用[!UICONTROL 「命名頁面」]工具變更可見的頁面名稱，但這隱含潛在風險，且可能對您的報表造成負面影響。使用「命名頁面」工具前，請先與 Adobe [!UICONTROL 客戶服務]連絡。

**缺陷、問題和提示** {#section_BB41DC9682C34385B9CAA80D5257C113}

請確定 *`pageName`* 不包含非法字元。

## pageType {#concept_F67870238EF74491B5D3909A33CDB985}

 變數的用途僅止於指定 404 (找不到頁面) 錯誤頁面。

<!-- 

pageType.xml

 -->

<table id="table_0492B136E9D14070A6CA49ED534BCA4C"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大尺寸 </th> 
   <th class="entry"> 偵錯器參數 </th> 
   <th class="entry"> 填充報表 </th> 
   <th class="entry"> 預設值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 20 位元組 </td> 
   <td> pageType </td> 
   <td> 路徑 &gt; 頁面 &gt; 找不到頁面 <p>找不到 </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

此 *`pageType`* 變數會在 404 錯誤頁面顯示時擷取錯誤的 URL，而讓您能夠快速找出在自訂網站上已無效用的中斷連結和路徑。在錯誤頁 *`pageType`* 面上設定變數，如下所示。

請勿在 404 錯誤頁面上使用頁面名稱變數。此&#x200B;*`pageType`* 變數只會用於 404 錯誤頁面。

在大部分的情況下，404 錯誤頁面會是硬式編碼的靜態頁面。在這種情況下，請務必將 .JS 檔案的參考設為適當的全域或相對路徑/目錄。

**語法和可能的值** {#section_C1C59968226446559B05F6EE7374D525}

唯一允許的值 *`pageType`* 是"errorPage"，如下所示。

```js
s.pageType="errorPage"
```

**範例** {#section_6CE22FCB835B4A19B633B7F67E73A115}

```js
s.pageType="errorPage"
```

**組態設定** {#section_3B304A6D3A6C48F2BE90B4DA92A39DDB}

無

**缺陷、問題和提示** {#section_943681AB01FE47BEAC72E93CB60C53C8}

To capture other server-side errors (such as 500 errors), use a prop to capture the error message and put "`500 Error: <URL>`" where `<URL>` is the URL requested, in the *`pageName`* variable. 在執行這些動作後，您即可使用[!UICONTROL 「路徑分析」]報表來檢視是哪些路徑導致使用者產生 500 錯誤。此 prop 會說明哪個錯誤訊息是伺服器所發出的。

## pageURL {#concept_A15F710CD0174297A2286BF3E7452113}

 變數會覆寫頁面的實際 URL。

<!-- 

pageURL.xml

 -->

極少數的情況下，頁面的 URL 不會是您要在 Analytics 中報告的 URL。

<table id="table_D4DC6B476FFD4BEEB36A5C6B2D026255"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大尺寸 </th> 
   <th class="entry"> 偵錯器參數 </th> 
   <th class="entry"> 填充報表 </th> 
   <th class="entry"> 預設值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 不限* </td> 
   <td> <p>G </p> </td> 
   <td> 流量 &gt; 區段 &gt; 最受歡迎頁面的路徑 </td> 
   <td> 頁面 URL </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Although Adobe allows *`pageURL`* values up to 64k, some browsers impose a size limit on the URL of image requests. To prevent truncation of other data, page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter.

**語法和可能的值** {#section_22AF3BF7C2F743549967B0C760A095C0}

The *`pageURL`* variable must be a valid URL, with a valid protocol. 根據 Analytics 設定，網域在填入至報表之前會強制以小寫顯示，且查詢字串可能會被清除。

```js
s.pageURL="proto://domain/path?query_string"
```

僅允許與 URL 相容的字元作為頁面 URL。

>[!NOTE]
>
>強烈建議您先聯絡Adobe顧問或客戶服務，再針對自訂目的使 *`pageURL`* 用變數。

**範例** {#section_45158FDA3F8F4574BDEB5CBC9F7E6C97}

```js
s.pageURL="https://mysite.com/home.jsp?id=1224" 
```

```js
s.pageURL="https://www.mysite.com/"
```

**組態設定** {#section_A8F77DAD88164528ACC5C16C066B47DF}

無

## 外掛程式 {#concept_B570F04FEDA34EB7A9826687FE633953}

此變數在Netscape和Mozilla瀏覽器中會列出瀏覽器上安裝的外掛程式。

<!-- 

plugins.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>This variable should only be read and never set.

您可以讀取這些值，並將其複製到 prop/eVar 中，但絕不可加以變更。此變數是隨 JavaScript 檔案的 H.11 版導入的。

| 查詢參數 | 值 | 範例 | 受影響的報表 |
|---|---|---|---|
| p | 已辨識的外掛程式 | IE Tab Plug-in;QuickTime Plug-in 7.1.6;Mozilla Default Plug-in;iTunes Application Detector;Adobe Acrobat;ActiveTouch General Plugin Container;Shockwave Flash;Microsoft Office 2003;Java(TM) Platform SE 6 U1;Windows Media Player Plug-in Dynamic Link Library;Microsoft® DRM; | 流量 &gt; 技術 &gt; 外掛程式 |

## products {#concept_A4007F6307E4419DAA65E1668A8FEBA2}

The  variable is used for tracking products and product categories as well as purchase quantity and purchase price. 產品通常會與購物車事件或 事件一起設定。

<!-- 

products.xml

 -->

>[!IMPORTANT]
>
>In January of 2016, we updated the logic that sets the *`prodView`* event automatically, which happens when there is a *`product`* but no *`event`*. 此更新可能會導致 *`prodView`事件增加。**`prodViews`* 數目增加的條件僅限於:
>
>1. The events variable contains nothing but an unrecognized event, such as *`shoppingCart`* or *`cart`*, which are not valid events.
   >
   >
1. The *`products`* variable is not empty.
>
>
A possible side effect is that merchandising eVars triggered by *`prodView`* events could be associated with an empty *`product`*, but only if the *`product list`* contains only an invalid product (such as a semicolon with no product listed).

The *`products`* variable tracks how users interact with products on your site. 例如，產品變數可追蹤某項產品被檢視、新增至購物車、結帳和購買的次數。此外也可追蹤您的網站上各個商品銷售類別的相對效力。以下是使用產品變數時的常見情況。

此&#x200B;*`products`*&#x200B;變數一律應與成功事件一起設定。

<table id="table_D5A11AFDDD364D0993D387906343DDF3"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大尺寸 </th> 
   <th class="entry"> 偵錯器參數 </th> 
   <th class="entry"> 填充報表 </th> 
   <th class="entry"> 預設值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>「產 <span class="wintitle"> 品 </span>」字串的大小上限為64k。 </p> </td> 
   <td> 產品 </td> 
   <td> 產品 <p>類別 (選用) </p> <p>收入 (選用) </p> <p>件數 (選用) </p> <p>自訂事件 (選用) </p> <p>eVar (選用) </p> </td> 
   <td> " " </td> 
  </tr> 
 </tbody> 
</table>

**語法** {#section_ABA3682985E540E6AA67A510176CCFFC}

```js
"Category;Product;Quantity;Price;eventN=X[|eventN2=X2];eVarN=merch_category[|eVarN2=merch_category2]"
```

| 欄位 | 定義 |
|---|---|
| 類別 | 包含相關聯產品類別。在第 15 版中，產品可與多個類別相關聯，這會修正第 14 版中存在的限制。如果您先前未記錄產品類別，則鼓勵您開始對第 15 版的報告套件填寫此欄位。 |
| 產品 | (必要) 用以追蹤產品的識別碼。此識別碼可用來填入[!UICONTROL 「產品」]報表。請確實在整個結帳程序中使用相同的識別碼。 |
| 數量 | 購買產品的件數。此欄位必須與[!UICONTROL 購買]事件一起設定，才能記錄下來。 |
| 價格 | 請參考已購買的組合總品質成本 (單位 x 個別單位價格)，而非參考個別價和。此欄位必須與[!UICONTROL 購買]事件一起設定，才能記錄下來。 |
| 事件 | 與指定之事件相關聯的貨幣事件。請參閱[產品特有的貨幣事件](../../../implement/js-implementation/c-variables/page-variables.md#section_F814DF053C0D463A97DA039E6323720C)及[整張訂單貨幣事件](../../../implement/js-implementation/c-variables/page-variables.md#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0)。 |
| eVar | 與指定之產品相關聯的銷售 eVar 值。請參閱 [銷售變數](/help/components/c-variables/c-merch-variables/var-merchandising.md)。 |

包含在以下的值 *`products`*&#x200B;變數中包括的值是根據您正在記錄的事件類型。省略類別時，必須以類別/產品分隔字元 (;) 作為預留位置。僅在需要其他分隔字元，來區分您將包括的參數時，才需要這些分隔字元，如此頁面上的範例所示。

**設定產品與非購買事件** {#section_D5E689D4AAE941EC851CA9B98328A4DE}

The *`products`* variable must be set in conjunction with a success event.

**設定產品與購買事件** {#section_618AAC96E7B541A7AABAA028E5F4E5C3}

The *`purchase`* event should be set on the final confirmation ("Thank You!") 頁面。產品名稱、類別、數量和價格全都會擷取到 *`products`* variable. Although the *`purchaseID`* variable is not required, it is strongly recommended in order to prevent duplicate orders.

**產品特有貨幣事件** {#section_F814DF053C0D463A97DA039E6323720C}

如果貨幣事件接收到變數中的 *`products`* 值而非事件變數，則只套用至該值。 這有助於追磫產品特有折扣、產品出貨，以及類似值。例如，如果您已將事件 1 設為追蹤產品出貨，則具有 "4.50" 運送費用的產品可能會出現，如下所示:

```js
s.events="event1" 
s.products="Footwear;Running Shoes;1;99.99;event1=4.50"
```

在此範例中，值 4.50 直接與 "Running Shoes" 產品相關聯。如果已將 event1 新增至產品報告，則您將看到 "4.50" 針對 "Running Shoes" 細項列出。與 Price 類似，此值應該反映所列出之數量的總金額。如果您有 2 個項目，每個項目的運送費用為 4.50，則 event1 應為 "9.00"。

**整張訂單貨幣事件** {#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0}

如果貨幣事件接收到事件清單中的值而非變數， *`products`* 則會套用至變數中的所有 *`products`* 產品。 這在追蹤整張訂單的折扣、運費及類似的價格時很有用，不必修改產品價格或在產品清單中個別追蹤。

例如，如果您已將 event10 設定為包含整張訂單的折扣，則享有 10% 折扣的購買可能會如下所示: 

```js
s.events="purchase,event10=9.95" 
s.products="Footwear;Running Shoes;1;69.95,Running Essentials;Running Socks;10;29.50" 
s.purchaseID="1234567890"
```

在貨幣事件報表中，報表總計代表已刪除重複資料的事件總計 (在此範例中，是指報告時段的折扣金額總計)，而非每項產品的事件值總和。例如，您將看到 "9.95" 同時針對 "Running Shoes" 和 "Running Socks" 列出，而且總金額也將為 "9.95"。

>[!NOTE]
>
>如果在變數和變數中指定相同數值／貨幣事 *`products`* 件的值， *`events`* 則會使用來自的 *`events`* 值。

**缺陷、問題和提示** {#section_D38FD0B79C0347B9AB4CF1632183DA2E}

* The *`products`* variable should always be set in conjunction with a [!UICONTROL success] event (events). 若未指定[!UICONTROL 成功]事件，預設事件將是 [!UICONTROL prodView]。

* 在填入產品前，請先移除產品和類別名稱中的所有逗號和分號。
* 移除所有的 HTML 字元 (註冊符號、商標等)。
* 移除價格中的貨幣符號 ($)。

**範例** {#section_FCC6EF43D3534ECB9A95CDB05820F564}

<table id="table_6F1334E73CE048A5AC0CC28B561C1B2D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <code> s.products=”Category;ABC123” </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products=”Category2;ABC123,;ABC456” </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products=”Category3;ABC123;1;10” </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products=”Category;ABC123;1;10,;ABC456;2;19.98” </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1” </code> <p> <code> s.products="Category;ABC123;;;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99,;ABC123;2;19.98;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping|evar2=3 Stars" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping, ;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2,event3” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2,event3=9.95” </code> <p> <code> s.products="Category;ABC123;,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## propN {#concept_0F10FA2DE69B4029A31EA5E9313AA254}

屬性 ([!UICONTROL prop]) 變數可用來建置[!UICONTROL 流量模組]內的自訂報表。

<!-- 

propN.xml

 -->

prop 變數可作為計數器 (用以計算頁面檢視的傳送次數)、用於路徑分析報表，或用於關聯報表中。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 100 位元組 | c1 - c75 | 自訂流量 | "" |

**語法和可能的值** {#section_4D3013AF2979426B9589CA2BB9D254CD}

```js
s.propN="value"
```

除了標準變數限制以外，[!UICONTROL 屬性]變數並無其他限制。

**範例** {#section_FFBB916DA9F44B668D5FAB7C511F6182}

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**組態設定** {#section_25FDEB6ECA8242A2A44EE540C083078A}

請向 Adobe 客戶服務洽詢為 [!UICONTROL prop] 變數顯示[!UICONTROL 「瀏覽」]、[!UICONTROL 「訪客」]和[!UICONTROL 「路徑」]等度量的相關事宜。

## purchaseID {#concept_21937434E63F413CB469007623B933AE}

 可用來防止報表中重複計算同一份訂單。

<!-- 

purchaseID.xml

 -->

Whenever the [!UICONTROL purchase] event is used on your site, you should use the *`purchaseID`* variable.

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 20 位元組 | purchaseID | 轉換 &gt; 購買 &gt; 收入轉換 | "" |

當訪客在您的網站上購買商品時，*`purchaseID`* 即會在「感謝您」頁面中與引發[!UICONTROL 購買]事件相同的位置上填入。If the *`purchaseID`* is populated, the products on the "Thank You" page are counted only once per *`purchaseID`*. 這是很重要的，因為網站上會有許多訪客基於本身的用途而儲存「感謝您」或「確認」頁面。此&#x200B;*`purchaseID`* 可防止在每次檢視頁面時都計算一次購買數。

除了避免購買資料被計算兩次外，使用時 *`purchaseID`*，還可防止所有轉換資料在報表中重複計算。

**語法和可能的值** {#section_E352CE2370D54BA69A368E1F63A9C32D}

```js
s.purchaseID="unique_id"
```

The *`purchaseID`* must be 20 characters or fewer, and be standard ASCII.

**範例** {#section_60A5C1EAF42F4611898CD6A4F4CF5A28}

```js
s.purchaseID="11223344" 
s.purchaseID="a8g784hjq1mnp3"
```

**組態設定** {#section_1808631C96674380BF9C4A6D9A2C568E}

無

**缺陷、問題和提示** {#section_F5D010F234ED43F19AD1FCD2CD64E060}

The *`purchaseID`* variable allows all conversion variables on the page to be counted only once in reports.

## referrer {#concept_3D8E6A5D30DC4D92982EFA34D4C7F81B}

變數可用來還原遺失的反向連結資訊。

<!-- 

referrer.xml

 -->

伺服器端和 JavaScript 重新導向通常用於將訪客引導到合適的位置。但是，當瀏覽器被重新導向後，會遺失原始反向連結 URL。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 255 位元組 | R | 流量 &gt; 尋找方法轉換 &gt; 尋找方法 | document.referrer |

許多公司會在其網站間的許多位置使用重新導向。例如，搜尋引擎付費搜尋結果的重新導向可能會帶來訪客。當瀏覽器重新導向後，通常會遺失反向連結。此 變 *`referrer`* 數可用來還原重新導向 *`referrer`* 後第一頁的原始值。 The *`referrer`* may be populated server-side, or via JavaScript from the query string.

反向連結必須屬於「正常格式」，Analytics 才能加以記錄，也就是說，必須遵循標準 URL 格式，具有通訊協定和適當位置。

**語法和可能的值** {#section_A0365D76789C4F4A959E81FE5A9D491D}

```js
s.referrer="URL"
```

此 *`referrer`*. 請確保字串是 URL 編碼的 (無空格)。

**範例** {#section_86FB1577670C4AA18BF3718F0832FCD4}

```js
s.referrer="https://www.google.com/search?q=search+string" 
s.referrer=<%=referrerVar%> // populated server-side  
if(s.getQueryParam('ref') 
s.referrer=s.getQueryParam('ref') 
```

**組態設定** {#section_7AAEF28A7CBC446984F32C0659EFBF8D}

無

**缺陷、問題和提示** {#section_B42BF7FBA1094FF9805707FEA810CFE1}

The *`referrer`* must look like a standard URL and include a protocol.

## 解析度 {#concept_8CBDDBE710744A3AA09E6B1E1519BF30}

The  variable indicates the monitor resolution of the visitor viewing the web page.

<!-- 

resolution.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>This variable should only be read and never set.

您可以讀取這些值，並將其複製到 prop/eVar 中，但絕不可加以變更。此變數是隨 JavaScript 檔案的 H.11 版導入的。

| 查詢參數 | 值 | 範例 | 受影響的報表 |
|---|---|---|---|
| s | WxH | 1680 x 1050 | 流量 &gt; 技術 &gt; 螢幕解析度 |

## s_objectID {#concept_48B50DE6B7E546EBB4D187033F1CAF2B}

The  variable is a global variable that should be set in the [!UICONTROL onClick] event of a link.

<!-- 

s_objectID.xml

 -->

By creating a unique object ID for a link or link location on a page, you can either improve visitor activity tracking or use [!UICONTROL Activity Map] to report on a link type or location, rather than the link URL.

>[!NOTE]
>
>A trailing semicolon (;) is required when using s_objectID with [Activity Map](https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/activitymap-link-tracking-use-case.html).

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 100 位元組 | OID | [!UICONTROL Activity Map], [!UICONTROL ClickMap] | 被點按連結的絕對 URL |

使用 s_objectID 有三個普遍原因。 *`s_objectID`*:

* 彙總一天內經常變更的訪客活動。
* To separate link activity that [!UICONTROL Activity Map] combines.
* To improve the accuracy of [!UICONTROL Activity Map] data reporting.

**彙總高度動態連結的點按數** {#section_BA730A0393B149DDBCAA272C3C23A1C5}

如果您的網站高度動態，且某些頁面上的連結在一天中都會變更， *`s_objectID`* 則可用於識別頁面上的連結位置。 如 *`s_objectID`* 果設為「左上1」或「左上2」（例如，左上2）代表頁面左上方的第一個連結，則會與訪客點按對映一起報告出現在該位置(或設為相同值 *`s_objectID`* )的所有連結。 If you don't use *`s_objectID`*, you see the number of times that a specific link was clicked, but you lose insight into how all the other links in that location were used by visitors to your site.

**區隔合併的點按數** {#section_1AE91FB8A2D3423CBE064ACF02FEEA47}

若您網 *`pageName`**`s_objectID`* 站上的變數用來顯示訪客所檢視的區段或範本，而非訪客所檢視的特定頁面，則您可能會想使用來區隔出現在該頁面範本多個版本上的連結。 例如，若您的網站上有一個適用於所有產品的範本頁面，則所有頁面上都可能會有從該範本連至首頁和搜尋方塊的連結。若您想依個別產品來檢視這些連結的使用情形 (而不依照範本)，您可以為 *`s_objectID`* 填入產品特定值，例如 "prod 123789 home page" 或 "prod 123789 search"。Once completed, [!UICONTROL Activity Map] reports on those links at an individual product basis.

**改善[!UICONTROL Activity map的正確]性**{#section_08B3406821294DCCABEEB99C90CF5C52}

在某些情況下，Internet Explorer、Firefox、Netscape、Opera 與 Safari 以外的瀏覽器都不會列入報表中。儘管所占比例較小，但它確實占去了某些點按和其他度量。Use *`s_objectID`* within links to uniquely identify the addresses the browser reporting issue. The following is an example of how to update your links to use *`s_objectID`*:

```js
<a href="/art.jsp?id=559" onClick="s_objectID='top left 1';">Article 559</a> 
<a href="/home.jsp" onClick="s_objectID='prod 123789 home page';">Home</a> 
```

**語法和可能的值** {#section_85841DF9F06A4680953D9B2A884A1A5A}

s_objectID 可包含任何文字識別碼。

```js
s_objectID="unique_id" 
```

除標準變數限制以外，對於&#x200B;*`s_objectID`*&#x200B;並無其他限制。

**範例** {#section_33F119D532CA4ACAA3426253C42030BB}

```js
s_objectID="top left 2" 
```

```js
s_objectID="prod 123789 search"
```

**組態設定** {#section_95396657D55B41ECB66B83D0534EA827}

無

## server {#concept_BF77952603BA454BAFC9A0A81D06A7D2}

此變數可用來顯示網頁的網域（以顯示訪客進入的網域）或為頁面提供服務的伺服器（以供負載平衡快速參考）。

<!-- 

server.xml

 -->

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 100 位元組 | 伺服器 | 伺服器 | "" |

若您的網站有多個網域提供相同內容，您可以使用&#x200B;*`server`*&#x200B;變數來追蹤訪客使用了其中的哪些網域。下列 JavaScript 會將頁面的網域填入伺服器變數中。

```js
s.server=window.location.hostname
```

若您要使用伺服器變數提供負載平衡的快速指引，您可以在伺服器變數中放入伺服器名稱或號碼。請檢視下列範例: 

```js
s.server="server 14"
```

雖然[!UICONTROL 「最受歡迎伺服器」]報表可作為負載平衡快速參考，但以此方式測量伺服器負載並不精準。例如，「上一頁」按鈕的流量並不會增加伺服器負載，但卻會顯示於報表中。此報表並不會顯示哪些伺服器提供了影像或大量下載內容。

**語法和可能的值** {#section_48E4B9BFEBFF4409A246D86EC0C0FB13}

```js
s.server="server_name"
```

There are no limitations on the *`server`* variable outside of the standard variable limitations.

**範例** {#section_78B9EE3C27FB491384869E3D0BD503D6}

```js
s.server="server 18" 
s.server=window.location.hostname 
```

**組態設定** {#section_969DB379D5BD469FBEE8D505D3000E49}

無

**缺陷、問題和提示** {#section_42A28F9B01574F38891D9D54B411D8FE}

The *`server`* variable can be used to show which domains are most popular or which servers are serving the most pages.

## state {#concept_82295D22888947BF8B1C76182C635C6C}

和變數是轉換變數。

<!-- 

state.xml

 -->

它們與 eVar 的相同之處是都會擷取事件，但不像 eVar 一樣具有永久性。此 *`zip`* and *`state`* variables are like eVars that expire immediately.

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 50 位元組 | state | 轉換 &gt; 訪客資料 &gt; 訪客狀態 | "" |

Because the *`state`* and *`zip`* variables expire immediately, the only events associated with them are events that are fired on the same page on which they are populated. For example, if you are using *`state`* to compare conversion rates by state, you should populate the *`state`* variable on every page of the checkout process. 針對轉換網站，Adobe 建議您以帳單地址作為郵遞區號的來源，但您也可選擇使用交貨地址 (假設該訂單只有一個交貨地址)。媒體網站可選擇使用  *`zip`* and *`state`* for registration or ad click-through tracking.

**語法和可能的值** {#section_EDD1F5F9EDBC457898E61695F08C1744}

```js
s.state="state"
```

The *`state`* variable does not impose any special value or format restrictions. There are no limitations on *`state`* outside of the standard variable limitations.

**範例** {#section_D181B163F79A41D199CA4C70765E583F}

```js
s.state="california" 
```

```js
s.state="prince edward island"
```

**組態設定** {#section_DB0D6DC3F4764AC59C11B10D27D2806C}

無

**缺陷、問題和提示** {#section_02F1620D0BB14AA6A838966FDB9A234F}

* Populate *`state`* on every page that a relevant event is fired (such as each page of the checkout process).
* The *`zip`* and *`state`* variables act like eVars that expire on the Page View.

## timestamp {#concept_D997A2FF4D134C80A614C0BC7A4D7507}

此變數可讓您自訂點擊的時間戳記，如同其他平台的 AppMeasurement 程式庫。

<!-- 

timestamp.xml

 -->

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 4 位元組 | 日期/時間 | 不直接報告。 | 由資料收集伺服器設定。 |

**語法** {#section_1DF752B1202C4412A301AC7CC10874DF}

```js
s.timestamp="UNIX or ISO-8601 format timestamp"
```

The *`timestamp`* variable must be in the format explained in the next section.

>[!IMPORTANT]
>
>Your report suite must be timestamp-enabled by Customer Care before you can use the *`timestamp`* variable. After timestamp support is enabled, all hits sent to this report suite from JavaScript must have a timestamp manually set (using *`s.timestamp`*) or the hits will not be recorded.
>
>此外，如果您啟用報表套裝的時間戳記支援以便支援離線追蹤，從 JavaScript 傳送給此報表套裝的所有點擊也必須以手動設定時間戳記 (使用 *`s.timestamp`*). 您不能同時傳送具有時間戳記和不具有時間戳記的點擊給同一份報表套裝。
>
>您也可以使用[可選時間戳記](../../../implement/js-implementation/timestamps-overview.md#concept_1A7DF6F7BDA34467B51A6F61E08BB73F)設定，以在相同的全域報表套裝中混合時間戳記及非時間戳記資料，從行動應用程式將時間戳記資料傳送至全域報表套裝，也可將應用程式升級，以便在不創建新報表套裝的情形下採用時間戳記。

**時間戳記格式** {#section_C12CBCECCD7047D38EF63A5800761CE9}

時間戳記必須採用 UNIX (自 1970 年 1 月 1 日起的秒數) 或 ISO-8601 格式，且對認可的 ISO-8601 格式具有下列限制: 

* 日期與時間都必須提供，使用 "T" 分隔
* 日期必須是使用完整精確度 (年、月及日) 的日曆日期。。不支援週日期和序數日期。
* 日期可以使用標準或延伸格式 (`YYYY-MM-DD` 或 `YYYYMMDD`)，但是必須包含小時與分鐘。秒數是可選的( `HH:MM`、 `HH:MM:SS`、 `HHMM`或 `HHMMSS`)。 可以傳入分數的分鐘與秒，但是分數部分會忽略。

* An optional time zone can be specified in standard or extended format ( `±HH`, `±HH:MM`, `±HH`, `±HHMM`, or Z)

仍會繼續支援 UNIX 時間戳記 (自 1970 年 1 月 1 日起的秒數)。

**範例** {#section_FA19C53D70DE4CF2AF259A5B968B84C3}

```js
s.timestamp=Math.round((new Date()).getTime()/1000);
```

```js
s.timestamp="2012-04-20T12:49:31-0700";
```

下列清單包含有效 ISO-8601 格式時間戳記的範例: 

```
2013-01-01T12:30:05+06:00 
2013-01-01T12:30:05Z 
2013-01-01T12:30:05 
2013-01-01T12:30
```

**組態設定** {#section_5275D206F2CB4009B3681E8C4457124A}

報表套裝必須能夠接受客戶服務所提供的自訂時間戳記，您才可使用此變數。在啟用自訂時間戳記後，所有傳送至報表套裝的點擊都必須包含時間戳記，否則即會被捨棄。

**缺陷、問題和提示** {#section_EFDE8F67D13C4775A461E0B00D30AFD7}

* 時間戳記主要用來追蹤行動平台上的離線資料。在一般情況下會停用自訂時間戳記，除非您要在相同的報表套裝中同時收集網頁和離線應用程式資料。
* 當行動 SDK 中啟用離線資料(預設設定)，或報表套裝設定為接受已加註時間戳記的資料時，資料就會加註時間戳記。在行動裝置上離線收集的資料可能會在資料發生的數小時或數週後傳送。這些點擊可能佇列在 Analytics 平台中，比無時間戳記的多等幾分鐘或幾小時。

   * 於極接近目前時間傳送的已加註時間戳記資料，可能延遲 10 到 15 分鐘。
   * 於昨天傳送的已加註時間戳記資料，可能延遲 2 小時。
   * 至於比昨天更早傳送的已加註時間戳記資料，每早一天就多 1 小時延遲，最多到 15 天前，延遲就不會再往上增加。

* 啟動時間戳記的作業資料最多可保留 92 日。

## trackingServer {#concept_45EE91B1A99B4A37AFAEF1C0A8A6B02F}

 變數會用於第一方 Cookie 實施，以指定影像要求和 Cookie 寫入所在的網域。

<!-- 

trackingServer.xml

 -->

用於非安全頁面。若&#x200B;*`trackingServer`*&#x200B;已定義，則不會傳送任何資料到 2o7.net。If *`trackingServer`* is not defined (and dc is not defined), data goes to 112.2o7.net.

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | "" |

[此處](https://helpx.adobe.com/analytics/kb/determining-data-center.html)提供 Adobe 資料中心清單。

## trackingServerSecure {#concept_28132A2606E34A2F87BEC9E7ACADC7DD}

 變數會用於第一方 Cookie 實施，以指定影像要求和 Cookie 寫入所在的網域。

<!-- 

trackingServerSecure.xml

 -->

用於安全頁面。若 *`trackingServerSecure`* 未定義，則 SSL 資料會傳送至 *`trackingServer`*.

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | "" |

## transactionID {#concept_FBFA55E137E644A2BD97B41E92F6AFEF}

[!UICONTROL 「整合資料來源」使用交易 ID 將離線資料連接到線上交易 (像是在線上產生的潛在客戶或購買)。]

<!-- 

transactionID.xml

 -->

Each unique *`transactionID`* sent to Adobe is recorded in preparation for a [!UICONTROL Data Sources] upload of offline information about that transaction. 請參閱 [Data Sources](https://marketing.adobe.com/resources/help/en_US/sc/datasources/)。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 100 位元組 | xact | 不適用 | "" |

**啟用交易ID儲存**{#section_3EA2C9DC9D4C4F0FBE4AB67981BCB52E}

Before *`transactionID`* values are recorded, [!UICONTROL Transaction ID Storage] must be enabled for the report suite selected in the Report Suite Manager. 此設定位於

```
Analytics > Admin > Report Suites > Edit Settings > General > General Account Settings.
```

若要查看某個報表套裝是否已啟用  *`transactionID Storage`* 請前往

```
Analytics > Admin > Data Sources > Manage
```

**語法和可能的值** {#section_0C18329203DC45E989DBAE70C0FB4801}

```js
s.transactionID="unique_id"
```

The *`transactionID`* should contain only alphanumeric characters. 若有多個 [!UICONTROL transactionID] 變數應記錄在單一點擊中，您可以使用逗號來分隔多個值。

**範例** {#section_A4C1F0E54CB54AD7B86A22147E9B5FEF}

```js
s.transactionID="11123456"
```

```js
s.transactionID="lead_12345xyz"
```

```js
s.transactionID=s.purchaseID
```

**缺陷、問題和提示** {#section_4299BAD5D0154DBC88A9EF0E2C252BB4}

* If  recording is not enabled,  values will be discarded and unavailable for use with Integration Data Sources. *`transactionID`**`transactionID`*Make sure to set a conversion variable or event (an eVar or the events variable) on the page where *`transactionID`* is set. Otherwise, no data is recorded for the *`transactionID`*.

* If you are recording transactionIDs for multiple systems, such as purchases and leads, make sure the value in  is always unique. *`transactionID`*&#x200B;要確保這一點，您可以為 ID 加上前置詞，如 lead_1234 與 purchase_1234。[!UICONTROL 整合資料來源] (如果有兩次看見獨特資料， [!UICONTROL 資料來源資料將會系結至錯誤資料)]*`transactionID`* 的運作不如預期。

* 依預設， *`transactionID`* 值會記住90天。 如果您的離線互動程序超過 90 天，請聯絡客戶服務以要求延長期限。

>[!NOTE]
>
>The *`transactionID`* variable can contain any character other than a comma. 其所在位置應與字元限制 (100 位元組) 的指定位置相同。若使用了多位元組字元，則必須啟用多位元組字元支援，以避免 *另存`transactionID`。*

## visitorID {#concept_CD273CC915CC4ABD8F52E4209FF9557E}

訪客可由 變數來識別，或由 IP 位址/使用者代理識別。

<!-- 

visitorID.xml

 -->

The *`visitorID`* can be up to 100 alpha-numeric characters and must not contain a hyphen.

如果您明確設定自訂 ID，則會優先於其他 ID 方法而使用此自訂 ID。

使用順序如下: s.visitorID &gt; s_vi &gt; s_fid &gt; IP/UA.

| ** 最大尺寸** | ** 偵錯器參數** | ** 填充報表** | ** 預設值** |
|---|---|---|---|
| 100 位元組 | vid | 不適用 | "" |

**語法和可能的值** {#section_5F768C7AE6824557997E92B295C09280}

```js
s.visitorID="visitor_id"
```

>[!NOTE]
>
>The *`visitorID`* variable should not contain a hyphen.

**範例** {#section_F7F07FEFAC3644A5A084D166ACE1315E}

```js
s.visitorID="abc123"
```

**組態設定** {#section_582B376FE55C4BCA8F978E0F62B5DB54}

無

## visitorNamespace {#concept_8369DDB3830C4BF2905F1CFC8C8B0D92}

 變數可用來識別 Cookie 設定所在的網域。

<!-- 

visitorNamespace.xml

 -->

If *`visitorNamespace`* is used in your JavaScript file, do not delete or alter it. If *`visitorNamespace`* changes, all visitors reported in Analytics may become new visitors. 訪客的歷史記錄會與目前和後續的流量失去連結。未經 Adobe 代表許可，請勿更改此變數。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | ns | 不適用 | "" |

Analytics 會使用 Cookie 對進入您的網站的訪客進行唯一識別。If *`visitorNamespace`* is not used, the cookie is associated 2o7.net. If *`visitorNamespace`* is used, the cookie is associated with a sub-domain of 2o7.net. 瀏覽您網站的所有訪客均應有各自關聯至相同網域或子網域的 Cookie。

之所以使用 *`visitorNamespace`* 變數，是為了避免發生超出瀏覽器 Cookie 限制的狀況。Internet Explorer 會有每個網域 20 個 Cookie 的限制。藉由使用 *`visitorNamespace`* 變數，其他公司的 Analytics Cookie 就不會與您的訪客的 Cookie 發生衝突。

**語法和可能的值** {#section_EE247FE371784CA4B6058182181F3EA1}

The value of *`visitorNamespace`* must be provided by Adobe and is a string of ASCII characters that don't contain commas, periods, spaces, or special characters.

```js
s.visitorNamespace="company_specific_value"
```

**跨報表套裝的訪客識別** {#section_7AC5A97FC8C045DD8850245A62BB09F4}

If you do not specify a `visitorNamespace`, each report suite in your company receives its own visitor ID cookie written as `s_vi_[random string]`. 如果有指定 `visitorNamespace`，將對所有傳送資料至所指定之 `s_vi` 的報表套裝，使用相同的 `trackingServer` Cookie。如果有實施多套裝標記，請務必指定訪客命名空間，好讓每個報表套裝使用相同的 Cookie。

**範例** {#section_89A95852AB9446E794AD3283B8800B09}

```js
s.visitorNamespace="company_name"
```

```js
s.visitorNamespace="Adobe"
```

**組態設定** {#section_1128A2531ECC43DFA6749ECC21F050A2}

無

## zip {#concept_C1DF93083553410DA36EAB61FBFDF69A}

The  and  variables are conversion variables.

<!-- 

zip.xml

 -->

它們與 eVar 的相同之處是都會擷取事件，但不像 eVar 一樣具有永久性。此 *`zip`* and *`state`* variables are like eVars that expire immediately.

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 50 位元組 | zip | 轉換 &gt; 訪客資料 &gt; 郵遞區號 | "" |

由於  *`state`* and *`zip`* variables expire immediately, the only events associated with them are events fired on the same page that are populated. For example, if you are using *`zip`* to compare conversion rates by Zip Code, you should populate *`zip`* on every page of the checkout process. Adobe 建議您以帳單地址作為郵遞區號的來源。您也可選擇使用交貨地址 (假設該訂單只有一個交貨地址)。媒體網站可選擇使用  *`zip`* and *`state`* for registration or ad click-through tracking.

**語法和可能的值** {#section_5EDCFCAC8FC241D1B4CC777996858CD7}

```js
s.zip="zip_code"
```

The *`zip`* variable does not impose any value or format restrictions. There are no limitations on *`zip`* outside of the standard variable limitations.

**範例** {#section_F25C0D0CC3C04B81892A662CD605C593}

```js
s.zip="92806"
```

```js
s.zip="92806-4115"
```

**組態設定** {#section_7987084EECC34DD38B643B94F82385CA}

無

**缺陷、問題和提示** {#section_E86774D5CE8B40EFA36353CDEE3A84D0}

* 請將[!UICONTROL 郵遞區號]填入至有相關事件引發的每個頁面上 (如結帳程序的每個頁面)。
* The *`zip`* and *`state`* variables act like eVars that expire on the Page View.

