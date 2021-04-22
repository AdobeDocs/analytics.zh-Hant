---
title: getVisitDuration
description: 追蹤訪客目前為止在網站上逗留的時間。
exl-id: 5299caa8-1e47-40b0-a8f4-422590f33ee4
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '585'
ht-degree: 100%

---

# Adobe 外掛程式：getVisitDuration

>[!IMPORTANT]
>
>此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`getVisitDuration` 外掛程式會追蹤訪客截至該時間點為止在網站上逗留的時間長度，以分鐘為單位。如果您想要追蹤網站上截至該時間點的累計時間，或追蹤執行活動所花費的時間，Adobe 建議使用此外掛程式。此外掛程式不會追蹤事件之間的時間長度；如果需要此功能，請使 [`getTimeBetweenEvents`](gettimebetweenevents.md) 用外掛程式。

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
   * 動作類型：初始化 getVisitDuration
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
/* Adobe Consulting Plugin: getVisitDuration v2.1 */
function getVisitDuration(){if(arguments&&"-v"===arguments[0])return{plugin:"getVisitDuration",version:"2.1"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof d&&(d.contextData.getVisitDuration="2.1");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};d=(new Date).getTime();var k=cookieRead("s_dur"),a=0;if(isNaN(k)||18E5<d-k)k=d;a=d-k;cookieWrite("s_dur",k+"",30);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute":a+" minutes"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getVisitDuration` 方法不使用任何引數。它會傳回以下其中一個值：

* `"first hit of visit"`
* `"less than a minute"`
* `"1 minute"`
* `"[x] minutes"` (其中 `[x]` 是訪客進到網站以來經過的分鐘數)

此外掛程式會建立名為 `"s_dur"` 的第一方 Cookie，這是訪客進到網站以來經過的毫秒數。閒置 30 分鐘後，Cookie 便會到期。

## 呼叫範例

### 範例 #1

下列程式碼...

```js
s.eVar10 = s.getVisitDuration();
```

...一律會將 eVar10 設為等於訪客進到網站以來經過的分鐘數

### 範例 #2

下列程式碼...

```js
if(s.inList(s.events, "purchase")) s.eVar10 = s.getVisitDuration();
```

...使用 inList 外掛程式來檢查事件變數是否包含購買事件。若包含，eVar10 會設為等於訪客開始造訪時間和購買時間之間的分鐘數。

### 範例 #3

下列程式碼...

```js
s.prop10 = s.getVisitDuration();
```

...一律會將 prop10 設為等於訪客進到網站以來經過的分鐘數。如果 prop10 已啟用路徑功能，此設定會非常實用。將「退出」量度新增至 prop10 報表時，會顯示較精細的「散點圖」報表，指出訪客離開網站前的造訪分鐘數。

## 版本記錄

### 2.1 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### 2.0 (2018 年 5 月 2 日)

* 單點發行 (外掛程式全面重新分析/重寫)。
