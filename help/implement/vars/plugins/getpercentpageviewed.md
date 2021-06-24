---
title: getPercentPageViewed
description: 擷取訪客所檢視的頁面比例。
exl-id: 7a842cf0-f8cb-45a9-910e-5793849bcfb8
source-git-commit: 633ba0b9a3fe40bfd1b36820949810c631597397
workflow-type: tm+mt
source-wordcount: '906'
ht-degree: 98%

---

# Adobe 外掛程式：getPercentPageViewed

>[!IMPORTANT]
>
>此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`getPercentPageViewed` 外掛程式可測量訪客的捲動活動，以查看訪客在前往其他頁面前所檢視的頁面比例。如果您的頁面高度較小或不想測量捲動活動，就不需要此外掛程式。

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
   * 動作類型：初始化 getPercentPageViewed
1. 儲存並發佈規則的變更。

## 使用 Launch 自訂程式碼編輯器安裝外掛程式

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
1. 按一下所需的屬性。
1. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 擴充功能底下的[!UICONTROL 「設定」]按鈕。
1. 展開[!UICONTROL 使用自訂程式碼設定追蹤]摺疊式功能表，便會顯示[!UICONTROL 「開啟編輯器」]按鈕。
1. 開啟自訂程式碼編輯器，並將下方提供的外掛程式程式碼貼入編輯視窗中。
1. 儲存並發佈 Analytics 擴充功能的變更。

## 使用 AppMeasurement 安裝外掛程式

Analytics 追蹤物件實例化 (使用 [`s_gi`](../functions/s-gi.md)) 後，將下列程式碼複製並貼到 AppMeasurement 檔案中的任何位置。保留您實施中的程式碼備註和版本號碼，有助於 Adobe 疑難排解任何可能問題。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPercentPageViewed v5.0.1 */
function getPercentPageViewed(pid,ch){var n=pid,r=ch;function p(){if(window.ppvID){var a=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),b=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,d=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+b,f=Math.min(Math.round(d/a*100),100),l=Math.floor(d/b);b=Math.floor(a/b);var c="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||1==window.ppvChange&&window.cookieRead("s_tp")&&a!=window.cookieRead("s_tp")){(decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",d);if(window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");c=window.cookieRead("s_ppv");var h=-1<c.indexOf(",")?c.split(","):[];c=h[0]?h[0]:"";h=h[3]?h[3]:"";var q=window.cookieRead("s_ips");c=c+","+Math.round(h/a*100)+","+Math.round(q/a*100)+","+h+","+l}window.cookieWrite("s_tp",a)}else c=window.cookieRead("s_ppv");var k=c&&-1<c.indexOf(",")?c.split(",",6):[];a=0<k.length?k[0]:encodeURIComponent(window.ppvID);h=1<k.length?parseInt(k[1]):f;q=2<k.length?parseInt(k[2]):f;var t=3<k.length?parseInt(k[3]):d,u=4<k.length?parseInt(k[4]):l;k=5<k.length?parseInt(k[5]):b;0<f&&(c=a+","+(f>h?f:h)+","+q+","+(d>t?d:t)+","+(l>u?l:u)+","+(b>k?b:k));window.cookieWrite("s_ppv",c)}}if("-v"===n)return{plugin:"getPercentPageViewed",version:"5.0.1"};var m=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof m&&(m.contextData.getPercentPageViewed="5.0.1");window.pageName="undefined"!==typeof m&&m.pageName||"";window.cookieWrite=window.cookieWrite||function(a,b,d){if("string"===typeof a){var f=window.location.hostname,l=window.location.hostname.split(".").length-1;if(f&&!/^[0-9.]+$/.test(f)){l=2<l?l:2;var c=f.lastIndexOf(".");if(0<=c){for(;0<=c&&1<l;)c=f.lastIndexOf(".",c-1),l--;c=0<c?f.substring(c):f}}g=c;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var h=new Date;h.setTime(h.getTime()+6E4*d)}else h=d;return a&&(document.cookie=encodeURIComponent(a)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+h.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(a)===b:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var b=" "+document.cookie,d=b.indexOf(" "+a+"="),f=0>d?d:b.indexOf(";",d);return(a=0>d?"":decodeURIComponent(b.substring(d+2+a.length,0>f?b.length:f)))?a:""};window.p_fo=window.p_fo||function(a){window.__fo||(window.__fo={});if(window.__fo[a])return!1;window.__fo[a]={};return!0};var e=window.cookieRead("s_ppv");e=-1<e.indexOf(",")?e.split(","):[];n=n?n:window.pageName?window.pageName:document.location.href;e[0]=decodeURIComponent(e[0]);window.ppvChange="undefined"===typeof r||1==r?!0:!1;"undefined"!==typeof m&&m.linkType&&"o"===m.linkType||(window.ppvID&&window.ppvID===n||(window.ppvID=n,window.cookieWrite("s_ppv",""),p()),window.p_fo("s_gppvLoad")&&window.addEventListener&&(window.addEventListener("load",p,!1),window.addEventListener("click",p,!1),window.addEventListener("scroll",p,!1)),this._ppvPreviousPage=e[0]?e[0]:"",this._ppvHighestPercentViewed=e[1]?e[1]:"",this._ppvInitialPercentViewed=e[2]?e[2]:"",this._ppvHighestPixelsSeen=e[3]?e[3]:"",this._ppvFoldsSeen=e[4]?e[4]:"",this._ppvFoldsAvailable=e[5]?e[5]:"")};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getPercentPageViewed` 方法使用以下引數：

* **`pid`** (選用，字串)：頁面型識別碼，可與外掛程式測量結果提供的比例建立關聯。預設為 `pageName` 變數。
* **`ch`** (選用，布林值)：如果您不希望外掛程式考慮頁面初次載入後對頁面大小所做的任何變更，請將此項設為 `false` (或 `0`)。如果省略，此引數會預設為 `true`。Adobe 建議在大多數情況下省略此引數。

呼叫此方法不會傳回任何結果，而是會設定下列變數：

* `s._ppvPreviousPage`：已檢視的上一頁名稱。載入新頁面後才可對目前頁面進行最終捲動測量。
* `s._ppvHighestPercentViewed`：訪客已檢視的上一個頁面的最高比例 (以高度計)。訪客在上一個頁面向下捲動至最遠的點。
* `s._ppvInitialPercentViewed`：前一個頁面首次載入時的頁面可見比例。
* `s._ppvHighestPixelsSeen`：當訪客向下捲動前一個頁面時已查看之總畫素的最高數量 (以高度計)。
* `s._ppvFoldsSeen`：當訪客向下捲動前一個頁面時達到的「折頁」最高數量。此變數包含「頁面頂端」折頁。
* `s._ppvFoldsAvailable`：可在上一個頁面向下捲動的「折頁」總數。

將上述一或多個變數指派給 eVar，便可在報表中查看維度資料。

此外掛程式會建立包含上述值且名為 `s_ppv` 的第一方 Cookie。它會在瀏覽器作業階段結束時到期。

## 呼叫範例

### 範例 #1

下列程式碼...

```js
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed + " + | foldsSeen=" + s._ppvFoldsSeen + " | foldsAvailable=" + s._ppvFoldsAvailable;
}
```

* 判斷是否已設定 s.pageName；若已設定，程式碼將執行 getPercentPageViewed 函數
* getPercentPageViewed 函數執行時，會建立上文「傳回」一節中所述的變數
* 若已成功設定「傳回」變數：
   * 程式碼會將 s.prop1 設為等於 s._ppvPreviousPage 的值 (亦即 s.pageName 的上一個值或上一頁)。
   * 程式碼也會將 s.prop2 設為上一頁的「最高檢視比例」和上一頁的「初始檢視比例」，以及訪客達到的折頁數和可用的折頁數

**注意**：如果首次載入時會顯示整個頁面，則「最高檢視比例」和「初始檢視比例」維度都會等於 100，而「已見折頁」和「可用折頁」都會等於 1。如果初次載入時不會顯示整個頁面，但訪客在移動到下一個頁面前未曾向下捲動頁面，則「最高檢視比例」和「初始檢視比例」維度會等於同一個值。

### 範例 #2

假設已將 s.prop5 設定為擷取統計「頁面類型」，而不是整個頁面名稱。

下列程式碼會判斷是否已設定 s.prop5；若已設定，則會將其值儲存為「previous page」，與「最高檢視比例」和「初始檢視比例」維度建立關聯。此值仍會儲存在 s._ppvPreviousPage 變數中，但可將其視為上一個頁面類型，而不是上一個頁面名稱。

```js
if(s.prop5) s.getPercentPageViewed(s.prop5);
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}
```

## 版本記錄

### 5.0.1（2021年6月22日）

* 修正某些特殊字元會導致外掛程式中斷的問題

### 5.0 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### v4.0 (2019 年 10 月 7 日)

* 新增 `s._ppvFoldsSeen` 和 `s._ppvFoldsAvailable` 解決方案

### v3.01 (2018 年 8 月 13 日)

* 修正一個頁面上有多個 AppMeasurement 物件的頁面問題

### v3.0 (2018 年 4 月 13 日)

* 單點發行 (程式碼經重新編譯且大小較小)
* 外掛程式現在會建立要指派給 Adobe Analytics 變數的變數，而非傳回值
