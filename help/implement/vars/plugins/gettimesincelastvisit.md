---
title: getTimeSinceLastVisit
description: 測量兩次造訪之間經過的時間長度。
feature: Appmeasurement Implementation
exl-id: c5cef219-8a8a-4e57-a372-f2e063325a67
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 72%

---

# Adobe 外掛程式：getTimeSinceLastVisit

{{plug-in}}

`getTimeSinceLastVisit` 外掛程式可用來追蹤訪客從上次造訪到下次回訪您網站經過的時間長度。

## 使用Web SDK擴充功能安裝外掛程式

Adobe提供擴充功能，可讓您搭配Web SDK使用最常用的外掛程式。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下左側的&#x200B;**[!UICONTROL 標籤]**，然後按一下所需的標籤屬性。
1. 按一下左側的&#x200B;**[!UICONTROL 擴充功能]**，然後按一下&#x200B;**[!UICONTROL 目錄]**&#x200B;標籤
1. 尋找並安裝&#x200B;**[!UICONTROL 常用Web SDK外掛程式]**&#x200B;擴充功能。
1. 按一下左側的&#x200B;**[!UICONTROL 資料元素]**，然後按一下所需的資料元素。
1. 使用下列設定來設定所需的資料元素名稱：
   * 擴充功能：常見的Web SDK外掛程式
   * 資料元素： `getTimeSinceLastVisit`
1. 儲存並發佈資料元素的變更。

## 手動實作網站SDK安裝外掛程式

此外掛程式尚不支援在手動實作Web SDK時使用。

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
   * 動作類型：初始化 getTimeSinceLastVisit
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
/* Adobe Consulting Plugin: getTimeSinceLastVisit v2.0 */
 function getTimeSinceLastVisit(){if(arguments&&"-v"===arguments[0])return{plugin:"getTimeSinceLastVisit",version:"2.0"};var h=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof h&&(h.contextData.getTimeSinceLastVisit="2.0");window.formatTime=window.formatTime||function(c,b,d){function f(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var e="";"string"===typeof b&&"d"===b||("string"!==typeof b||!f("h,m,s",b))&&86400<=c?(b=86400,e="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!f("m,s",b))&&3600<=c?(b=3600,e="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!f("s",b))&&60<=c?(b=60,e="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,e="seconds",d=isNaN(d)?.2:b/d);e=Math.round(c*d/b)/d+" "+e;0===e.indexOf("1 ")&&(e=e.substring(0,e.length-1));return e}};window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var f=window.location.hostname,e=window.location.hostname.split(".").length-1;if(f&&!/^[0-9.]+$/.test(f)){e=2<e?e:2;var k=f.lastIndexOf(".");if(0<=k){for(;0<=k&&1<e;)k=f.lastIndexOf(".",k-1),e--;k=0<k?f.substring(k):f}}g=k;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var h=new Date;h.setTime(h.getTime()+6E4*d)}else h=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+h.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),f=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>f?b.length:f)))?c:""};h=new Date;var m=h.getTime(),n=cookieRead("s_tslv")||0,l=Math.round((m-n)/1E3);h.setTime(m+63072E6);cookieWrite("s_tslv",m,h);return n?1800<l||cookieRead("s_inv")?(cookieRead("s_inv")&&(l=cookieRead("s_inv")),cookieWrite("s_inv",l,30),"0"!==l?formatTime(l):"New Visitor"):"":(cookieWrite("s_inv","0",30),"New Visitor")};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getTimeSinceLastVisit` 函數不使用任何引數。 它會傳回自訪客上次造訪網站以來經過的時間長度，並以下列格式分組：

* 自上次造訪後 30 分鐘至 1 小時之間的時間設為最接近的半分鐘基準。例如：`"30.5 minutes"`、`"53 minutes"`
* 一小時至一天之間的時間會捨入至最接近的四分之一小時基準。例如：`"2.25 hours"`、`"7.5 hours"`
* 大於一天的時間會捨入至最接近的天數基準。例如：`"1 day"`、`"3 days"`、`"9 days"`、`"372 days"`
* 如果訪客之前未造訪過，或經過的時間超過兩年，則值會設為 `"New Visitor"`。

>[!NOTE]
>
>此外掛程式只會傳回造訪首次點擊時的值。

此外掛程式會建立名為 `"s_tslv"` 的第一方 Cookie，並設為目前時間的 Unix 時間戳記。閒置兩年後 Cookie 便會到期。

## 範例

```js
// Given a visitor's first visit to the site
// Sets prop1 to "New Visitor"
s.prop1 = getTimeSinceLastVisit();

// 35 minutes later, the same visitor returns
// Sets prop1 to "35 minutes"
s.prop1 = getTimeSinceLastVisit();

// 4 days later, the same visitor returns
// Sets prop1 to "4 days"
s.prop1 = getTimeSinceLastVisit();
```

## 版本記錄

### 2.0 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### 1.0 (2018 年 4 月 16 日)

* 單點發行 (重新編譯程式碼且大小較小)。
* 衍生自 `getDaysSinceLastVisit` 外掛程式的程式碼 (現已過時並重新命名)。
* 現在請使用 `formatTime` 和 `inList` 外掛程式來傳回值。
