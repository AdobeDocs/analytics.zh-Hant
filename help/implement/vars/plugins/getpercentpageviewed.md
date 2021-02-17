---
title: getPercentPageViewed
description: 擷取訪客所檢視的頁面比例。
translation-type: ht
source-git-commit: 69c1daa9dbf3bbf39072cc7104f2dd32fb95eb79
workflow-type: ht
source-wordcount: '781'
ht-degree: 100%

---


# Adobe 外掛程式：getPercentPageViewed

>[!IMPORTANT]
>
>此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`getPercentPageViewed` 外掛程式可測量訪客的捲動活動，以查看訪客在前往其他頁面前所檢視的頁面比例。如果您的頁面高度較小或不想測量捲動活動，就不需要此外掛程式。

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
/* Adobe Consulting Plugin: getPercentPageViewed v4.0 w/handlePPVevents helper function (Requires p_fo plug-in) */
s.getPercentPageViewed=function(pid,ch){var s=this,a=s.c_r("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];a[0]=s.unescape(a[0]); pid=pid?pid:s.pageName?s.pageName:document.location.href;s.ppvChange="undefined"===typeof ch||!0==ch?!0:!1;if("undefined"=== typeof s.linkType||"o"!==s.linkType)s.ppvID&&s.ppvID===pid||(s.ppvID=pid,s.c_w("s_ppv",""),s.handlePPVevents()), s.p_fo("s_gppvLoad") &&window.addEventListener&&(window.addEventListener("load",s.handlePPVevents,!1),window.addEventListener("click",s.handlePPVevents, !1),window.addEventListener("scroll",s.handlePPVevents,!1)),s._ppvPreviousPage=a[0]?a[0]:"",s._ppvHighestPercentViewed=a[1]?a[1]:"",s._ppvInitialPercentViewed=a[2]?a[2]:"",s._ppvHighestPixelsSeen=a[3]?a[3]:"",s._ppvFoldsSeen=a[4]?a[4]:"",s._ppvFoldsAvailable=a[5]?a[5]:""};

/* Adobe Consulting Plugin: handlePPVevents helper function (for getPercentPageViewed v4.0 Plugin) */
s.handlePPVevents=function(){if("undefined"!==typeof s_c_il){for(var c=0,g=s_c_il.length;c<g;c++)if(s_c_il[c]&& (s_c_il[c].getPercentPageViewed||s_c_il[c].getPreviousPageActivity)){var s=s_c_il[c];break}if(s&&s.ppvID){var f=Math.max (Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight, document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),h= window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight;c=(window.pageYOffset|| window.document.documentElement.scrollTop||window.document.body.scrollTop)+h;g=Math.min(Math.round(c/f*100),100);var k=Math.floor(c/h);h=Math.floor(f/h);var d="";if(!s.c_r("s_tp")||s.unescape(s.c_r("s_ppv").split(",")[0])!==s.ppvID||s.p_fo(s.ppvID) ||1==s.ppvChange&&s.c_r("s_tp")&&f!=s.c_r("s_tp")){(s.unescape(s.c_r("s_ppv").split(",")[0])!==s.ppvID||s.p_fo(s.ppvID+"1"))&&s.c_w("s_ips",c);if(s.c_r("s_tp")&&s.unescape(s.c_r("s_ppv").split(",")[0])===s.ppvID){s.c_r("s_tp");d=s.c_r("s_ppv");var e=-1< d.indexOf(",")?d.split(","):[];d=e[0]?e[0]:"";e=e[3]?e[3]:"";var l=s.c_r("s_ips");d=d+","+Math.round(e/f*100)+","+Math.round(l/ f*100)+","+e+","+k}s.c_w("s_tp",f)}else d=s.c_r("s_ppv");var b=d&&-1<d.indexOf(",")?d.split(",",6):[];f=0<b.length?b[0]: escape(s.ppvID);e=1<b.length?parseInt(b[1]):g;l=2<b.length?parseInt(b[2]):g;var m=3<b.length?parseInt(b[3]):c,n=4<b.length? parseInt(b[4]):k;b=5<b.length?parseInt(b[5]):h;0<g&&(d=f+","+(g>e?g:e)+","+l+","+(c>m?c:m)+","+(k>n?k:n)+","+(h>b?h:b)); s.c_w("s_ppv",d)}}};

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
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

### v4.0 (2019 年 10 月 7 日)

* 新增 `s._ppvFoldsSeen` 和 `s._ppvFoldsAvailable` 解決方案

### v3.01 (2018 年 8 月 13 日)

* 修正一個頁面上有多個 AppMeasurement 物件的頁面問題

### v3.0 (2018 年 4 月 13 日)

* 單點發行 (程式碼經重新編譯且大小較小)
* 外掛程式現在會建立要指派給 Adobe Analytics 變數的變數，而非傳回值
