---
title: getQueryParam
description: 擷取 URL 查詢字串參數的值。
exl-id: d2d542d1-3a18-43d9-a50d-c06d8bd473b8
translation-type: ht
source-git-commit: 5a087087c8f54650173391bd7766bfdfd12ccb7e
workflow-type: ht
source-wordcount: '918'
ht-degree: 100%

---

# Adobe 外掛程式：getQueryParam

>[!IMPORTANT]
>
>此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`getQueryParam` 外掛程式讓您可擷取 URL 中所含任何查詢字串參數的值。如需從登陸頁面 URL 擷取內部和外部促銷活動程式碼，此外掛程式非常有用。擷取搜尋詞或其他查詢字串參數時，它也很有用。

此外掛程式提供完善的功能，可剖析複雜的 URL，包括雜湊和包含多個查詢字串參數的 URL。如果您的查詢字串參數需求很簡單，Adobe 建議使用 Launch 中的 URL 參數功能，或是 AppMeasurement 中包含的 [`Util.getQueryParam()`](../functions/util-getqueryparam.md) 方法。

## 使用 Adobe Experience Platform Launch 擴充功能安裝外掛程式

Adobe 提供一個擴充功能，可讓您使用最常用的外掛程式。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
1. 按一下所需的屬性。
1. 前往[!UICONTROL 擴充功能]標籤，然後按一下[!UICONTROL 「目錄」]按鈕
1. 安裝並發佈[!UICONTROL 常用 Analytics 外掛程式]擴充功能
1. 如果您尚未執行上述步驟，請使用下列設定建立標示為「初始化外掛程式」的規則：
   * 條件：無
   * 事件：核心 - 已載入程式庫 (頁面頂端)
1. 使用下列設定將動作新增至上述規則：
   * 擴充功能：常用 Analytics 外掛程式
   * 動作類型：初始化 getQueryParam
1. 儲存並發佈規則的變更。

## 使用 Launch 自訂程式碼編輯器安裝外掛程式

如果您不想使用外掛程式擴充功能，可以使用自訂程式碼編輯器。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
1. 按一下所需的屬性。
1. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 擴充功能底下的[!UICONTROL 「設定」]按鈕。
1. 展開[!UICONTROL 使用自訂程式碼設定追蹤]摺疊式功能表，便會顯示[!UICONTROL 「開啟編輯器」]按鈕。
1. 開啟自訂程式碼編輯器，並將下方提供的外掛程式程式碼貼入編輯視窗中。
1. 儲存並發佈 Analytics 擴充功能的變更。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v4.0.1  */
function getQueryParam(a,d,f){function n(g,c){c=c.split("?").join("&");c=c.split("#").join("&");var e=c.indexOf("&");if(g&&(-1<e||c.indexOf("=")>e)){e=c.substring(e+1);e=e.split("&");for(var h=0,p=e.length;h<p;h++){var l=e[h].split("="),q=l[1];if(l[0].toLowerCase()===g.toLowerCase())return decodeURIComponent(q||!0)}}return""}if("-v"===a)return{plugin:"getQueryParam",version:"4.0.1"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var g=0,c;g<window.s_c_il.length;g++)if(c=window.s_c_il[g],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.getQueryParam="4.0");if(a){d=d||"";f=(f||"undefined"!==typeof b&&b.pageURL||location.href)+"";(4<d.length||-1<d.indexOf("="))&&f&&4>f.length&&(b=d,d=f,f=b);b="";for(var m=a.split(","),r=m.length,k=0;k<r;k++)a=n(m[k],f),"string"===typeof a?(a=-1<a.indexOf("#")?a.substring(0,a.indexOf("#")):a,b+=b?d+a:a):b=""===b?a:b+(d+a);return b}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getQueryParam` 方法使用以下引數：

* **`qsp`** (必要)：要在 URL 中尋找的查詢字串參數清單 (以逗號分隔)。不區分大小寫。
* **`de`** (選用)：有多個查詢字串參數相符時要使用的分隔字元。預設為空字串。
* **`url`** (選用)：自訂 URL、字串或變數，系統會從其中擷取查詢字串參數值。預設為 `window.location`。

若呼叫此方法，系統會根據上述引數和 URL 傳回值：

* 如果找不到相符的查詢字串參數，方法會傳回空字串。
* 如果找到相符的查詢字串參數，方法會傳回查詢字串參數值。
* 如果找到相符的查詢字串參數但值為空，方法會傳回 `true`。
* 如果找到多個相符的查詢字串參數，方法會傳回一個字串，其中每個參數值都由 `de` 引數中的字串分隔開。

## 呼叫範例

### 範例 #1

如果目前的 URL 為：

```js
http://www.abc123.com/?cid=trackingcode1
```

下列程式碼會將 s.campaign 設為等於 &quot;trackingcode1&quot;：

```js
s.campaign=s.getQueryParam('cid');
```

### 範例 #2

如果目前的 URL 為：

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

下列程式碼會將 s.campaign 設為等於「trackingcode1:123456」：

```js
s.campaign=s.getQueryParam('cid,ecid',':');
```

### 範例 #3

如果目前的 URL 為：

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

下列程式碼會將 s.campaign 設為等於 &quot;trackingcode1123456&quot;：

```js
s.campaign=s.getQueryParam('cid,ecid');
```

### 範例 #4

如果目前的 URL 為：

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456#location
```

下列程式碼會將 s.campaign 設為等於「123456」：

```js
s.campaign=s.getQueryParam('ecid');
```

### 範例 #5

如果目前的 URL 為：

```js
http://www.abc123.com/#location&cid=trackingcode1&ecid=123456
```

下列程式碼會將 s.campaign 設為等於「123456」

```js
s.campaign=s.getQueryParam('ecid');
```

**注意：**&#x200B;若不存在問號，該外掛程式會以問號取代 URL 以檢查雜湊字元。如果 URL 中雜湊字元前含有問號，外掛程式會以 &amp; 符號取代 URL 以檢查雜湊字元；

### 範例 #6

如果目前的 URL 為...

```js
http://www.abc123.com/
```

...且若變數 s.testURL 的設定如下：

```js
s.testURL="http://www.abc123.com/?cid=trackingcode1&ecid=123456#location&pos=300";
```

下列程式碼完全不會設定 s.campaign：

```js
s.campaign=s.getQueryParam('cid');
```

但是，下列程式碼會將 s.campaign 設為 &quot;trackingcode1&quot;：

```js
s.campaign=s.getQueryParam('cid','',s.testURL);
```

**注意：**&#x200B;第三個參數可為任何字串/變數，程式碼將用來嘗試在其中尋找查詢字串參數

下列程式碼會將 s.eVar2 設為等於「123456|trackingcode1|true|300」：

```js
s.eVar2=s.getQueryParam('ecid,cid,location,pos','|',s.testURL);
```

* 123456 值來自 s.testURL 變數中的 ecid 參數
* trackingcode1 值來自 s.testURL 變數中的 cid 參數
* true 值來自 s.testURL 變數中雜湊字元之後位置參數的存在 (但非值)

300 值來自 s.testURL 變數中 pos 參數的值

## 版本記錄

### 4.0.1 (2021 年 3 月 26 日)

* 已更新後述情況的問題：如果查詢字串中未顯示查詢參數，則傳回 undefined 而非 &quot;&quot;。

### 4.0 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。
* 已移除 pt 外掛程式上的相依性。

### 3.3 (2019 年 9 月 24 日)

* 略過不必要的邏輯以縮小程式碼大小

### 3.2 (2018 年 5 月 15 日)

* 將 `findParameterValue` 和 `getParameterValue` 函數移入 `getQueryParam` 函數

### 3.1 (2018 年 5 月 10 日)

* 修正擷取無值查詢字串參數的問題

### 3.0 (2018 年 4 月 16 日)

* 單點發行 (重新編譯，程式碼大小較小)。
* 為提高可讀性，將協助程式函數重新命名為 `findParameterValue` 和 `getParameterValue`。
* 移除新增引數以尋找 URL 雜湊中所含參數的必要性

### 2.5 (2016 年 1 月 8 日)

* 與 H-Code 和 AppMeasurement 相容(需要 `s.pt` 搭配 AppMeasurement)。

### 2.4

* 新增 `h` 參數，讓程式碼可尋找在雜湊 (`#`) 字元後發現的查詢字串參數

### 2.3

* 修正外掛程式只有在追蹤代碼之後出現雜湊時才運作的回歸問題

### 2.2

* 現在會從傳回值中移除雜湊字元 (以及之後的所有內容)

### 2.1

* 與 H.10 程式碼相容
