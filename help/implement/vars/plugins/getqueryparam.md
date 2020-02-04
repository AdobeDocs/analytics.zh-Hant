---
title: getQueryParam
description: 擷取URL查詢字串參數的值。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobe外掛程式：getQueryParam

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以協助您從Adobe Analytics中獲得更多價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外 `getQueryParam` 掛程式可讓您擷取URL中所含任何查詢字串參數的值。 它對於從著陸頁面URL擷取內部和外部促銷活動代碼非常有用。 在擷取搜尋詞或其他查詢字串參數時，它也很有用。

此外掛程式在剖析複雜URL時提供強穩的功能，包括雜湊和包含多個查詢字串參數的URL。 如果您只有簡單的查詢字串參數需求，Adobe建議使用Launch中的URL參數功能或AppMeasurement `Util.getQueryParam` 中包含的方法。

## 使用Adobe Experience Platform Launch擴充功能安裝增效模組

Adobe提供擴充功能，讓您使用最常用的增效模組。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 按一下所要的屬性。
1. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下「目錄 [!UICONTROL 」按鈕]
1. 安裝和發佈 [!UICONTROL Common Analytics Plugins] extension
1. 對於您想要使用外掛程式的任何「啟動規則」，請新增具有下列設定的動作：
   * 擴充功能：常見Analytics外掛程式
   * 動作類型：初始化addProductEvar
1. 儲存並發佈規則的變更

## 使用Launch自訂程式碼編輯器安裝外掛程式

如果您不想使用外掛程式擴充功能，則可使用自訂程式碼編輯器。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 按一下所要的屬性。
1. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下 [!UICONTROL Adobe Analytics延伸模組下的「設定] 」按鈕。
1. 展開「使 [!UICONTROL 用自訂程式碼] accordion設定追蹤」，此會顯示 [!UICONTROL 「開啟編輯器] 」按鈕。
1. 開啟自訂程式碼編輯器，並將下方提供的外掛程式碼貼入編輯視窗。
1. 儲存變更並發佈至Analytics擴充功能。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v3.3 (Requires pt plug-in) */
s.getQueryParam=function(qsp,de,url){var g=this,e="",k=function(b,de){de=de.split("?").join("&");de=de.split("#").join("&");var d=de.indexOf("&"),url="";b&&(-1<d||de.indexOf("=")>d)&&(d=de.substring(d+1),url=g.pt(d,"&","gpval",b));return url};qsp=qsp.split(",");var l=qsp.length;g.gpval=function(de,b){if(de){var d=de.split("="),url=d[0];d=d[1]?d[1]:!0;if(b.toLowerCase() ==url.toLowerCase())return"boolean"===typeof d?d:this.unescape(d)}return""};de=de?de:"";url=(url?url:g.pageURL?g.pageURL: location.href)+"";if((4<de.length||-1<de.indexOf("="))&&url&&4>url.length){var b=de;de=url;url=b}for(var h=0;h<l;h++)b=k(qsp[h],url) ,"string"===typeof b?(b=-1<b.indexOf("#")?b.substring(0,b.indexOf("#")):b,e+=e?de+b:b):e=""===e?b:e+(de+b);return e};

/* Adobe Consulting Plugin: pt v2.01 */ 
s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

該方 `getQueryParam` 法使用以下引數：

* **`qsp`**（必要）:要在URL中尋找的查詢字串參數的逗號分隔清單。 不區分大小寫。
* **`de`**（可選）:若多個查詢字串參數相符，則使用的分隔字元。 預設為空字串。
* **`url`**（可選）:自訂URL、字串或變數，以從中擷取查詢字串參數值。 預設為`window.location`。

呼叫此方法會根據上述引數和URL傳回值：

* 如果找不到相符的查詢字串參數，則方法會傳回空字串。
* 如果找到匹配的查詢字串參數，則方法會傳回查詢字串參數值。
* 如果找到相符的查詢字串參數，但該值為空，則方法會傳回 `true`。
* 如果找到多個匹配的查詢字串參數，則方法會傳回一個字串，其中每個參數值都由引數中的字串 `de` 分隔。

## 呼叫範例

### 範例#1

如果目前的URL如下：

```js
http://www.abc123.com/?cid=trackingcode1
```

下列程式碼會將s.campaign設為&quot;trackingcode1&quot;:

```js
s.campaign=s.getQueryParam('cid');
```

### 範例#2

如果目前的URL如下：

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

下列程式碼會將s.campaign設為&quot;trackingcode1:123456&quot;:

```js
s.campaign=s.getQueryParam('cid,ecid',':');
```

### 範例#3

如果目前的URL如下：

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

下列程式碼會將s.campaign設為&quot;trackingcode1123456&quot;:

```js
s.campaign=s.getQueryParam('cid,ecid');
```

### 範例#4

如果目前的URL如下：

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456#location
```

下列程式碼會將s.campaign設為&quot;123456&quot;:

```js
s.campaign=s.getQueryParam('ecid');
```

### 範例#5

如果目前的URL如下：

```js
http://www.abc123.com/#location&cid=trackingcode1&ecid=123456
```

下列程式碼會將s.campaign設為&quot;123456&quot;

```js
s.campaign=s.getQueryParam('ecid');
```

**** 注意：外掛程式會在不存在問號時，以問號取代URL以檢查雜湊字元。  如果URL包含雜湊字元前的問號，外掛程式會以&amp;符號取代URL以檢查雜湊字元；

### 範例#6

如果目前的URL是下列……

```js
http://www.abc123.com/
```

...及若變數s.testURL的設定如下：

```js
s.testURL="http://www.abc123.com/?cid=trackingcode1&ecid=123456#location&pos=300";
```

下列程式碼完全不會設定s.campaign:

```js
s.campaign=s.getQueryParam('cid');
```

但是，下列程式碼會將s.campaign設為&quot;trackingcode1&quot;:

```js
s.campaign=s.getQueryParam('cid','',s.testURL);
```

**** 注意：第三個參數可以是程式碼將用來嘗試在

下列程式碼會將s.eVar2設為&quot;123456|trackingcode1|true|300&quot;:

```js
s.eVar2=s.getQueryParam('ecid,cid,location,pos','|',s.testURL);
```

* 值123456來自s.testURL變數中的ecid參數
* trackingcode1的值來自s.testURL變數中的cid參數
* true的值來自s.testURL變數中雜湊字元後之位置參數的存在（但非值）

值300來自s.testURL變數中pos參數的值

## 版本記錄

### 3.3（2019年9月24日）

* 略過不必要的邏輯以減少程式碼大小

### 3.2（2018年5月15日）

* 將 `findParameterValue` 和 `getParameterValue` 函式移入函 `getQueryParam` 數

### 3.1（2018年5月10日）

* 修正擷取無值查詢字串參數的問題

### 3.0（2018年4月16日）

* 點數發行（重新編譯，程式碼大小較小）。
* 將協助程式函式重新 `findParameterValue` 命名為 `getParameterValue` 可讀性功能。
* 已移除新增參數以尋找URL雜湊中所含參數的需求

### 2.5（2016年1月8日）

* 與H程式碼和AppMeasurement相容(需 `s.pt` 要與AppMeasurement)。

### 2.4

* 新增參 `h` 數，讓程式碼可尋找雜湊(`#`)字元後找到的查詢字串參數

### 2.3

* 修正外掛程式只有在追蹤程式碼之後出現雜湊時才起作用的回歸問題

### 2.2

* 現在會從傳回值中移除雜湊字元（以及之後的所有項目）

### 2.1

* 與H.10程式碼相容
