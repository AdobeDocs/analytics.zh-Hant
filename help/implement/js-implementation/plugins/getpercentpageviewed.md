---
description: 測量訪客的捲動活動，以查看訪客在前往其他頁面前所檢視的頁面比例。此外掛程式可讓您判斷使用者平均對您的內容會做多少檢視，以便您根據使用者行為對頁面長度與版面配置進行最佳化。
keywords: Analytics 實施
seo-description: 測量訪客的捲動活動，以查看訪客在前往其他頁面前所檢視的頁面比例。此外掛程式可讓您判斷使用者平均對您的內容會做多少檢視，以便您根據使用者行為對頁面長度與版面配置進行最佳化。
seo-title: getPercentPageViewed
solution: Analytics
subtopic: 外掛程式
title: getPercentPageViewed
topic: 開發人員和實施
uuid: 1751dcdb-699f-4bd1-8bcc-5e62fa24896a
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getPercentPageViewed

getPercentPageViewed外掛程式會測量訪客的捲動活動，以查看訪客在移至另一個頁面之前所檢視的頁面大小。

>[!NOTE]
>如果您的網頁高度較小，且不需要測量訪客向下捲動的程度，則不需要使用getPercentPageViewed外掛程式。此外，如果您只想測量退出頁面上的捲動活動，則無法使用此外掛程式。

## 必備條件

您必須有AppMeasurement和handlyppEvents helper外掛程式，才能執行getPercentPageViewed外掛程式。

## 實施

To implement this plugin, copy and paste the code to anywhere within the **[!UICONTROL Plugins]** section of the [!DNL AppMeasurement] file.

>[!NOTE]
>將程式碼的粗體留言/版本號碼新增至AppMeasurement檔案可協助Adobe Consulting疑難排解任何可能的實施問題。

You can run the `getPercentPageViewed` function as needed within the doPlugins function (see example calls below.)

## 要傳入的引數

| 引數 | 定義 |
|---|---|
| pid(選用、字串) | 與外掛程式測量所提供百分比關聯的頁面識別碼。若未設定pageName變數，則會預設為Analytics pageName變數或URL |
| ch(選用，布林) | 「True」是此引數的建議/預設值。如果您不希望此增效模組在初始載入後(因為SPA程式碼、動態HTML等)對頁面大小進行任何變更，請將此設為「false」。 |

## 傳回

getPercentPageViewed外掛程式不會傳回任何項目。相反地，此外掛程式會設定下列 AppMeasurement 物件中的變數:

* `s._ppvPreviousPage`：檢視上一頁的名稱(因為在新的頁面載入之前無法使用最終度量)。
* `s._ppvHighestPercentViewed`：訪客檢視的上一頁(高度)的最高百分比。換言之，訪客在上一頁向下捲動的最粗點。
* `s._ppvInitialPercentViewed`：上一頁初次載入時顯示的上一頁百分比。
* `s._ppvHighestPixelSeen`：訪客捲動上一頁時所見(高度)的最高像素總數。

## Cookie

The getPercentPageViewed plugin creates a cookie, called `s_ppv`, that is passed from page to page. Cookie的內容包含上述四個變數中插入的值，並在作業結束時過期。

## 呼叫範例

**範例呼叫1**

```
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + "initialPercentViewed="s._ppvInitialPercentViewed;
}  
```

上述程式碼範例：
* 判斷s. pageName是否已設定，此時，程式碼會執行getPercentPageViewed函數。
* `getPercentPageViewed` 函數執行時，會建立上述「返回」一節中所述的變數。
* 如果已成功設定「傳回」變數：

   * The code sets s.prop1 equal to the value of `s._ppvPreviousPag`e (i.e. the previous value of `s.pageName`, or the previous page.)
   * 此程式碼也會設定s. prop等於上一頁的「最高百分比檢視百分比」和上一頁的「初始百分比檢視次數」。

>[!NOTE]
>如果整個頁面第一次載入時顯示，則「已檢視最高百分比」和「檢視的初始百分比」維度將等於100。不過，如果整個頁面在第一次載入時不顯示，但訪客在移至下一頁之前從未向下捲動頁面，則「已檢視最高百分比」和「初始百分比檢視的百分比」將等於相同值。

**範例呼叫2**

假設s. prop已設為擷取已遞延的「頁面類型」，而非整個頁面名稱。

下列程式碼會決定s. prop是否已設定，如果是，將其值儲存為「上一頁」以關聯至「已檢視的最高百分比」和「初始百分比檢視的初始百分比」維度。The value is still stored in the `s._ppvPreviousPage` variable but can be treated as if it were the previous page type instead of the previous page name.

```
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}  
```

## 物件取代

將主要AppMeasurement程式庫物件與「s」以外的名稱實例化時，請變更以下外掛程式程式碼的下列部分：

`s.getPercentPageViewed=function(pid,ch)`

至此：

`[objectname].getPercentPageViewed=function(pid,ch)`

## 部署程式碼

外掛程式區段: 將下列程式碼新增至 `s_code.js` 檔案中標示為 PLUGINS SECTION 的區域中。請勿對此部分的外掛程式程式碼進行任何變更。

```
/******************************************* BEGIN CODE TO DEPLOY *******************************************/ 
/* Adobe Consulting Plugin: getPercentPageViewed v3.01 w/handlePPVevents helper function (Requires AppMeasurement and p_fo plugin) */
s.getPercentPageViewed=function(pid,ch){var s=this,a=s.c_r("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];a[0]=s.unescape(a[0]); 
pid=pid?pid:s.pageName?s.pageName:document.location.href;s.ppvChange=ch?ch:!0;if("undefined"===typeof s.linkType||"o"!==
s.linkType)s.ppvID&&s.ppvID===pid||(s.ppvID=pid,s.c_w("s_ppv",""),s.handlePPVevents()),s.p_fo("s_gppvLoad")&&window
.addEventListener&&(window.addEventListener("load",s.handlePPVevents,!1),window.addEventListener("click",s.handlePPVevents, !1),window.addEventListener("scroll",s.handlePPVevents,!1),window.addEventListener("resize",s.handlePPVevents,!1)),s._ppvPreviousPage
=a[0]?a[0]:"",s._ppvHighestPercentViewed=a[1]?a[1]:"",s._ppvInitialPercentViewed=a[2]?a[2]:"",s._ppvHighestPixelsSeen=a[3]?a[3]:""}; 

/* Adobe Consulting Plugin: handlePPVevents helper function (for getPercentPageViewed v3.01 Plugin) */ 
s.handlePPVevents=function(){if("undefined"!==typeof s_c_il){for(var c=0,d=s_c_il.length;c<d;c++)if(s_c_il[c]&&s_c_il[c].getPercentPageViewed){var a=s_c_il[c];break}if(a&&a.ppvID){var f=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.
body.clientHeight,document.documentElement.clientHeight));c=(window.pageYOffset||window.document.documentElement.scrollTop|
|window.document.body.scrollTop)+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight);d=Math.min(Math.round
(c/f*100),100);var e="";!a.c_r("s_tp")||a.unescape(a.c_r("s_ppv").split(",")[0])!==a.ppvID||1==a.ppvChange&&
a.c_r("s_tp")&&f!= a.c_r("s_tp")?(a.c_w("s_tp",f),a.c_w("s_ppv","")):e=a.c_r("s_ppv");var b=e&&-1<e.indexOf(",")?e.split(",",4):[];f=0<b.length?b[0]:escape(a.ppvID);var g=1<b.length?parseInt(b[1]):d,h=2<b.length?parseInt(b[2]):d;b=3<b.length?parseInt(b[3]):c;0<d&&(e=f+","+(d>g?d:g)+","+h+","+(c>b?c:b));a.c_w("s_ppv",e)}}}; 

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 (Requires AppMeasurement) */ 
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0}; 
/******************************************** END CODE TO DEPLOY ********************************************/
```
