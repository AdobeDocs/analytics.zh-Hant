---
title: getVisitNum
description: 追蹤訪客的目前造訪次數。
feature: Appmeasurement Implementation
exl-id: 05b3f57c-7268-4585-a01e-583f462ff8df
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 76%

---

# Adobe 外掛程式：getVisitNum

{{plug-in}}

`getVisitNum` 外掛程式會傳回在指定天數內造訪過網站的所有訪客造訪次數。Analysis Workspace 提供的「造訪次數」維度具有類似功能。如果您想更深入控製造訪次數的增加方式，Adobe 建議使用此外掛程式。如果 Analysis Workspace 中的內建「造訪次數」維度足以滿足您的報表需求，就不需要此外掛程式。

## 使用Web SDK擴充功能安裝外掛程式

Adobe提供擴充功能，可讓您搭配Web SDK使用最常用的外掛程式。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下左側的&#x200B;**[!UICONTROL 標籤]**，然後按一下所需的標籤屬性。
1. 按一下左側的&#x200B;**[!UICONTROL 擴充功能]**，然後按一下&#x200B;**[!UICONTROL 目錄]**&#x200B;標籤
1. 尋找並安裝&#x200B;**[!UICONTROL 常用Web SDK外掛程式]**&#x200B;擴充功能。
1. 按一下左側的&#x200B;**[!UICONTROL 資料元素]**，然後按一下所需的資料元素。
1. 使用下列設定來設定所需的資料元素名稱：
   * 擴充功能：常見的Web SDK外掛程式
   * 資料元素： `getVisitNum`
1. 在右側設定所要的引數。
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
   * 動作類型：初始化 getVisitNum
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
/* Adobe Consulting Plugin: getVisitNum v4.2 */
function getVisitNum(rp,erp){var a=rp,l=erp;function m(c){return isNaN(c)?!1:(parseFloat(c)|0)===parseFloat(c)}function n(c){var b=new Date,e=isNaN(c)?0:Math.floor(c);b.setHours(23);b.setMinutes(59);b.setSeconds(59);"w"===c&&(e=6-b.getDay());if("m"===c){e=b.getMonth()+1;var a=b.getFullYear();e=(new Date(a?a:1970,e?e:1,0)).getDate()-b.getDate()}b.setDate(b.getDate()+e);"y"===c&&(b.setMonth(11),b.setDate(31));return b}if("-v"===a)return{plugin:"getVisitNum",version:"4.2"};var f=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof f&&(f.contextData.getVisitNum="4.2");window.cookieWrite=window.cookieWrite||function(c,b,e){if("string"===typeof c){var a=window.location.hostname,d=window.location.hostname.split(".").length-1;if(a&&!/^[0-9.]+$/.test(a)){d=2<d?d:2;var h=a.lastIndexOf(".");if(0<=h){for(;0<=h&&1<d;)h=a.lastIndexOf(".",h-1),d--;h=0<h?a.substring(h):a}}g=h;b="undefined"!==typeof b?""+b:"";if(e||""===b)if(""===b&&(e=-60),"number"===typeof e){var f=new Date;f.setTime(f.getTime()+6E4*e)}else f=e;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(e?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:365;l="undefined"!==typeof l?!!l:m(a)?!0:!1;var p=(new Date).getTime();f=n(a);if(window.cookieRead("s_vnc"+a))var d=window.cookieRead("s_vnc"+a).split("&vn="),k=d[1];if(window.cookieRead("s_ivc"))return k?(window.cookieWrite("s_ivc",!0,30),k):"unknown visit number";if("undefined"!==typeof k)return k++,d=l&&m(a)?p+864E5*a:d[0],f.setTime(d),window.cookieWrite("s_vnc"+a,d+"&vn="+k,f),window.cookieWrite("s_ivc",!0,30),k;d=m(a)?p+864E5*a:n(a).getTime();window.cookieWrite("s_vnc"+a,d+"&vn=1",f);window.cookieWrite("s_ivc",!0,30);return"1"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getVisitNum` 函數會使用以下引數：

* **`rp`** (選用，整數或字串)：造訪次數計數器重設前的天數。若未設定，則預設為 `365`。
   * 此引數為`"w"`時，計數器會在當週結束時（本週六晚上11:59）重設
   * 此引數為 `"m"` 時，計數器會在當月結束時 (本月的最後一天) 重設
   * 此引數為 `"y"` 時，計數器會在當年結束時 (12 月 31 日) 重設
* **`erp`** (選用，布林值)：`rp` 引數為數字時，此引數會決定是否應延長造訪次數的期限。若設為 `true`，您網站的後續點擊會重設造訪次數計數器。若設為 `false`，造訪次數計數器重設時，您網站的後續點擊不會延長。預設為 `true`。`rp` 引數為字串時，此引數無效。

訪客閒置 30 分鐘後再返回您的網站時，造訪次數會增加。呼叫此函數會傳回一個整數，該整數代表訪客目前的造訪次數。

此外掛程式會設定名為 `"s_vnc[LENGTH]"` 的第一方 Cookie，其中的 `[LENGTH]` 是傳入 `rp` 引數的值。例如 `"s_vncw"`、`"s_vncm"` 或 `"s_vnc365"`。Cookie 的值是 Unix 時間戳記的組合，代表造訪計數器重設的時間，例如當週結束時、當月結束時或閒置 365 天後。其中也包含目前的造訪次數。此外掛程式會設定另一個名為 `"s_ivc"` 的 Cookie，該 Cookie 設為 `true` 且閒置 30 分鐘後會到期。

## 範例

```js
// Sets prop4 to the visit number, storing the value in a cookie that expires in 365 days
// The cookie value is reset only if there are 365+ days of inactivity or the visitor clears their cookies.
s.prop4 = getVisitNum();

// Sets eVar4 to the visit number, storing the value in a cookie that expires in 200 days
// The cookie value is reset only if there are 200+ days of inactivity or the visitor clears their cookies.
s.eVar4 = getVisitNum(200);

// Sets eVar16 to the visit number, storing the value in a cookie that expires in 90 days.
// The cookie value is reset after 90 days, regardless of how many visits that happen in those 90 days.
s.eVar16 = getVisitNum(90,false);

// Track the visit number unique to the week, month, and year, all in separate variables
// The plug-in automatically creates three separate cookies to track these values
s.prop1 = getVisitNum("w");
s.prop2 = getVisitNum("m");
s.prop3 = getVisitNum("y");
```

## 版本記錄

### 4.2 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### 4.11 (2019 年 9 月 30 日)

* 修正 `erp` 引數明確設為 `false` 的問題。

### 4.1 (2018 年 5 月 21 日)

* 將 `endOfDatePeriod` 外掛程式更新為 v1.1。

### 4.0 (2018 年 4 月 17 日)

* 單點發行 (重新編譯，程式碼大小較小)。
* 移除 Cookie 引數，因為外掛程式現在會根據 `rp` 引數以動態方式產生 Cookie)

### 3.0 (2016 年 6 月 5 日)

* 全面檢修
* 結合各種 `getVisitNum` 外掛程式版本中可用的所有舊版解決方案。
