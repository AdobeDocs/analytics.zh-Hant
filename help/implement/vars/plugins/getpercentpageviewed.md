---
title: getPercentPageViewed
description: 擷取訪客所檢視的頁面比例。
feature: Variables
exl-id: 7a842cf0-f8cb-45a9-910e-5793849bcfb8
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 84%

---

# Adobe 外掛程式：getPercentPageViewed

{{plug-in}}

`getPercentPageViewed` 外掛程式可測量訪客的捲動活動，以查看訪客在前往其他頁面前所檢視的頁面比例。如果您的頁面高度較小或不想測量捲動活動，就不需要此外掛程式。

## 使用Web SDK或Web SDK擴充功能安裝外掛程式

此外掛程式尚不支援在Web SDK中使用。

## 使用Adobe Analytics擴充功能安裝外掛程式

Adobe提供擴充功能，可讓您搭配Adobe Analytics使用最常用的外掛程式。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往[!UICONTROL 擴充功能]標記，然後按一下[!UICONTROL 「目錄」]按鈕
1. 安裝並發佈[!UICONTROL 常用 Analytics 外掛程式]擴充功能
1. 如果您尚未執行上述步驟，請使用下列設定建立標示為「初始化外掛程式」的規則：
   * 條件：無
   * 事件：核心 - 已載入資料庫 (頁面頂端)
1. 使用下列設定將動作新增至上述規則：
   * 擴充功能：常用 Analytics 外掛程式
   * 動作類型：初始化 getPercentPageViewed
1. 儲存並發佈規則的變更。

## 使用自訂程式碼編輯器安裝外掛程式

如果您不想使用常見Analytics外掛程式擴充功能，可以使用自訂程式碼編輯器。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的屬性。
1. 前往[!UICONTROL 擴充功能]索引標籤，然後按一下 Adobe Analytics 擴充功能底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
1. 展開[!UICONTROL 使用自訂程式碼設定追蹤]摺疊式功能表，便會顯示[!UICONTROL 「開啟編輯器」]按鈕。
1. 開啟自訂程式碼編輯器，並將下方提供的外掛程式程式碼貼入編輯視窗中。
1. 儲存並發佈 Analytics 擴充功能的變更。

## 使用 AppMeasurement 安裝外掛程式

Analytics 追蹤物件實例化 (使用 [`s_gi`](../functions/s-gi.md)) 後，將下列程式碼複製並貼到 AppMeasurement 檔案中的任何位置。保留您實作中的程式碼備註和版本號碼，有助於 Adobe 疑難排解任何可能問題。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPercentPageViewed v5.1 */
function getPercentPageViewed(pid,ch){var e=pid,i=ch;if("-v"===e)return{plugin:"getPercentPageViewed",version:"5.1"};var t=function(){if(void 0!==window.s_c_il){for(var e,i=0;i<window.s_c_il.length;i++)if((e=window.s_c_il[i])._c&&"s_c"===e._c)return e}}();function o(){if(window.ppvID){var e=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),i=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,t=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+i,o=Math.min(Math.round(t/e*100),100),n=Math.floor(e/i),p=Math.floor(t/i),s="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||!0==window.ppvChange&&window.cookieRead("s_tp")&&e!=window.cookieRead("s_tp")){if((decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",t),window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");var a=window.cookieRead("s_ppv"),c=a.indexOf(",")>-1?a.split(","):[],d=c[0]?c[0]:"",r=window.cookieRead("s_ips"),l=c[3]?c[3]:"";s=d+","+Math.round(r/e*100)+","+Math.round(l/e*100)+","+o+","+l+","+n+","+p}window.cookieWrite("s_tp",e)}else s=window.cookieRead("s_ppv");var v=s&&s.indexOf(",")>-1?s.split(",",7):[],f=v.length>0?v[0]:encodeURIComponent(window.ppvID),$=v.length>1?parseInt(v[1]):o,h=v.length>2?parseInt(v[2]):o,u=v.length>4?parseInt(v[4]):t,k=v.length>5?parseInt(v[5]):n,m=v.length>6?parseInt(v[6]):p;o>0&&(s=f+","+$+","+(o>h?o:h)+","+o+","+(t>u?t:u)+","+(n>k?n:k)+","+(p>m?p:m)),window.cookieWrite("s_ppv",s)}}void 0!==t&&(t.contextData.getPercentPageViewed="5.1"),window.pageName=void 0!==t&&t.pageName||"",window.cookieWrite=window.cookieWrite||function(e,i,t){if("string"==typeof e){if(g=function(){var e=window.location.hostname,i=window.location.hostname.split(".").length-1;if(e&&!/^[0-9.]+$/.test(e)){i=2<i?i:2;var t=e.lastIndexOf(".");if(0<=t){for(;0<=t&&1<i;)t=e.lastIndexOf(".",t-1),i--;t=0<t?e.substring(t):e}}return t}(),i=void 0!==i?""+i:"",t||""===i){if(""===i&&(t=-60),"number"==typeof t){var o=new Date;o.setTime(o.getTime()+6e4*t)}else o=t}return!!e&&(document.cookie=encodeURIComponent(e)+"="+encodeURIComponent(i)+"; path=/;"+(t?" expires="+o.toUTCString()+";":"")+(g?" domain="+g+";":""),void 0!==window.cookieRead)&&window.cookieRead(e)===i}},window.cookieRead=window.cookieRead||function(e){if("string"!=typeof e)return"";e=encodeURIComponent(e);var i=" "+document.cookie,t=i.indexOf(" "+e+"="),o=0>t?t:i.indexOf(";",t);return(e=0>t?"":decodeURIComponent(i.substring(t+2+e.length,0>o?i.length:o)))?e:""},window.p_fo=window.p_fo||function(e){return window.__fo||(window.__fo={}),!window.__fo[e]&&(window.__fo[e]={},!0)};var n=window.cookieRead("s_ppv"),p=n.indexOf(",")>-1?n.split(","):[];p[0]=p.length>0?decodeURIComponent(p[0]):"",e=e||(window.pageName?window.pageName:document.location.href),void 0===i||!0==i?window.ppvChange=!0:window.ppvChange=!1,void 0!==t&&t.linkType&&"o"===t.linkType||(window.ppvID&&window.ppvID===e||(window.ppvID=e,window.cookieWrite("s_ppv",""),o()),window.p_fo("s_gppvLoad2")&&window.addEventListener&&(window.addEventListener("load",o,!1),window.addEventListener("click",o,!1),window.addEventListener("scroll",o,!1)),this._ppvPreviousPage=p[0]?p[0]:"",this._ppvInitialPercentViewed=p[1]?p[1]:"",this._ppvHighestPercentViewed=p[2]?p[2]:"",this._ppvFinalPercentViewed=p[3]?p[3]:"",this._ppvHighestPixelsSeen=p[4]?p[4]:"",this._ppvFoldsAvailable=p[5]?p[5]:"",this._ppvFoldsSeen=p[6]?p[6]:"")}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getPercentPageViewed` 函數會使用以下引數：

* **`pid`** (選項，字串)：等於目前頁面的變量或值。 在 AppMeasurement pageName 變數尚未設定的情況下，預設為 Analytics AppMeasurement `pageName` 變數或 目前的 URL。
* **`ch`** (選用，布林值)：如果您不希望外掛程式考慮頁面初次載入後對頁面大小所做的任何變更，請將此項設為 `false` (或 `0`)。如果省略，此引數會預設為 `true`。Adobe 建議在大多數情況下省略此引數。

呼叫此函數不會傳回任何內容，而是會設定以下變數：

* `window._ppvPreviousPage`：已檢視的上一頁名稱。載入新頁面後才可對目前頁面進行最終捲動測量。
* `window._ppvInitialPercentViewed`：上一個頁面初次載入時的頁面可見百分比。 如果在最初載入頁面時可以看到整個頁面，這個值就是 `100`。
* `window._ppvHighestPercentViewed`：訪客已檢視的上一個頁面的最高比例 (以高度計)。訪客在上一個頁面向下捲動至最遠的點。 如果在最初載入頁面時可以看到整個頁面，這個值就是 `100`。
* `window._ppvFinalPercentViewed`：在訪客前往頁面時可見到上一頁的百分比。 此數值將等於或大於原始檢視百分比，也將等於或小於最高頁面檢視百分比。
* `window._ppvHighestPixelsSeen`：當訪客向下捲動前一個頁面時已查看之總畫素的最高數量 (以高度計)。
* `window._ppvFoldsAvailable`：可在上一個頁面向下捲動的「摺頁」總數。 如果在最初載入頁面時可以看到整個頁面，這個值就是 `1`。
* `window._ppvFoldsSeen`：當訪客向下捲動前一個頁面時達到的「折頁」最高數量。此變數包含「頁面頂端」摺頁。 如果在最初載入頁面時可以看到整個頁面，這個值就是 `1`。

將上述一或多個變數指派給 eVar，便可在報表中查看維度資料。

此外掛程式會建立三個第一方Cookie，在瀏覽器作業階段結束時過期：

* `s_ppv`：儲存每個透過呼叫函式公開的值
* `s_tp`：儲存上一頁的總畫素高度
* `s_ips`：儲存上一頁的初始捲動百分比

## 範例

```js
// 1. Runs the getPercentPageViewed function if the page variable is set
// 2. Sets prop1 to the previous value of the page variable
// 3. Sets prop2 to the intial percent, the highest percent, and the final percent viewed; the number of folds available on the page, and the number of folds viewed ( of the previous page)
if(s.pageName) getPercentPageViewed();
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "initialPercent=" + _ppvInitialPercentViewed + " | highestPercent=" + _ppvHighestPercentViewed + " | finalPercent=" + _ppvFinalPercentViewed + " | foldsAvailable=" + _ppvFoldsAvailable + " | foldsSeen=" + _ppvFoldsSeen;
}

// Given prop5 operates as a page type variable:
// 1. Runs the getPercentPageViewed function if prop5 has a value
// 2. Sets prop1 to the previous value of the page type
// 3. Sets prop2 to the initial percent viewed and the highest percent viewed.
if(s.prop5) getPercentPageViewed(s.prop5);
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "initialPercent=" + _ppvInitialPercentViewed + " | highestPercent=" + _ppvHighestPercentViewed;
}
```

## 版本記錄

### 5.1 (2022 年 12 月 8 日)

* 已新增 `_finalPercentViewed` 解決方案

### 5.0.1 (2021 年 6 月 22 日)

* 修正部分特殊字元會導致外掛程式中斷的問題

### 5.0 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### v4.0 (2019 年 10 月 7 日)

* 新增 `s._ppvFoldsSeen` 和 `s._ppvFoldsAvailable` 解決方案

### v3.01 (2018 年 8 月 13 日)

* 修正一個頁面上有多個 AppMeasurement 物件的頁面問題

### v3.0 (2018 年 4 月 13 日)

* 單點發行 (程式碼經重新編譯且大小較小)
* 外掛程式現在會建立要指派給 Adobe Analytics 變數的變數，而非傳回值
