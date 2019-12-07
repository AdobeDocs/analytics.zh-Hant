---
description: 測量訪客的捲動活動，以查看訪客在前往其他頁面前所檢視的頁面比例。此外掛程式可讓您判斷使用者平均對您的內容會做多少檢視，以便您根據使用者行為對頁面長度與版面配置進行最佳化。
keywords: Analytics Implementation
subtopic: Plug-ins
title: getPercentPageViewed
topic: Developer and implementation
uuid: 1751dcdb-699f-4bd1-8bcb-5e62fa24896a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getPercentPageViewed

getPercentPageViewed 外掛程式會測量訪客的捲動活動，以查看訪客在前往其他頁面前已檢視的頁面比例。

>[!NOTE]
>如果您的網頁高度很短，則不需要使用 getPercentPageViewed 外掛程式，而且也不需要測量訪客向下捲動到多遠的位置。此外，若只要測量退出頁面上的捲動活動，則無法使用此外掛程式。

## 必備條件

您必須有 AppMeasurement 和 handlePPVevents 輔助外掛程式，才能執行 getPercentPageViewed 外掛程式。

## 實施

若要實作此外掛程式，請將程式碼複製並貼到 [!DNL AppMeasurement] 檔案的&#x200B;**[!UICONTROL 外掛程式]**&#x200B;區段內的任何位置。

>[!NOTE]
>您可以將程式碼的粗體格式備註/版本號碼新增至 AppMeasurement 檔案，這有助於 Adobe 諮詢針對任何可能的實施問題進行疑難排解。

您可以視需要在 doPlugins 函數內執行 `getPercentPageViewed` 函數 (請參閱下列呼叫範例)。

## 要傳入的引數

| 引數 | 定義 |
|---|---|
| pid (選用，字串) | 與外掛程式測量所提供的比例關聯的頁面識別碼。在 pageName 變數尚未設定的情況下，此預設為 Analytics pageName 變數或 URL |
| ch (選用，布林值) | 此引數的建議/預設值為「True」。如果您不希望此外掛程式在頁面初始載入 (由於 SPA 程式碼、動態 HTML 等) 後，將頁面大小的任一變更納入計算，則請將此變數設為「false」。 |

## 傳回

getPercentPageViewed 外掛程式不會傳回任何項目。相反地，此外掛程式會設定下列 AppMeasurement 物件中的變數:

* `s._ppvPreviousPage`: 上一個已檢視頁面的名稱 (因為最終測量要等到新頁面載入後才能取得)。
* `s._ppvHighestPercentViewed`: 訪客已檢視的上一個頁面的最高比例 (以高度計)。換句話說，就是訪客在上一個頁面向下捲動最遠的點。
* `s._ppvInitialPercentViewed`: 前一個頁面首次載入時的頁面可見比例。
* `s._ppvHighestPixelSeen`: 當訪客向下捲動前一個頁面時已查看之總畫素的最高數量 (以高度計)。

## Cookie

getPercentPageViewed 外掛程式會建立在不同頁面間傳遞的 Cookie (稱為 `s_ppv`)。Cookie 內容包含在上述四個變數中插入的值，並且會在工作階段結束時過期。

## 呼叫範例

**呼叫範例 1**

```
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + "initialPercentViewed="s._ppvInitialPercentViewed;
}  
```

以上程式碼範例:
* 判斷是否已設定 s.pageName；若已設定，程式碼將執行 getPercentPageViewed 函數。
* 當 `getPercentPageViewed` 函數執行時，會建立以上「傳回」一節中所述的變數。
* 若已成功設定「傳回」變數:

   * 程式碼會將 s.prop1 設為等於 `s._ppvPreviousPag`e 的值 (亦即 `s.pageName` 的上一個值或上一頁)。
   * 程式碼也會將 s.prop2 設為等於上一頁的最高檢視比例，以及上一頁的初始檢視比例。

>[!NOTE]
>如果能初次載入時顯示整個頁面，則最高檢視比例和初始檢視比例維度都會等於 100。不過，如果初次載入時無法顯示整個頁面，但訪客在移動到下一個頁面前未曾向下捲動頁面，則最高檢視比例和初始檢視比例維度都會等於同一個值。

**呼叫範例 2**

假設已將 s.prop5 設定為擷取統計「頁面類型」，而不是整個頁面名稱。

下列程式碼會判斷是否已設定 s.prop5；若已設定，則會將其值儲存為「上一頁」，以與高檢視比例和初始檢視比例維度相關。此值仍會儲存在 `s._ppvPreviousPage` 變數中，但可將其視為上一個頁面類型，而不是上一個頁面名稱。

```
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}  
```

## S 物件取代

具現化含有「s」以外的名稱的主要 AppMeasurement 程式庫物件時，請將以下部分外掛程式的程式碼從這個:

`s.getPercentPageViewed=function(pid,ch)`

變更為這個:

`[objectname].getPercentPageViewed=function(pid,ch)`

## 要部署的程式碼

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
body.clientHeight,document.documentElement.clientHeight));c=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight);d=Math.min(Math.round
(c/f*100),100);var e="";!a.c_r("s_tp")||a.unescape(a.c_r("s_ppv").split(",")[0])!==a.ppvID||1==a.ppvChange&&
a.c_r("s_tp")&&f!= a.c_r("s_tp")?(a.c_w("s_tp",f),a.c_w("s_ppv","")):e=a.c_r("s_ppv");var b=e&&-1<e.indexOf(",")?e.split(",",4):[];f=0<b.length?b[0]:escape(a.ppvID);var g=1<b.length?parseInt(b[1]):d,h=2<b.length?parseInt(b[2]):d;b=3<b.length?parseInt(b[3]):c;0<d&&(e=f+","+(d>g?d:g)+","+h+","+(c>b?c:b));a.c_w("s_ppv",e)}}}; 

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 (Requires AppMeasurement) */ 
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0}; 
/******************************************** END CODE TO DEPLOY ********************************************/
```
