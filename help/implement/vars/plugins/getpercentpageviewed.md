---
title: getPercentPageViewed
description: 擷取訪客檢視之頁面的百分比。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobe外掛程式：getPercentPageViewed

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以協助您從Adobe Analytics中獲得更多價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

The `getPercentPageViewed` plug-in measures a visitor&#39;s scroll activity to see how much of a page they view before moving on to another page. 如果您的頁面高度較小或不想測量捲動活動，則不需要此外掛程式。

## 使用Launch自訂程式碼編輯器安裝外掛程式

如果您不想使用外掛程式擴充功能，則可使用自訂程式碼編輯器。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 按一下所要的屬性。
1. 前往標籤 [!UICONTROL Extensions] ，然後按一下Adobe Analytics [!UICONTROL Configure] 擴充功能下的按鈕。
1. 展開accordion [!UICONTROL Configure tracking using custom code] ，以顯示按 [!UICONTROL Open Editor] 鈕。
1. 開啟自訂程式碼編輯器，並將下方提供的外掛程式碼貼入編輯視窗。
1. 儲存變更並發佈至Analytics擴充功能。

## 使用AppMeasurement安裝外掛程式

在Analytics追蹤物件實例化（使用）後，將下列程式碼複製並貼至AppMeasurement檔案中的任 [`s_gi`](../functions/s-gi.md)何位置。 保留您實作中的程式碼注釋和版本號碼，有助於Adobe疑難排解任何潛在問題。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPercentPageViewed v4.0 w/handlePPVevents helper function (Requires p_fo plug-in) */
s.getPercentPageViewed=function(pid,ch){var s=this,a=s.c_r("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];a[0]=s.unescape(a[0]); pid=pid?pid:s.pageName?s.pageName:document.location.href;s.ppvChange="undefined"===typeof ch||!0==ch?!0:!1;if("undefined"=== typeof s.linkType||"o"!==s.linkType)s.ppvID&&s.ppvID===pid||(s.ppvID=pid,s.c_w("s_ppv",""),s.handlePPVevents()), s.p_fo("s_gppvLoad") &&window.addEventListener&&(window.addEventListener("load",s.handlePPVevents,!1),window.addEventListener("click",s.handlePPVevents, !1),window.addEventListener("scroll",s.handlePPVevents,!1)),s._ppvPreviousPage=a[0]?a[0]:"",s._ppvHighestPercentViewed=a[1]?a[1]:"",s._ppvInitialPercentViewed=a[2]?a[2]:"",s._ppvHighestPixelsSeen=a[3]?a[3]:"",s._ppvFoldsSeen=a[4]?a[4]:"",s._ppvFoldsAvailable=a[5]?a[5]:""};

/* Adobe Consulting Plugin: handlePPVevents helper function (for getPercentPageViewed v4.0 Plugin) */
s.handlePPVevents=function(){if("undefined"!==typeof s_c_il){for(var c=0,g=s_c_il.length;c<g;c++)if(s_c_il[c]&& (s_c_il[c].getPercentPageViewed||s_c_il[c].getPreviousPageActivity)){var s=s_c_il[c];break}if(s&&s.ppvID){var f=Math.max (Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight, document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),h= window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight;c=(window.pageYOffset|| window.document.documentElement.scrollTop||window.document.body.scrollTop)+h;g=Math.min(Math.round(c/f*100),100);var k=Math.floor(c/h);h=Math.floor(f/h);var d="";if(!s.c_r("s_tp")||s.unescape(s.c_r("s_ppv").split(",")[0])!==s.ppvID||s.p_fo(s.ppvID) ||1==s.ppvChange&&s.c_r("s_tp")&&f!=s.c_r("s_tp")){(s.unescape(s.c_r("s_ppv").split(",")[0])!==s.ppvID||s.p_fo(s.ppvID+"1"))&&s.c_w("s_ips",c);if(s.c_r("s_tp")&&s.unescape(s.c_r("s_ppv").split(",")[0])===s.ppvID){s.c_r("s_tp");d=s.c_r("s_ppv");var e=-1< d.indexOf(",")?d.split(","):[];d=e[0]?e[0]:"";e=e[3]?e[3]:"";var l=s.c_r("s_ips");d=d+","+Math.round(e/f*100)+","+Math.round(l/ f*100)+","+e+","+k}s.c_w("s_tp",f)}else d=s.c_r("s_ppv");var b=d&&-1<d.indexOf(",")?d.split(",",6):[];f=0<b.length?b[0]: escape(s.ppvID);e=1<b.length?parseInt(b[1]):g;l=2<b.length?parseInt(b[2]):g;var m=3<b.length?parseInt(b[3]):c,n=4<b.length? parseInt(b[4]):k;b=5<b.length?parseInt(b[5]):h;0<g&&(d=f+","+(g>e?g:e)+","+l+","+(c>m?c:m)+","+(k>n?k:n)+","+(h>b?h:b)); s.c_w("s_ppv",d)}}};

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

該方 `getPercentPageViewed` 法使用以下引數：

* **`pid`** （可選，字串）: 頁面型識別碼，可與外掛程式測量提供的百分比建立關聯。  預設為變 `pageName` 數。
* **`ch`** （可選，布林）: 如果您不 `false` 希望外掛程式考慮頁面初次載入後對頁面大小所做的任何變更，請將此設定為(或 `0`)。 如果省略，此引數預設為 `true`。 Adobe建議在大多數情況下省略此引數。

調用此方法不會返回任何結果；而是設定下列變數：

* `s._ppvPreviousPage`:已檢視的上一頁名稱。 當前頁面的最終捲動度量直到載入新頁面後才可用。
* `s._ppvHighestPercentViewed`: 訪客已檢視的上一個頁面的最高比例 (以高度計)。訪客在上一頁捲動至最遠的點數。
* `s._ppvInitialPercentViewed`: 前一個頁面首次載入時的頁面可見比例.
* `s._ppvHighestPixelsSeen`: 當訪客向下捲動前一個頁面時已查看之總畫素的最高數量 (以高度計)。
* `s._ppvFoldsSeen`:當訪客向下捲動上一頁時，「頁面折頁數」達到最高。 此變數包含「頁面頂端」折頁。
* `s._ppvFoldsAvailable`:可在上一頁向下捲動的「頁面折疊」總數。

將一或多個這些變數指派給eVar，以在報表中查看維度資料。

此外掛程式會建立名為的第一方Cookie, `s_ppv` 其中包含上述值。 它會在瀏覽器作業結束時過期。

## 呼叫範例

### 範例#1

下列程式碼……

```js
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed + " + | foldsSeen=" + s._ppvFoldsSeen + " | foldsAvailable=" + s._ppvFoldsAvailable;
}
```

* 判斷是否已設定s.pageName，若已設定，程式碼將執行getPercentPageViewed函式
* 當getPercentPageViewed函式執行時，它將建立上述「傳回」區段中所述的變數
* 如果已成功設定「傳回」變數：
   * 程式碼會將s.prop1設定為s.ppvPreviousPage的值（即s.pageName的上一個值或上一頁）
   * 程式碼也會將s.prop2設定為上一頁的「檢視最高百分比」和上一頁的「檢視初始百分比」，以及訪客到達的折頁數和可用的折頁數

**注意**: 如果首次載入時整個頁面可見，「檢視的最高百分比」和「檢視的初始百分比」維度都會等於100，而「檢視的折頁」和「可用折頁」都會等於1。   當首次載入整個頁面時，不會顯示整個頁面，但訪客在移至下一頁之前從未向下捲動頁面，則「檢視的最高百分比」和「檢視的初始百分比」維度都會等於相同值。

### 範例#2

假設已將 s.prop5 設定為擷取統計「頁面類型」，而不是整個頁面名稱。

下列程式碼會判斷s.prop5是否已設定，若已設定，則會將其值儲存為「上一頁」，以與「檢視的最高百分比」和「檢視的初始百分比」維度建立關聯。  值仍會儲存在s._ppvPreviousPage變數中，但可視為其為上一頁類型，而非上一頁名稱。

```js
if(s.prop5) s.getPercentPageViewed(s.prop5);
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}
```

## 版本記錄

### v4.0（2019年10月7日）

* 新增的 `s._ppvFoldsSeen` 解決方案 `s._ppvFoldsAvailable` 和

### v3.01（2018年8月13日）

* 已修正頁面上具有多個AppMeasurement物件的頁面問題

### v3.0（2018年4月13日）

* 點數發行（重新編譯，程式碼小）
* 外掛程式現在會建立要指派給Adobe Analytics變數的變數，而非傳回值
