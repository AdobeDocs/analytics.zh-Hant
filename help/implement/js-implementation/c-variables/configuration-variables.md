---
description: AppMeasurement. js中設定的組態變數。
keywords: Analytics 實施
seo-description: Adobe Analytics的AppMeasurement. js中設定的組態變數
seo-title: 組態變數
solution: Analytics
subtopic: 變數
title: 組態變數
topic: 開發人員和實施
uuid: a19484b6-e35-4c12-b4 d6-a31 c79 a42 db0
translation-type: tm+mt
source-git-commit: 72f2b06f53c6a3c1cae965a1a9b030b0123bfca1

---


# 組態變數

設定變數會控制資料在報表中擷取及處理的方式。通常在主要全域JavaScript AppMeasurement. js中設定的最常用組態變數。這些變數可在Analytics頁面層級代碼和連結中設定，並視情況而定。

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. 其中有些設定變數可能不符合您的網站實施需求。

使用這些設定變數的部分目標為:

* 追蹤多個網站或網域。
* 在購買中使用任何貨幣。
* 擷取不同語言中的資料。
* 連結追蹤 (下載檔案數、外部網站連結。
* 因特殊目的追蹤自訂連結。

>[!NOTE]
>
>[!DNL AppMeasurement] 要求在初始呼叫追蹤函數之前設定所有組態變數 `t()`。If configuration variables are set after the call to `t()`, unexpected results may occur. To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

## s.account {#concept_685A5C832A6C40619ACB5920925785DC}

<!--
s_account.xml
-->

 變數會判斷資料儲存及報告所在的報表套裝。

If sending to multiple report suites (multi-suite tagging), `s.account` may be a comma-separated list of values. 報表套裝 ID 由 Adobe 決定。

**參數**

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|--- |--- |--- |--- |
| 40 位元組 | 在 URL 路徑中 | 不適用 | 不適用 |

Each report suite ID must match the value created in the [!DNL Admin Console]. 每個報表套裝 ID 的位元組數不可超過 40，但所有報表套裝的彙總值 (整份逗號分隔清單) 則無限制。

報告套裝是報告中最基本的區段層級。您可以在合同允許的情況下設定任意數量的報告套裝。每個報告套裝代表一組已在 Adobe 收集伺服器中填入的專用表格。報告套裝可透過 JavaScript 程式碼中的`s_account` 變數來識別。

在 [!DNL Analytics] 中，位於報表左上方的網站下拉式方塊會顯示目前的報表套裝。每個報表套裝都有一個唯一識別碼，名為報表套裝 ID。此`s_account`變數包含資料所要傳送到的一或多個報表套裝 ID。報表套裝 ID 值不會對 [!DNL Analytics] 使用者顯示，且必須由 Adobe 提供或核准，您才可使用。Every report suite ID has an associated "friendly name" that can be changed in the report suites section of the [!DNL Admin Console].

`s_account` 變數通常會在JavaScript檔案(s_ code. js)內宣告。You can declare the `s_account` variable on the HTML page, which is a common practice when the value of `s_account` may change from page to page. `s_account` 因為變數具有全域範圍，因此應在包含Adobe的JavaScript檔案前立即宣告。If `s_account` does not have a value when the JavaScript file is loaded, no data is sent to [!DNL Analytics].

Adobe's [!DNL DigitalPulse Debugger] displays the value of `s_account` in the path of the URL that appears just below the word "Image," just after /b/ss/. In some cases, the value of `s_account` also appears in the domain, before 112.2o7.net. 路徑中的值是決定目標報表套裝的唯一值。下方的粗體文字顯示資料所傳送到的報表套裝，如同除錯程式中所顯示。請參閱 [DigitalPulse 除錯程式](../../../implement/impl-testing/debugger.md#concept_B26FFE005EDD4E0FACB3117AE3E95AA2).

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

**語法和可能的值** {#section_3BE913DF26D848AEB4CB5B0A6CE7F0CA}

報表套裝 ID 是 ASCII 字元的英數字串，長度不得超過 40 位元組。唯一可用的非英數字元是連字號。空格、句號、逗號與其他標點符號皆不准使用。此`s_account`變數可包含多個報表套裝，所有報表套裝都會從頁面接收資料。

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

All values of `s_account` must be provided or approved by Adobe.

**範例** {#section_16580A9101B64560A58C7745397FB42F}

```js
var s_account="mycompanycom"
```

```js
var s_account="mycompanycom,mycompanysection"
```

**在 Analytics** 中設定變數 {#section_7DFB2CCF02F045AFB1AD4F376638393B}

與各報表套裝 ID 相關聯的好記名稱，可由 Adobe [!DNL Customer Care] 進行變更。好記名稱可在 [!DNL Analytics] 中位於畫面左上方的網站下拉式方塊中檢視。

**缺陷、問題和提示** {#section_BFFDA5C0AF31442494B0E02F0925CF93}

* If `s_account` is empty, not declared, or contains an unexpected value, no data is collected.
* `s_account` 當變數是逗號分隔清單(多套裝標記)時，請勿在報表套裝ID之間放入空格。
* If [!UICONTROL s.dynamicAccountSelection] is set to *True* the URL is used to determine the destination report suite. Use the [!DNL DigitalPulse Debugger] to determine the destination report suite(s).

* 某些情況下可使用 [!DNL VISTA] 來更改目標報表套裝。使用第一方 Cookie 時，或您的網站擁有超過 20 個作用中報表套裝時，建議使用 [!DNL VISTA] 將資料重新路由或複製到其他報表套裝。

* Always declare `s_account` inside the JS file or just before it is included.

## s.dynamicAccountSelection {#concept_FAD499DB357148DB8BD74F08093D3E35}

 變數可讓您根據各頁面的 URL 動態選取報表套裝。

>[!NOTE]
>
>`dynamicAccountSelection` 無法與自訂連結追蹤搭配使用。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | False |

>[!NOTE]
>
>Both `dynamicAccountList` and `dynamicAccountMatch` are ignored if the `dynamicAccountSelection` variable is not declared or set to 'false.'

**語法和可能的值** {#section_36E5D0E2170345F5A652B44CE85DFED1}

```js
s.dynamicAccountSelection=[true|false]
```

Only 'true' and 'false' are allowed as values of *`dynamicAccountSelection`*.

**範例** {#section_E8CE8BA62C7545889531495E2521663D}

```js
s.dynamicAccountSelection=true
```

```js
s.dynamicAccountSelection=false
```

**組態設定** {#section_F052FA38144B4F84B015A263A8E711CF}

無

**缺陷、問題和提示** {#section_62F0B0895BC84A05840AEEED0643DE60}

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8).
* Always use the [!DNL DigitalPulse Debugger] to determine which report suite is receiving data from each page.

## s.dynamicAccountList {#concept_19715BA0AD4D41748E0C4A4A6B71AB51}

<!-- 
dynamicAccountList.xml
-->

[!DNL AppMeasurement]JavaScript 適用的 可動態選取其資料所要傳送到的報表套裝。 變數包含用來決定目標報表套裝的規則。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | "" |

此變數在使用時會搭配 *`dynamicAccountSelection`* 和 *`dynamicAccountMatch`* 變數。The rules in *`dynamicAccountList`* are applied if *`dynamicAccountSelection`* is set to 'true,' and they apply to the section of the URL specified in *`dynamicAccountMatch`*.

If none of the rules in *`dynamicAccountList`* matches the URL of the page, the report suite identified in `s_account` is used. 此變數中所列的規則會以由左至右的順序套用。若頁面 URL 符合多個規則，則會使用最左側的規則來決定報表套裝。因此，您應將較通用的規則移至清單的右側。

In the following examples, the page URL is `www.mycompany.com/path1/?prod_id=12345` and `dynamicAccountSelection` is set to *true* and `s_account` is set to `mysuitecom.`

| DynamicAccountList 值 | DynamicAccountMatch 值 | 要接收資料的報表套裝 |
|---|---|---|
| `mysuite2=www2.mycompany.com;mysuite1=mycompany.com` | window.location.host | mysuite1 |
| "mysuite1=path4,path1;mysuite2=path2" | window.location.pathname | mysuite1、mysuite2 |
| "mysuite1=path5" | window.location.pathname | mysuitecom、mysuite1 |
| "myprodsuite=prod_id" | window.location.search?window.location.search:"?") | myprodsuite |

**語法和可能的值** {#section_7360E4354ED345E8BAAE210DBD58A7EC}

`dynamicAccountList` 變數是以分號分隔的名稱=值配對(規則)清單。清單中的每一項均應包含下項目: 

* 一或多個報表套裝 ID (以逗號分隔)
* 一個等號
* 一或多個 URL 篩選器 (以逗號分隔)

```js
s.dynamicAccountList=rs1[,rs2]=domain1.com[,domain2.com/path][;...]
```

字串中只應使用標準 ASCII 字元 (無空格)。

**範例** {#section_49936D14EF6D45859B666C9E7A4CBA9E}

```js
s.dynamicAccountList="mysuite2=www2.mycompany.com;mysuite1=mycompany.com"
```

```js
s.dynamicAccountList="ms1,ms2=site1.com;ms1,ms3=site3.com"
```

**組態設定** {#section_9F99CD741BC7449B8CCC108094B2EB85}

無

**缺陷、問題和提示** {#section_3E10534FCC05457AB67147BB480C8BB3}

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8).
* 若頁面 URL 符合多項規則，將會使用最左側的規則。
* 若沒有相符的規則，則會使用預設報表套裝。
* 若您的頁面儲存至某人的硬碟，或透過網頁型翻譯引擎進行翻譯 (例如 Google 的翻譯頁面)，可能將無法使用動態帳戶選項。如需更精確的追蹤，請在伺服器端填入 `s_account` 變數。
* `dynamicAccountSelection` 規則僅適用於指定之URL的區段 `dynamicAccountMatch`。

* When using dynamic account selection, be sure to update *`dynamicAccountList`* every time you obtain a new domain.
* Use the [!DNL DigitalPulse Debugger] when trying to identify the destination report suite. `dynamicAccountSelection` 變數一律會覆寫 `s_account`值。

## s.dynamicAccountMatch {#concept_718171E602214CCC9905C749708BBE52}

<!-- 
dynamicAccountMatch.xml
-->

 變數會使用 DOM 物件來擷取套用了 中所有規則的 URL 區段。

This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' 由於預設值為 [!DNL window.location.host]，因此這個變數並非[!UICONTROL 動態帳戶選項]運作所需的必要項目。For additional information, see [dynamicAccountList](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_19715BA0AD4D41748E0C4A4A6B71AB51).

The rules found in `dynamicAccountList` are applied to the value of `dynamicAccountMatch`. If `dynamicAccountMatch` only contains [!DNL window.location.host] (default), the rules in `dynamicAccountList` apply only to the domain of the page.

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | window.location.host |

**語法和可能的值** {#section_95CD81972C22419B80A921CA137D3841}

`dynamicAccountMatch` 變數通常由提供JavaScript適用AppMeasurement檔案的Adobe顧問填入。但下方所列的值隨時都可套用。

```js
s.dynamicAccountMatch=[DOM object]
```

| 說明 | 值 |
|---|---|
| 網域 (預設值) | window.location.host |
| 路徑 | window.location.pathname |
| 查詢字串 | (window.location.search?window.location.search:"?") |
| 網域和路徑 | window.location.host+window.location.pathname |
| 路徑和查詢字串 | window.location.pathname+(window.location.search?window.location.search:"?") |
| 完整 URL | window.location.href |

**範例** {#section_924687CCE255421AA2223A3D4B8B6A30}

```js
s.dynamicAccountMatch=window.location.pathname
```

```js
s.dynamicAccountMatch=window.location.host+window.location.pathname
```

**組態設定** {#**section_43BCE13B1ADD4D418DF7CBB9DD7A6472}

無

**缺陷、問題和提示** {#section_EF9B2977BC21497D8C5EEB9BAD731E17}

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8).
* When pages are saved to a hard drive, [!DNL window.location.host] is empty, causing those page views to be sent to the default report suite (in `s_account`).

* 在透過網頁型翻譯引擎 (例如 Google) 翻譯頁面時，[!UICONTROL 「動態帳戶選項」]無法如預期運作。如需更精確的追蹤，請在伺服器端填入 [!UICONTROL s_account] 變數。

## s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

<!-- 
dynamicVariablePrefix.xml
-->

 變數可讓您在部署中為動態填入的變數加上標記。

Cookie、要求標題和影像查詢字串參數皆可動態填入。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | D= | 任何 | D= |

**語法和可能的值** {#section_D0669899567F46B6A081C7661362BA81}

```js
s.prop1="D=User-Agent”
```

或對動態變數使用自訂標幟

```js
s.dynamicVariablePrefix=".."
```

**範例** {#section_DD148560F9E8416EBCF159194FA427AC}

```js
s.prop1="D=User-Agent”
```

或對動態變數使用自訂標幟

```js
s.dynamicVariablePrefix=".."
```

```js
s.prop1="..User-Agent"
```

**缺陷、問題和提示** {#section_6889908FBD78488D955F67DDB17617B1}

* 動態變數可藉由將值複製到其他變數中，而大幅降低 URL 的總長度。
* 動態變數可讓您從無法以其他方式用於資料收集的標題和 Cookie 進行資料收集。

## s.charSet {#concept_E65B9A8F75C3482C87D0D455805F89BD}

<!-- 
charset.xml
-->

charSet屬性通常會在JavaScript檔案中設定，可供Analytics用來將傳入的資料轉換為UTF-8，以便依Analytics進行儲存和報告。

>[!Nte：] 傳送資料至多位元組報表套裝時需要使用charSet屬性，且不應與標準報表套裝搭配使用。使用標準 ISO 報表套裝設定 charSet 屬性可導致變數截斷或意外的字元轉換。

charSet 屬性的值應與 META 標記或 http 標題中的頁面編碼相符，即使語法稍有不同。儘管 META 標記使用別名進行編碼，charSet 的值也應使用慣用 (或官方) 名稱。

下表列出了一些更常見編碼的慣用名稱和別名。

| 慣用名稱 | 別名 |
|--- |--- |
| ISO-8859-1 | ISO_8859-1,CP819,latin1 |
| ISO-8859-2 | ISO_8859-2,latin2 |
| ISO-8859-5 | ISO_8859-5,cyrillic |
| Big5 | Big-5 |
| Shift_JIS | SJIS |

由於存在許多編碼和別名，請連絡實施顧問或Adobe客戶服務，以確認charSet的正確值(如果未出現在上表中)。

If a site has different web encodings on different pages, or a single JavaScript file is used for multiple sites, the charSet property can be set to a default value in the JavaScript file and then reset on specific pages as needed to override the default; for example, `s.charSet="UTF-8"` or `s.charSet="SJIS"`.

任何 charSet 參數的非空白值均可導致資料轉換為 UTF-8 儲存。所有 128-255 範圍的字元均將轉換為合適的 UTF-8 雙位元組序列並儲存。這些字元將無法在標準報表套裝中正確顯示。因此，嚴禁在標準報表套裝中使用 charSet 屬性。

同樣，charSet 參數的空白值可跳過資料轉換過程，所有 128-255 範圍中的字元均會以單位元組的形式儲存。由於這些字元的單位元組代碼均是無效的 UTF-8，這些字元將無法在多位元組報表套裝中正確顯示。因此，應始終在多位元組報表套裝中使用 charSet 參數。此外，正確值應與網頁編碼相關。

*`charSet`* 如果變數包含不正確的值，則所有其他變數中的資料將不正確地翻譯。If JavaScript variables on your pages (e.g. *`pageName`*, [!UICONTROL prop1], or *`channel`*) contain only ASCII characters, *`charSet`* does not need to be defined. However, if the variables on your pages contain non-ASCII characters, the *`charSet`* variable must be populated.

**參數**

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|--- |--- |--- |--- |
| 不適用 | CE | 不適用 | "" |

**語法和可能的值** {#section_EBC2176067A04D9E814CF78A86DC80FA}

```js
s.charSet="character_set"
```

**範例** {#section_406DE0A2B58441DB8512F5B3BE5D9CB5}

```js
s.charSet="ISO-8859-1"
```

```js
s.charSet="SJIS"
```

## s.currencyCode {#concept_CE216F1610E2499D8178DB9A8EB97C63}

<!-- 
currencycode.xml
-->

 變數會決定要對收入套用的轉換率。

所有金額都會以您所選擇的貨幣儲存。若該貨幣與 *`currencyCode`*&#x200B;或 *`currencyCode`* 空白，則不會套用任何轉換。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|--- |--- |--- |--- |
| 不適用 | cc | 轉換 &gt; 購買 &gt; 收入 所有顯示收入或金額值的轉換報表 | "USD" |

若您的網站可讓訪客以多種貨幣購買商品，您應使用 *`currencyCode`* 變數確定收入會以適當的貨幣儲存。For example, if the base currency for your report suite is USD, and you sell an item for 40 Euros, you should populate the *`currencyCode`* with "EUR" on the HTML page. 資料收集在接收到資料後，會使用目前的轉換率將 40 歐元轉換為等值的美元。

若您以多種貨幣販售商品，則應在 HTML 頁面上填入 *`currencyCode`* 變數，而不是在 JavaScript 檔案中。If you want to use your own conversion rates rather than the conversion rates used by Adobe, set the *`currencyCode`* to equal the base currency of your report suite. 接著，您應先轉換所有的收入，再將其傳送至 [!DNL Analytics] 中。

對於收入和任何貨幣事件都會套用貨幣轉換。這些事件是用來加總類似於收入的值 (例如稅金和運費) 的事件。收入和貨幣事件指定於產品字串中。如需產品的詳細資訊，請參閱 [events](../../../implement/js-implementation/c-variables/page-variables.md#concept_FFD115543D54401B98FE683BD7D5B3FE). 如需如何管理貨幣的詳細資訊，請參閱[多貨幣支援](https://marketing.adobe.com/resources/help/en_US/whitepapers/currency/)。

**語法和可能的值** {#section_7CD68F08AB4848EE9B0D19DCC3F1BECE}

```js
s.currencyCode="currency_code"
```

僅允許使用[多貨幣支援](https://marketing.adobe.com/resources/help/en_US/whitepapers/currency/)中列出的貨幣代碼。

**範例** {#section_D55ED45369544C8AAA02B3193752636C}

```js
s.currencyCode="GBP"
```

```js
s.currencyCode="EUR"
```

**組態設定** {#section_D05E29F545A04958B1C0A82248BCA1B0}

Adobe [!DNL Customer Care] 可變更報表套裝的預設貨幣設定。當您變更報表套裝的基本貨幣時，系統中的現有收入並不會轉換。新收入值則全都會據以轉換。

**缺陷、問題和提示** {#section_08A80A87B54A4861905953A6FA61FF8F}

* If you notice surprisingly large amounts of revenue in reports, ensure that the *`currencyCode`* variable and base currency of the report suite are set correctly.
* *`currencyCode`* 變數不是永久性的，這表示變數必須傳入與收入或其他貨幣相關度量相同的影像要求中。
* 貨幣事件不應用在非貨幣用途上。若您需要計算非貨幣的任意值或動態值，請使用[!UICONTROL 數值]事件類型。
* 當 *`currencyCode`* 變數空白，則不會套用轉換。

## s.cookieDomain {#concept_6164C39CF8BE4737A7EF1DE5A8376C1B}

<!-- 
cookiedomain.xml
-->

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set.

Commonly, `s.cookieDomainPeriods` is used to generate `s.cookieDomain` from `window.location.hostnam`e. Instead of using `s.cookieDomainPeriods`, you can explicitly set `s.cookieDomain` to what you want to use in your implementation. 舉例來說，您可以使用下列語法，以完全合格的頁面名稱來設定 Cookie:

`s.cookieDomain = window.location.hostname;`

## s.cookieDomainPeriods {#concept_F17A59C7D8F54F5897AD40980B6725EB}

<!-- 
cookiedomainperiods.xml
-->

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set by determining the number of periods in the domain of the page URL. 有些外掛程式也會使用此變數來決定用以設定外掛程式 Cookie 的正確網域。

The default value for *`cookieDomainPeriods`* is "2". This is the value that is used if *`cookieDomainPeriods`* is omitted. For example, using the domain `www.mysite.com`, *`cookieDomainPeriods`* should be "2". For `www.mysite.co.jp`, *`cookieDomainPeriods`* should be "3".

If *`cookieDomainPeriods`* is set to "2" but the domain contains three periods, the JavaScript file attempts to set cookies on the domain suffix.

For example, if setting *`cookieDomainPeriods`* to "2" on the domain `www.mysite.co.jp`, the `s_cc` and `s_sq` cookies are created on the domain `co.jp`. 由於 `co.jp` 是無效網域，幾乎所有瀏覽器都會拒絕這些 Cookie。因此，訪客點按對映資料將會遺失，且「[!UICONTROL 訪客資料] &gt; [!UICONTROL 技術] &gt; [!UICONTROL Cookie]」報表會指出幾乎所有的訪客都拒絕 Cookie。

若&#x200B;*`cookieDomainPeriods`* 設為 "3"，但網域僅包含兩個句號，則 JavaScript 檔案會在網站的子網域上設定 Cookie。For example, if setting *`cookieDomainPeriods`* to "3" on the domain `www2.mysite.com`, the `s_cc` and `s_sq` cookies are created on the domain `www2.mysite.com`. When a visitor goes to another subdomain of your site (such as `www4.mysite.com`), all cookies set with `www2.mysite.com` cannot be read.

>[!NOTE]
>
>Do not include additional subdomains as part of *`cookieDomainPeriods`*. For example, `store.toys.mysite.com` would still have *`cookieDomainPeriods`* set to "2". 此變數定義會在根網域 [!DNL mysite.com] 上正確設定 Cookie。Setting *`cookieDomainPeriods`* to "3" in this example would set cookies on the domain [!DNL toys.mysite.com], which has the same implications as the prior example.

See also [s.fpCookieDomainPeriods](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_0A25BD152B0744989E7C662A95448274).

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | CDP | 可控制訪客 ID 的儲存與處理方式，而影響多份報表。 | "2" |

>[!NOTE]
>
>有些雲端運算服務被視為頂層網域，不允許編寫Cookie。(For example, `compute.amazonaws.com`, `*.herokuapp.com`, `*.googlecode.com`, and so on.) 如果您在這些服務上實施，且沒有設定自己的網域 (例如您正在測試自己的實施)，可能會受到 Analytics 隱私權設定影響，已封鎖所有 Cookie 的使用者會遭到移除。若發生這種情況，經系統判斷 Cookie 已停用、無作用或無法存取的所有點擊都會遭退出，因此排除在報表之外。

**範例** {#section_4218BE29FA5E49F58975A2094329B268}

手動設定變數: 

```js
s.cookieDomainPeriods = "3";
```

數個動態設定變數的範例 (若您的核心 JavaScript 檔案同時包含兩種類型):

```js
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```

```js
s.cookieDomainPeriods = "2"; 
var d=window.location.hostname; 
if(d.indexOf(".co.uk") > 0 || d.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

```js
s.cookieDomainPeriods = "2"; 
if(window.location.indexOf(".co.jp") > 0 || window.location.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

**缺陷、問題和提示** {#section_F3BE3F039E5C4359B694DBB61369822C}

* If you notice that visitor click map data is absent, or that the [!UICONTROL Traffic] &gt; [!UICONTROL Technology] &gt; [!UICONTROL Cookies] report shows a large percentage of visitors who reject cookies, check that the value of *`cookieDomainPeriods`* is correct.

* If *`cookieDomainPeriods`* is higher than the number of sections in the domain, cookies will be set with the full domain. 這可能會導致訪客在不同子網域之間切換時遺失資料。
* 此   *`cookieDomainPeriods`* 變數用於設定訪客ID *`trackingServer`* Cookie之前已過時的實施中。Though only present in outdated code, failure to correctly define *`cookieDomainPeriods`* in this circumstance puts your implementation at risk of data loss.

## s.fpCookieDomainPeriods {#concept_0A25BD152B0744989E7C662A95448274}

<!-- 
fpCookieDomainPeriods.xml
-->

 變數會用於由 JavaScript (s_sq、s_cc、外掛程式) 設定、原本即為第一方 Cookie 的 Cookie，即使您的實施使用第三方 2o7.net 或 omtrdc.net 網域亦然。

*`fpCookieDomainPeriods`* 不應動態設定變數。If you use *`cookieDomainPeriods`*, it is good practice to specify a value for *`fpCookieDomainPeriods`* as well. *`fpCookieDomainPeriods`* 繼承 *`cookieDomainPeriods`* 值。Note that *`fpCookieDomainPeriods`* does not affect the domain on which the visitor ID cookie is set, even if your implementation treats this as a first-party cookie.

The name " *`fpCookieDomainPeriods`*" refers to the number of periods (".") "www" 開頭時位於網域中的句號 (.) 數。For example, `www.mysite.com` contains two periods, while `www.mysite.co.jp` contains three periods. Another way to describe the variable is the number of sections in the main domain of the site (two for `mysite.com` and three for `mysite.co.jp`).

[!DNL AppMeasurement] JavaScript檔案使用 *`fpCookieDomainPeriods`* 變數來判斷要設定第一方Cookie以外的網域，而非 [!UICONTROL 訪客ID] (s_ vi) Cookie。至少有兩個 Cookie 會受此變數影響，包括 s_sq 與 s_cc (分別用於訪客點按對映和 Cookie 檢查)。此外，[!UICONTROL getValOnce] 之類的外掛程式所使用的 Cookie 也會受影響。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | cookieDomainPeriods |

**用以設定 Cookie 網域變數的範例程式碼** {#section_5200A92D40384C82998606E800B69E13}

```js
s.fpCookieDomainPeriods="2" 
var d=window.location.hostname 
if(d.indexOf('.co.uk')>-1||d.indexOf('.com.au')>-1) 
  s.fpCookieDomainPeriods="3" 
```

**語法和可能的值** {#section_87923F4C12E74AF99CC9AFC0FFD77D49}

*`cookieDomainPeriods`* 變數應為字串，如下所示。

```js
s.fpCookieDomainPeriods="3"
```

**範例** {#section_EF7355718AD849BF963EE9F6F9F79891}

```js
s.fpCookieDomainPeriods="3"
```

```js
s.fpCookieDomainPeriods="2"
```

**組態設定** {#section_DB65D9BC4F3048C8AD08F9A7CD8FCFC0}

無

## s.cookieLifetime {#concept_8347C6648B0E4D4996E2F223C34B9A3D}

<!-- 
cookielifetime.xml
-->

JavaScript 和資料收集伺服器都會使用 變數來決定 Cookie 的有效期限。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | cl | 流量 &gt; 技術 &gt; Cookie (所有訪客相關) 報表 | "" |

若設定了 *`cookieLifetime`*，此變數將會覆寫 JavaScript 和資料收集伺服器的任何其他 Cookie 有效期，但有一個例外，以下會有說明。*`cookieLifetime`* 變數可以有下列三個值之一：

* [!DNL Analytics] Cookie
* Cookie
* JavaScript 設定和外掛程式

**語法和可能的值** {#section_09D4D122451B45FAB2C9398600EC66F1}

```js
s.cookieLifetime="value"
```

可能的值列出如下: 

* ""
* "NONE"
* "SESSION"
* 表示過期前秒數的整數

**範例** {#section_91499F70C8B14D3292FCF1B60F04E30A}

```js
s.cookieLifetime="SESSION"
```

```js
s.cookieLifetime="86400" // one day in seconds
```

**組態設定** {#section_7BDAD4CFE8414C9BA5717A8C8B1BDD34}

無

**缺陷、問題和提示** {#section_23E24877F6554E0D9F8C8B7A9C2994B2}

*`cookieLifetime`* 影響 [!DNL Analytics] 追蹤。If, for example, *`cookieLifetime`* is two days, then monthly, quarterly, and yearly unique visitor reports will be incorrect. Use caution when setting *`cookieLifetime`*.

## s.doPlugins {#concept_676EAE4FAFCF4B018876390FC874EFDA}

<!-- 
doPlugins.xml
-->

 變數是 函數的參考，可讓 函數在 JavaScript 檔案內的適當位置被呼叫。

The *`s_doPlugins`* function is called each time any of the following occurs:

* The *`t()`* function is called
* The *`tl()`* function is called
* 點按退出或下載連結
* 點按訪客點按對映所追蹤的任何頁面元素

 此&#x200B;*`doPlugins`* 函數可用來執行自訂常式，以蒐集或變更資料。If you are using an object name other than "s," make sure that the *`s_doPlugins`* is renamed appropriately. For example, if your object name is s_mc, the *`s_doPlugins`* function should be called s_mc_doPlugins.

**語法和可能的值** {#section_5CFB94598521455E80947964A306EA89}

*`s_doPlugins`* 函數不應以引號括住， *`doPlugins`* 且應一律指派給 *`s_doPlugins`* 函數的名稱(如果該函數已重新命名)。

```js
s.doPlugins=s_doPlugins;
```

**範例** {#section_A5CF0054C56745268A1313CCC7730022}

```js
s.doPlugins=s_doPlugins;
```

```js
s_mc.doPlugins=s_mc_doPlugins;
```

**組態設定** {#section_641F0EC55E3349E5A3F8671446797074}

無

**缺陷、問題和提示** {#section_0C7FB61CF0C946EF8A7D1B686D36E6ED}

* 您將內容與其他客戶共用，或提取其他客戶的內容，是唯一須變更物件名稱 (例如從 s 變更為 s_mc) 的原因。重新命名 *`s_doPlugins`*[!UICONTROL 函數]*`doPlugins`* 。

* If you unexpectedly start pulling in content from another Adobe customer, and your *`s_doPlugins`* function is being overwritten, it is possible to simply rename the *`s_doPlugins`* function without changing the object name. 雖然最理想的解決方案是使用與相同頁面上的其他 JavaScript 檔案不同的物件名稱，但這並非必要動作。

## s. registerPreTractCallback和s. registerPostTrackCallback

這些函數採用參數的形式: callback (函數) 和該函數的參數。例如:

```
s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
    console.log("pre track callback"); 
    console.dir(requestUrl); // Request URL 
    console.dir(a); // param1 
    console.dir(b); // param2 
    console.dir(c); // param3 
}, "param1", "param2", "param3");
```

在註冊 callback 時，系統會利用 `requestUrl` 和任何傳入的參數叫用 callback。這項作業會發生在追蹤呼叫之前或之後，須視用來註冊 callback 的方法而定。

我們無法保證這些 callback 的呼叫順序。在前置函數中註冊的 callback，會在最終的追蹤 URL 建立時叫用。後置 callback 會在追蹤呼叫成功時呼叫 (如果追蹤呼叫失敗，系統不會叫這些函數)。任何以 `registerPreTrackCallback` 註冊的 callback 均不會影響追蹤呼叫。此外，我們不建議在任何已註冊的 callback 中呼叫任何追蹤方法，因為這樣可能會導致無限迴圈。

## s.trackDownLoadLinks {#concept_0A7AEAB3172A4BEA8B2E8B1A3A8F596C}

<!-- 
trackDownloadLinks.xml
-->

若您要在網站上追蹤可下載檔案的連結，請將 設為 'true'。

If *`trackDownloadLinks`* is 'true,' *`linkDownloadFileTypes`* is used to determine which links are downloadable files.

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | True |

若您網站上的可下載檔案沒有連結，或是您不想要追蹤可下載檔案的點按次數，則只能將 *`trackDownloadLinks`* 變數設為 'false'。If *`trackDownloadLinks`* is 'true,' when a file download link is clicked, data is immediately sent to [!DNL Analytics]. 隨下載連結傳送的資料包括連結下載 URL，以及該連結的訪客點按對映資料。若&#x200B;*`trackDownloadLinks`* 為'false'時，您網站上可下載檔案的連結的訪客點按對映資料可能會被報告。

**語法和可能的值** {#section_828492CC2A144BC68D18C30CF397EEFC}

*`trackDownloadLinks`變數應為 'true' 或 'false'。*

**範例** {#section_BE2FA1873EBD4C5CA95E98B922B10280}

```
js
s.trackDownloadLinks=true 
```

```
js
s.trackDownloadLinks=false
```

**組態設定** {#section_9A5F69966BAF433A8DA2BCF655A652D1}

無

**缺陷、問題和提示** {#section_B3764520D81143968F96CB69AADD457F}

* When *`trackDownloadLinks`* is 'false,' links that people use to download files on your site are likely to be under reported in visitor click map.
* When *`trackDownloadLinks`* is 'true,' data is sent each time a visitor clicks a file download link.

## s.trackExternalLinks {#concept_E1321318696841648A54CF77F6C4A7AF}

<!-- 
trackExternalLinks.xml
-->

如果為'true'，並用於判斷所點按的任何連結是否為退出連結。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | True |

若您網站上的可下載檔案沒有連結，或是您不想要追蹤可下載檔案的點按次數，則只能將 *`trackExternalLinks`* 變數設為 'false'。退出連結是指將訪客帶離您網站的任何連結。若&#x200B;*`trackExternalLinks`* 為'true'時，當您按一下退出連結時，會立即傳送追蹤資料。隨退出連結傳送的資料包括連結 URL、連結名稱和該連結的訪客點按對映資料。若&#x200B;*`trackExternalLinks`* 為'false'時，您網站上退出連結的訪客點按對映資料可能會被報告。

**語法和可能的值** {#section_267748949A7544658E1D838AAEF964B2}

*`trackExternalLinks`變數應為 'true' 或 'false'。*

```
js
s.trackExternalLinks=true|false
```

**範例** {#section_EF18DB05884240F5B5062631E68E10A7}

```
js
s.trackExternalLinks=true 
```

```
js
s.trackExternalLinks=false
```

**組態設定** {#section_C8748CFE36324FAFB14C23E3E1FB5082}

無

**缺陷、問題和提示** {#section_FE2C3AF17DA24EA8A944BF1D394FB5BC}

* When *`trackExternalLinks`* is 'false,' links that take people away from your site are likely to be under reported in visitor click map.
* When *`trackExternalLinks`* is 'true,' data is sent each time a visitor clicks on an exit link (before link target loads).

## s.trackInlineStats {#concept_E3A811D9761E4917935F6CD9059C7FCC}

<!-- 
trackInlineStats.xml
-->

 會判斷 ClickMap 資料是否已收集。

If *`trackInlineStats`* is 'true,' data about the page and link clicked are stored in a cookie called s_sq. If 'false,' s_sq will have a value of "[[B]]," which is considered null.

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | ClickMap | False |

**語法和可能的值** {#section_46B2C1DD0D104A01A9C239929420CD90}

```
js
s.trackInlineStats=true|false
```

*`trackInlineStats`變數應為 'true' 或 'false'。*

**範例** {#section_F146770917A3493AB8007626913CD6AB}

```js
s.trackInlineStats=true
```

```js
s.trackInlineStats=false
```

**組態設定** {#section_FB2CDB07CDCE454786D96A66E4D8EDCD}

無

## s.linkDownloadFileTypes {#concept_06CC14C69DFD4887A5E6967A157A9E05}

<!-- 
linkDownloadFileTypes.xml
-->

 變數是以逗號分隔的副檔名清單。

若您的網站包含檔案的連結，且檔案具有其中任何副檔名，這些連結的 URL 將出現在[!UICONTROL 「檔案下載」]報表中。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|--- |--- |--- |--- |
| 不適用 | 不適用 | 流量 &gt; 網站流量 &gt; 檔案下載 | "exe、zip、wav、mp3、mov、mpg、avi、wmv、doc、pdf、xls" |

此&#x200B;*`linkDownloadFileTypes`* 變數僅在設為'True'時 *`trackDownloadLinks`* 才相關。

以滑鼠左鍵點按連結時，才會計入[!UICONTROL 「檔案下載」]報表中。任何在頁面載入時自動啟動的檔案下載，或是只會在重新導向後執行的檔案下載，都不會計入[!UICONTROL 「檔案下載」]報表中。當您以滑鼠右鍵按一下檔案，然後選取「另存目標...」選項時，並不會計入[!UICONTROL 「檔案下載」]報表中。

此&#x200B;*`linkDownloadFileTypes`* 變數可用來追蹤 RSS 饋送的點按次數。If you have links to RSS feeds with a .xml or other extension, appending ",xml" to the *`linkDownloadFileTypes`* list allows you to see how often each RSS link is clicked.

**語法和可能的值** {#section_E0B3F3817BBF4B11AFAABEF8BB951E5A}

僅包含副檔名 (無空格)。

```js
s.linkDownloadFileTypes="type1[,type2[,type3[...]]]"
```

任何副檔名皆可包含在清單內。請留意勿將常見副檔名 (例如 htm 或 aspx) 納入 *`linkDownloadFileTypes`*。此舉將導致每次點按時都會發送額外的影像要求，而計為主要伺服器呼叫的費用。

**範例** {#section_C53F1AF768434CEBA65F3D255BC470AD}

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls"
```

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls,xml"
```

**組態設定** {#section_CE24D5852E4D441A958A4EDDB82382A7}

無

**缺陷、問題和提示** {#section_786CF22D5553429EB6524B13774793BC}

* 以左鍵點按下載檔案時，才會使 URL 出現在[!UICONTROL 「檔案下載」]報表中。
* 將常見副檔名納入&#x200B;*`linkDownloadFileTypes`*&#x200B;中，可能會大幅增加傳送至 Adobe 伺服器的伺服器呼叫總數。
* 伺服器端重新導向的連結或自動開始下載檔案的 HTML 頁面不會被計入，除非該副檔名位於 *`linkDownloadFileTypes`*.
* 使用 JavaScript 的連結 (如 javascript:openLink( )) 不會計入檔案下載中。

## s.linkInternalFilters {#concept_D53C1186762E4AAE82451712B0801CAD}

<!-- 
linkInternalFilters.xml
-->

 變數可用來決定您網站上的哪些連結是退出連結。

這是篩選器的逗號分隔清單，它表示屬於網站組成部分的連結。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 路徑 &gt; 登入與退出 &gt; 退出連結 |  |

>[!NOTE]
>
>我們先前建議將linkInternalFilters設為javascript。但是，這會導致系統將所有網域都視為外部網域，包括目前標籤所在的網域。若要將多個網域視為內部網域，您可以新增這些網域 (如下列範例所示)。

*`linkInternalFilters`* 變數可用來判斷某個連結是否為退出連結，其定義為將訪客帶離您網站的任何連結。無論退出連結的目標視窗是快顯視窗還是現有視窗，這都不會影響該連結是否會出現在退出連結報表中。只有在  *`trackExternalLinks`* 設為 `"true"`. (如需 DTM 如何處理退出連結的相關資訊，請參閱動態標籤管理文件中的[連結追蹤](https://marketing.adobe.com/resources/help/en_US/dtm/link_tracking.html)。)The filters in *`linkInternalFilters`* are not case-sensitive.

The list of filters in *`linkInternalFilters`* applies to the domain and path of any link by default. If *`linkLeaveQueryString`* is set to `"true"`, then the filters apply to the entire URL (domain, path, and query string). 這些篩選器可始終被套用到 URL 的絕對路徑，即使相對路徑被用作 href 值。

請留意，您的網站的所有網域 (以及任何使用您的 JavaScript 檔案的合作夥伴)，都會納入 *`linkInternalFilters`*。若您未將所有網域納入此清單中，則位於和連結至這些網域的連結，都會被視為退出連結，而增加傳送的伺服器呼叫。If you would like multiple domains or companies to use a single [!DNL AppMeasurement] for JavaScript file, you may consider populating *`linkInternalFilters`* on the page, overriding the value specified in the JavaScript file. 若您有會立即重新導向至您的主要網域的虛名網域，這些虛名網域並不需要納入清單中。

以下範例可說明此變數的使用方式。In this example, the URL of the page is `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="mysite.com" 
s.linkExternalFilters="" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Exit Link</a> 
<a href="https://www2.site1.com/partners/">Exit Link</a> 
```

**語法和可能的值** {#section_810966F09912415B96EA9C2EDAE0CEA0}

*`linkInternalFilters`* 變數是以逗號分隔的ASCII字元清單。不允許空格。

```js
s.linkInternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

**範例** {#section_491F48556DC247889D54C66FC431B4EC}

```js
s.linkInternalFilters="mysite.com"
```

```js
s.linkInternalFilters="mysite.com,mysite.net,vanity1.com"
```

**組態設定** {#section_546AC1FACB664ABFBCF312990097C987}

無

**缺陷、問題和提示** {#section_E83A6F8B6EE44D51A2800D83F8BB264F}

* Include all domains that the [!DNL AppMeasurement] for JavaScript file may be served under in the filter list.
* 定期檢查「[!UICONTROL 路徑] &gt; [!UICONTROL 登入與退出] &gt; [!UICONTROL 退出連結]」報表，以確定該報表不含任何不正確的項目。

* 定期檢閱合作夥伴合約，以確認其中是否包含連結追蹤的相關限制。例如，合約可能禁止您追蹤出現在合作夥伴顯示廣告中的連結。將合作夥伴連結的網域新增至  *`linkInternalFilters`*:

```js
s.linkInternalFilters="mysite.com,mysite.net,mypartner.net/adclick"
```

## s.linkLeaveQueryString {#concept_118C280E29394DB5A16DBBF41EB4D742}

<!-- 
linkLeaveQueryString.xml
-->

預設情況下，查詢字串被排除在所有 報表之外。

對於部分退出連結和下載連結，URL 的重要部分可能就在查詢字串中，如下列範例 URL 所示。

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

下載檔案名稱可定義在查詢字串中，因此，必須透過查詢字串使[!UICONTROL 「檔案下載」]報表更為精準。

此 *`linkLeaveQueryString`* 變數可決定是否應將查詢字串納入[!UICONTROL 「退出連結」]和[!UICONTROL 「檔案下載」]報表中。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|--- |--- |--- |--- |
| 不適用 | 不適用 | 退出連結檔案下載 | false |

>[!NOTE]
>
>Setting `linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.

**語法** {#section_C40CF036B71A496D92574C6E46DE8302}

```js
s.linkLeaveQueryString=[false/true]
```

**範例** {#section_E42CEC8DDE624A4B979F4F6C8094A7F9}

```js
s.linkLeaveQueryString=false
```

**可能的值** {#section_E13211451B664B909B1BFDD050472F18}

```js
s.linkLeaveQueryString=false
```

```js
s.linkLeaveQueryString=true
```

**組態設定** {#section_835FD74D3CA9425A9D091CACF88A6F1F}

此變數不需進行設定。

**缺陷、問題和提示** {#section_085E79D1A7F74F5D95F82D34FB82AEC4}

* Setting `s.linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.
* `linkLeaveQueryString` 變數不會影響記錄的頁面URL、訪客點按對映或 [!UICONTROL 路徑] 報表。

## s.linkTrackVars {#concept_A6B117826C15402EBD0781A94C8065B9}

<!-- 
linkTrackVars.xml
-->

 變數是以逗號分隔，隨自訂、退出和下載連結而傳送的變數清單。

If *`linkTrackVars`* is set to "", all variables that have values are sent with link data. To avoid inflation of instances or page views associated with other variables, Adobe recommends populating *`linkTrackVars`* and *`linkTrackEvents`* in the [!UICONTROL onClick] event of a link that is used for link tracking.

All variables that should be sent with link data (custom, exit, and download links) should be listed in *`linkTrackVars`*. If *`linkTrackEvents`* is used, *`linkTrackVars`* should contain "events."

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 任何 | "無" |

在填入 *`linkTrackVars`*&#x200B;請勿使用變數的's.'首碼。For example, instead of populating *`linkTrackVars`* with "s.prop1," you should populate it with "prop1." The following example illustrates how *`linkTrackVars`* should be used.

```js
s.linkTrackVars="eVar1,events" 
s.linkTrackEvents="event1" 
s.events="event1" 
s.eVar1="value A" 
s.eVar2="value B" 
s.t() // eVar1, event1 and event2 are recorded 
<a href="https://google.com">event1 and eVar1 are recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.eVar1='value C';s.events='';s.tl(this,'o')">eVar1 is recorded</a> 
```

由於 google.com 的連結是退出連結 (除非您正在使用 Google)，event1 和 eVar1 會隨退出連結資料傳送，而增加與 eVar1 相關聯的例項數和 event1 的引發次數。In the link to [!DNL test.php], [!UICONTROL eVar1] is sent with a value of 'value C' because that is the current value of [!UICONTROL eVar1] at the time that *`tl()`* is called.

**語法和可能的值** {#section_DCC239F5CFE74959856764DAB1862BA7}

*`linkTrackVars`* 變數是區分大小寫、以逗號分隔的變數名稱清單，沒有物件名稱前置詞。請使用 'eVar1'，而非 's.eVar1'。

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

此&#x200B;*`linkTrackVars`* 變數只能包含傳送到 [!DNL Analytics]的變數，即： *`events`**`campaign`**`purchaseID`*、 *`products`*[!UICONTROL eVar1-75]、 [!UICONTROL prop1-75]、 [!UICONTROL hier1-5]*`channel`**`server`*、 *`state`*&#x200B;和 *`zip`**`pageType`*.

**範例** {#section_546BAAC7373A41BF8583B280EAAB607C}

```js
s.linkTrackVars="events,prop1,eVar49"
```

```js
s.linkTrackVars="products"
```

**組態設定** {#section_E387604B8A434A7F89A82A886649A89D}

無

**缺陷、問題和提示** {#section_99E0783A608C4462945F35D21AB4AC2B}

* If *`linkTrackVars`* is blank, all variables that have values are tracked with all server calls.
* Any variable listed in *`linkTrackVars`* that has a value at the time of any download, exit, or custom link, are tracked.
* If *`linkTrackEvents`* is used, *`linkTrackVars`* must contain "events."

* 變數請勿使用 "s." 或 "s_objectname."前置詞。

## s.linkTrackEvents {#concept_34D029097A674D0A97690C9569590EF5}

<!-- 
linkTrackEvents.xml
-->

The  variable is a comma-separated list of events that are sent with a [!UICONTROL custom], [!UICONTROL exit], or [!UICONTROL download] link.

If an event is not in *`linkTrackEvents`*, it is not sent to [!DNL Analytics], even if it is populated in the [!UICONTROL onClick] event of a link, as shown in the following example:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

在 [!DNL help.php] 的第一個連結中，請留意到事件變數保有連結被點按之前所設定的值。這讓 event1 可隨自訂連結傳送。In the second example, the link to [!DNL test.php], event2 is not recorded because it is not listed in *`linkTrackEvents`*.

To avoid confusion and potential problems, Adobe recommends populating *`linkTrackVars`* and *`linkTrackEvents`* in the [!UICONTROL onClick] event of a link that is used for link tracking.

*`linkTrackEvents`* 變數包含應隨 [!UICONTROL 自訂]、 [!UICONTROL 下載]和 [!UICONTROL 退出] 連結而傳送的事件。This variable is only considered if *`linkTrackVars`* contains "events."

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 轉換 | "無" |

**語法和可能的值** {#section_89BA2425FBDC400A8C8B7FCDE7D67D63}

*`linkTrackEvents`* 變數是以逗號分隔的事件清單(無空格)。

```js
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

Only event names are allowed in *`linkTrackEvents`*. These events are listed in [Events](../../../implement/js-implementation/c-variables/page-variables.md#concept_FFD115543D54401B98FE683BD7D5B3FE). 若事件名稱之前或之後出現空格，該事件即無法隨任何連結影像要求傳送。

**範例** {#section_AB7F952E522A4DCC92944EBF74C26BDD}

```js
s.linkTrackEvents="purchase,event1"
```

```js
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

**組態設定** {#section_D938A47346D94A0C9E98FB327F2EF349}

無

**缺陷、問題和提示** {#section_DBB68BECC9D44380816113DB2566C38C}

* The JavaScript file only uses *`linkTrackEvents`* if *`linkTrackVars`* contains the "events" variable. "events" should be included in *`linkTrackVars`* only when *`linkTrackEvents`* is defined.

* Beware if an event is fired on a page, and is listed in *`linkTrackEvents`*. That event is recorded again with any [!UICONTROL exit], [!UICONTROL download], or [!UICONTROL custom] links unless the events variable is reset prior to that event (in the [!UICONTROL onClick] of a link or after the call to the *`t()`* function).

* If *`linkTrackEvents`* contains spaces between event names, the events are not recorded.

## s.linkExternalFilters {#concept_92A59169DCE443EBAE81A373B27BB6DD}

<!-- 
linkExternalFilters.xml
-->

若您的網站含有許多外部網站的連結，而您不想追蹤所有的退出連結，請使用 來報告退出連結的特定子集。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 路徑 &gt; 登入與退出 &gt; 退出連結 | "" |

此 *`linkExternalFilters`* 變數是可搭配使用的變數，用來決定 *`linkInternalFilters`* 某個連結是否為退出連結。退出連結被定義為將訪客帶離您網站的任何連結。無論退出連結的目標視窗是快顯視窗還是現有視窗，這都不會影響該連結是否會出現在退出連結報表中。只有在&#x200B;*`trackExternalLinks`* 設為'true'。The filters in *`linkExternalFilters`* and *`linkInternalFilters`* are case insensitive.

>[!NOTE]
>
>If you don't want to use *`linkExternalFilters`*, delete it or set it to "".

The filters list in *`linkExternalFilters`* and *`linkInternalFilters`* apply to the domain and path of any link by default. If *`linkLeaveQueryString`* is set to 'true,' the filters apply to the entire URL (domain, path, and query string). 這些篩選器可始終被套用到 URL 的絕對路徑，即使相對路徑被用作 href 值。

有許多公司認為 *`linkInternalFilters`* 讓他們能夠充分控制退出連結 *`linkExternalFilters`*。Using *`linkExternalFilters`* simply decreases the likelihood that an exit link is considered external. If *`linkExternalFilters`* has a value, then a link is considered only external if it does not match *`linkInternalFilters`* and does match *`linkExternalFilters`*.

以下範例可說明此變數的使用方式。In this example, the URL of the page is `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="javascript:,mysite.com" 
s.linkExternalFilters="site1.com,site2.com,site3.com/partners" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Not an Exit Link</a> 
<a href="https://www.site1.com">Exit Link</a> 
<a href="https://www2.site3.com/partners/offer.asp">Exit Link</a> 
```

**語法和可能的值** {#section_E35DAAAE8BDE44CEB8F6763EF1344693}

*`linkExternalFilters`* 變數是以逗號分隔的ASCII字元清單。不允許空格。

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

URL 的任何部分皆可包含在 *`linkExternalFilters`*&#x200B;以逗號分隔。

**範例** {#section_1D2F13EEC28942868C2F4207ADF2DDE0}

```js
s.linkExternalFilters="partnersite.com,partnertwo.net/path/"
```

```js
s.linkExternalFilters=""
```

**組態設定** {#section_2D0CA911855B4B3698145FC18D5021C3}

無

**缺陷、問題和提示** {#section_8B40E6F539E3473B934A8DB7C5086D73}

* Using *`linkExternalFilters`* can result in fewer links on your site being exit links. Do not use this variable in place of *`linkInternalFilters`* to force internal links to become exit links.

* If *`linkExternalFilters`* should be applied to the query string of a link, make sure *`linkLeaveQueryString`* is set to 'true.' See [linkLeaveQueryString](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_118C280E29394DB5A16DBBF41EB4D742) before setting to `"true"`.

* To disable exit link tracking, set *`trackExternalLinks`* to `"false"`.

## s.usePlugins {#concept_81836470A25C41228CE04084565F667D}

<!-- 
s_usePlugins.xml
-->

If the  function is available and contains useful code, [!UICONTROL s_usePlugins] should be set to 'true.'

[!UICONTROL 當usePlugins] 為'true'時， *`s_doPlugins`* 會在每個影像要求之前呼叫函數。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | True |

**語法和可能的值** {#section_BAD0F150047A4B7FB1214491B939A1FC}

```js
s.usePlugins=true|false
```

[!UICONTROL usePlugins] 變數應為 'true' 或 'false'。

**範例** {#section_1423CC3026384B1A9F78B272166B1DF5}

```js
s.usePlugins=true
```

```js
s.usePlugins=false
```

[!UICONTROL 如果] 未在JavaScript檔案中宣告 *`s_doPlugins`* 函數，usePlugins變數只應為false(或未宣告)。

**組態設定** {#section_DFD41717134147E988B6AFC7DE5BB9E3}

無