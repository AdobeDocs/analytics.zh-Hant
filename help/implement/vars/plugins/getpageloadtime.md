---
title: getPageLoadTime
description: 追蹤頁面載入所需的時間。
exl-id: 9bf0e26b-f1af-48a6-900a-712f7e588d37
translation-type: ht
source-git-commit: c814c023fe909b5e78d6dd46de8c27213a4d92be
workflow-type: ht
source-wordcount: '580'
ht-degree: 100%

---

# Adobe 外掛程式：getPageLoadTime

>[!IMPORTANT]
>
>此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`getPageLoadTime` 外掛程式使用 JavaScript 效能物件，可讓您測量頁面完全載入所花的時間。如果您想要測量頁面載入所需的時間，Adobe 建議使用此外掛程式。

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
   * 動作類型：初始化 getPageLoadTime
1. 儲存並發佈規則的變更。

## 使用 Launch 自訂程式碼編輯器安裝外掛程式

如果您不想使用外掛程式擴充功能，可以使用自訂程式碼編輯器。

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
/* Adobe Consulting Plugin: getPageLoadTime v2.0.1 with performanceWriteFull, performanceWritePart, performanceCheck, and performanceRead helper functions (Requires AppMeasurement and the p_fo plugin) */
function getPageLoadTime(){function l(){var a=performance.timing;if(0<a.loadEventEnd&&(clearInterval(window.pi),""===window.cookieRead("s_plt"))){var b=window,d=b.cookieWrite;var c=a.loadEventEnd;var f=a.navigationStart;c=0<=c&&0<=f?6E4>c-f&&0<=c-f?parseFloat((c-f)/1E3).toFixed(2):60:void 0;d.call(b,"s_plt",c);window.cookieWrite("s_pltp",window.pageName)}window.ptc=a.loadEventEnd}if(arguments&&"-v"===arguments[0])return{plugin:"getPageLoadTime",version:"2.0.1"};var e=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof e&&(e.contextData.getPageLoadTime="2.0.1");window.pageName="undefined"!==typeof e&&e.pageName||"";window.cookieWrite=window.cookieWrite||function(a,b,d){if("string"===typeof a){var c=window.location.hostname,f=window.location.hostname.split(".").length-1;if(c&&!/^[0-9.]+$/.test(c)){f=2<f?f:2;var h=c.lastIndexOf(".");if(0<=h){for(;0<=h&&1<f;)h=c.lastIndexOf(".",h-1),f--;h=0<h?c.substring(h):c}}g=h;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var k=new Date;k.setTime(k.getTime()+6E4*d)}else k=d;return a&&(document.cookie=encodeURIComponent(a)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+k.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(a)===b:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var b=" "+document.cookie,d=b.indexOf(" "+a+"="),c=0>d?d:b.indexOf(";",d);return(a=0>d?"":decodeURIComponent(b.substring(d+2+a.length,0>c?b.length:c)))?a:""};window.p_fo=window.p_fo||function(a){window.__fo||(window.__fo={});if(window.__fo[a])return!1;window.__fo[a]={};return!0};"undefined"!==typeof performance&&p_fo("performance")&&((e=performance,e.clearResourceTimings(),""!==window.cookieRead("s_plt")&&(0<e.timing.loadEventEnd&&clearInterval(window.pi),this._pltLoadTime=window.cookieRead("s_plt"),this._pltPreviousPage=window.cookieRead("s_pltp"),window.cookieWrite("s_plt",""),window.cookieWrite("s_pltp","")),0===e.timing.loadEventEnd)?window.pi=setInterval(function(){l()},250):0<e.timing.loadEventEnd&&(window.ptc?window.ptc===e.timing.loadEventEnd&&1===e.getEntries().length&&(window.pwp=setInterval(function(){var a=performance;0<a.getEntries().length&&(window.ppfe===a.getEntries().length?clearInterval(window.pwp):window.ppfe=a.getEntries().length);""===window.cookieRead("s_plt")&&(window.cookieWrite("s_plt",((a.getEntries()[a.getEntries().length-1].responseEnd-a.getEntries()[0].startTime)/1E3).toFixed(2)),window.cookieWrite("s_pltp",window.pageName))},500)):l()))};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getPageLoadTime` 方法不使用任何引數。呼叫此方法時，它不會傳回任何內容。而是會設定下列變數：

* `s._pltPreviousPage`：上一頁，讓您可將載入時間與上一頁建立關聯
* `s._pltLoadTime`：上一頁載入所花費的秒數

getPageLoadTime 外掛程式會建立兩個第一方 Cookie：

* `s_plt`：上一頁載入所花費的秒數。瀏覽器作業階段結束時會到期。
* `s_pltp` `s.pageName` 變數的值，如先前 Adobe Analytics 影像要求中所記錄。瀏覽器作業階段結束時會到期。

## 呼叫範例

### 範例 #1

執行以下程式碼...

```js
if(s.pageName) s.getPageLoadTime();
if(s._pltPreviousPage)
{
  s.prop10 = s._pltLoadTime;
  s.prop11 = s._pltPreviousPage
  s.eVar10 = prop11;
  s.events = "event100=" + s._pltLoadTime;
}
```

...將執行下列作業：

* 設定 s.pageName 時執行 getPageLoadTime 外掛程式
* 將 s.prop10 設為等於上一頁的載入時間
* 將 s.prop11 和 s.eVar10 設為等於上一頁的名稱 (如 s.pageName 中所記錄)
* 將 event100 (自訂數值事件) 設為等於上一頁的載入時間。在此情況下，使用自訂事件可讓您取得上一頁所有頁面載入的總時間量 (來自所有訪客/造訪)，進而使用計算量度來取得每個頁面的平均頁面載入時間

## 版本記錄

### 2.0.1 (2021 年 3 月 26 日)

* 已修復外掛程式未在 S 物件上正確設定值的問題。

### 2.0 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### 1.0 (2018 年 5 月 22 日)

* 首次發行。
