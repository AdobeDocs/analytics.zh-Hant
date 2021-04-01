---
title: getTimeToComplete
description: 測量完成任務所花費的時間。
translation-type: ht
source-git-commit: 37a3a44053260d9cdb2a3797e07f6d34592abc1f
workflow-type: ht
source-wordcount: '762'
ht-degree: 100%

---


# Adobe 外掛程式：getTimeToComplete

>[!IMPORTANT]
>
>此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`getTimeToComplete` 外掛程式會追蹤使用者在網站上完成程序所花的時間。「時鐘」從呼叫 `start` 動作時開始，在呼叫 `stop` 動作時結束。如果網站上有工作流程需要一些時間才能完成，而且您想瞭解訪客完成該工作流程所花的時間，Adobe 建議您使用此外掛程式。如果您網站上的工作流程耗時較短 (少於 3 秒)，就不需要使用此外掛程式，因為精細度只會降至完整秒。

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
   * 動作類型：初始化 getTimeToComplete
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
/* Adobe Consulting Plugin: getTimeToComplete v4.0 */
function getTimeToComplete(sos,cn,exp,tp){var f=sos,m=cn,l=exp,e=tp;if("-v"===f)return{plugin:"getTimeToComplete",version:"4.0"};var k=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof k&&(k.contextData.getTimeToComplete="4.0");window.formatTime=window.formatTime||function(c,b,d){function e(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var h="";"string"===typeof b&&"d"===b||("string"!==typeof b||!e("h,m,s",b))&&86400<=c?(b=86400,h="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!e("m,s",b))&&3600<=c?(b=3600,h="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!e("s",b))&&60<=c?(b=60,h="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,h="seconds",d=isNaN(d)?.2:b/d);h=Math.round(c*d/b)/d+" "+h;0===h.indexOf("1 ")&&(h=h.substring(0,h.length-1));return h}};window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var e=window.location.hostname,h=window.location.hostname.split(".").length-1;if(e&&!/^[0-9.]+$/.test(e)){h=2<h?h:2;var f=e.lastIndexOf(".");if(0<=f){for(;0<=f&&1<h;)f=e.lastIndexOf(".",f-1),h--;f=0<f?e.substring(f):e}}g=f;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var k=new Date;k.setTime(k.getTime()+6E4*d)}else k=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+k.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),e=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>e?b.length:e)))?c:""};f=f?f.toLowerCase():"start";if("stop"===f||"start"===f){m=m?m:"s_gttc";e?e="d"===e?864E5:"h"===e?36E5:"s"===e?1E3:6E4:(l=30,e=6E4);l=isNaN(l)?30:l;l*=e;k=cookieRead(m);e=new Date;if("stop"===f&&k)return l=Math.round((e.getTime()-k)/1E3),cookieWrite(m,"",0),formatTime(l);"start"!==f||k?k&&Number(k)<e.getTime()+18E5&&cookieWrite(m,k,30):(f=String(e.getTime()),e.setTime(e.getTime()+l),cookieWrite(m,f,e))}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getTimeToComplete` 方法使用以下引數：

* **`sos`** (選用，字串)：要啟動計時器時請設為 `"start"`。要停止計時器時設為 `"stop"`。預設為 `"start"`。
* **`cn`** (選用，字串)：儲存開始時間的 Cookie 名稱。預設為 `"s_gttc"`。
* **`exp`** (選用，整數)：Cookie (和計時器) 到期的天數。預設為 `0`，代表瀏覽器作業階段結束。

呼叫此方法會傳回一個字串，其中包含 `"start"` 和 `"stop"` 動作之間所花費的天數、小時數、分鐘數和/或秒數。

## 呼叫範例

### 範例 #1

使用這些呼叫可判斷訪客何時開始結帳程序，以及何時進行購買。

訪客開始結帳時啟動計時器：

```js
if(s.events.indexOf("scCheckout") > -1) s.getTimeToComplete("start");
```

訪客進行購買時停止計時器，並將 prop1 設為停止與開始之間的時間差：

```js
if(s.events.indexOf("purchase") > -1) s.prop1 = s.getTimeToComplete("stop");
```

s.prop1 會擷取完成購買程序所需的時間長度

### 範例 #2

如果您想要同時執行多個計時器 (以測量不同的程序)，則需要手動設定 cn cookie 引數。例如，如果您想要測量完成購買所需的時間長度，應設定下列程式碼...

```javascript
if(s.inList(s.events, "scCheckout")) s.getTimeToComplete("start", "gttcpurchase");
if(s.inList(s.events, "purchase")) s.prop1 = s.getTimeToComplete("start", "gttcpurchase");
```

...但是，如果您也想 (同時) 測量填寫註冊表單所需的時間長度，也可執行下列程式碼：

```js
if(s.inList(s.events, "event1")) s.getTimeToComplete("start", "gttcregister", 7);
if(s.inList(s.events, "event2")) s.prop2 = s.getTimeToComplete("stop", "gttcregister", 7);
```

在第二個範例中，event1 是用來擷取註冊程序 (基於任何理由，最多可能需要 7 天才能完成) 的開始，而 event2 是用來擷取註冊程序的完成。s.prop2 會擷取完成註冊程序所需的時間長度

## 版本記錄

### 4.0 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### 3.1 (2019 年 9 月 30 日)

* 新增第一個引數中需要「start」或「stop」值的邏輯。傳入的其他所有值都會讓外掛程式停止執行。
* 將 `inList 2.0` 外掛程式更新至 `inList 2.1`。

### 3.0 (2018 年 8 月 23 日)

* 將 `formatTime v1.0` 外掛程式更新至 `formatTime v1.1`。

### 3.0 (2018 年 4 月 17 日)

* 單點發行 (重新編譯，程式碼大小較小)。
* 微幅錯誤修正。

### 2.0 2016 年 6 月 21 日)

* 消除對 `p_fo` 外掛程式的相依性。
* 新增與 H-Code 和 AppMeasurement 的相容性。
* 新增主控台記錄。
