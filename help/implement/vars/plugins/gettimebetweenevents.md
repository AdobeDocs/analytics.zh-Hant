---
title: getTimeBetweenEvents
description: 測量兩個事件之間的時間長度。
feature: Appmeasurement Implementation
exl-id: 15887796-4fe4-4b3a-9a65-a4672c5ecb34
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 91%

---

# Adobe 外掛程式：getTimeBetweenEvents

{{plug-in}}

`getTimeBetweenEvents` 外掛程式可讓您追蹤任兩個 Analytics 事件 (包括購物車和自訂事件) 之間的時間長度。若想追蹤完成結帳程序所花費的時間，或想測量任何其他程序所需的時間，此外掛程式十分有用。如果您沒有想要測量任何轉換程序所需的時間，就不需要此外掛程式。

## 使用網頁SDK或網頁SDK擴充功能安裝外掛程式

此外掛程式尚不支援在網頁SDK中使用。

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
   * 動作類型：初始化 getTimeBetweenEvents
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
/* Adobe Consulting Plugin: getTimeBetweenEvents v3.0 (AppMeasurement highly recommended) */
function getTimeBetweenEvents(ste,rt,stp,res,cn,etd,fmt,bml,rte){var v=ste,B=rt,x=stp,C=res,k=cn,m=etd,E=fmt,F=bml,p=rte;if("-v"===v)return{plugin:"getTimeBetweenEvents",version:"3.0"};var q=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();if("undefined"!==typeof q&&(q.contextData.getTimeBetweenEvents="3.0",window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var n=window.location.hostname,f=window.location.hostname.split(".").length-1;if(n&&!/^[0-9.]+$/.test(n)){f=2<f?f:2;var l=n.lastIndexOf(".");if(0<=l){for(;0<=l&&1<f;)l=n.lastIndexOf(".",l-1),f--;l=0<l?n.substring(l):n}}g=l;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var e=new Date;e.setTime(e.getTime()+6E4*d)}else e=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+e.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}},window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),e=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>e?b.length:e)))?c:""},window.formatTime=window.formatTime||function(c,b,d){function e(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var f="";"string"===typeof b&&"d"===b||("string"!==typeof b||!e("h,m,s",b))&&86400<=c?(b=86400,f="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!e("m,s",b))&&3600<=c?(b=3600,f="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!e("s",b))&&60<=c?(b=60,f="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,f="seconds",d=isNaN(d)?.2:b/d);f=Math.round(c*d/b)/d+" "+f;0===f.indexOf("1 ")&&(f=f.substring(0,f.length-1));return f}},window.inList=window.inList||function(c,b,d,e){if("string"!==typeof b)return!1;if("string"===typeof c)c=c.split(d||",");else if("object"!==typeof c)return!1;d=0;for(a=c.length;d<a;d++)if(1==e&&b===c[d]||b.toLowerCase()===c[d].toLowerCase())return!0;return!1},"string"===typeof v&&"undefined"!==typeof B&&"string"===typeof x&&"undefined"!==typeof C)){k=k?k:"s_tbe";m=isNaN(m)?1:Number(m);var r=!1,t=!1,y=v.split(","),z=x.split(",");p=p?p.split(","):[];for(var u=window.cookieRead(k),w,D=new Date,A=D.getTime(),h=new Date,e=0;e<p.length;++e)if(window.inList(q.events,p[e])){h.setDate(h.getDate()-1);window.cookieWrite(k,"",h);return}h.setTime(h.getTime()+864E5*m);for(e=0;e<y.length&&!r&&(r=window.inList(q.events,y[e]),!0!==r);++e);for(e=0;e<z.length&&!t&&(t=window.inList(q.events,z[e]),!0!==t);++e);1===y.length&&1===z.length&&v===x&&r&&t?(u&&(w=(A-u)/1E3),window.cookieWrite(k,A,m?h:0)):(!r||1!=B&&u||window.cookieWrite(k,A,m?h:0),t&&u&&(w=(D.getTime()-u)/1E3,!0===C&&(h.setDate(h.getDate()-1),window.cookieWrite(k,"",h))));return w?window.formatTime(w,E,F):""}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getTimeBetweenEvents` 函數會使用以下引數：

* **`ste`** (必要，字串)：啟動計時器事件。用於「啟動計時器」的 Analytics 事件字串 (以逗號分隔)。
* **`rt`** (必要，布林值)：重新啟動計時器選項。如果每次 `events` 變數包含啟動計時器事件時都需重新啟動計時器，則設為 `true`。如果您不希望計時器在看到啟動計時器事件時重新啟動，則設為 `false`。
* **`stp`** (必要，字串)：停止計時器事件。用於「停止計時器」的 Analytics 事件字串 (以逗號分隔)。
* **`res`** (必要，布林值)：重設計時器選項。如果要記錄計時器啟動後的時間，並在計時器停止後重設計時器，請設為 `true`。如果要記錄時間但不要停止計時器，請設為 `false`。如果設為 `false`，則計時器會在事件變數記錄停止事件後繼續執行。

  >[!TIP]
  >
  >如果將此引數設為 `false`，強烈建議設定下方的 `rte` 引數。
* **`cn`** (選用，字串)：儲存第一個事件時間的 Cookie 名稱。預設為 `"s_tbe"`。
* **`etd`** (選用，整數)：Cookie 的期限時間 (以天為單位)。設為 `0`，在瀏覽器作業階段結束時到期。若未設定，則預設為 1 天。
* **`fmt`** (選用，字串)：傳回秒數的時間格式 (無預設值)
   * `"s"` 代表秒數
   * `"m"` 代表分鐘
   * `"h"` 代表小時
   * `"d"` 代表天數
   * 若未設定，傳回值的格式會依據以下規則：
      * 不到一分鐘的任何時間，都會捨入至最接近的 5 秒基準。例如 10 秒、15 秒。
      * 一分鐘到一小時之間的任何時間，都會捨入至最接近的 1/2 分鐘基準。例如 30.5 分鐘、31分鐘
      * 一小時到一天之間的任何時間，都會捨入至最接近的四分之一小時基準。例如 2.25 小時、3.5 小時
      * 大於一天的任何時間，都會捨入至最接近的天數基準。例如 1 天、3 天、9 天
* **`bml`** (選用，數字)：根據 `fmt` 引數格式的捨入基準長度。例如，如果 `fmt` 引數為 `"s"` 且此引數為 `2`，則傳回值會捨入至最接近的 2 秒基準。如果 `fmt` 引數為 `"m"` 且此引數為 `0.5`，則傳回值會捨入至最接近的半分鐘基準。
* **`rte`** (選用，字串)：移除或刪除計時器的 Analytics 事件字串 (以逗號分隔)。無預設值。

呼叫此函數會傳回一個整數，該整數代表啟動計時器事件和停止計時器事件之間的時間長度 (以所需格式表示)。

## 呼叫範例

```js
// The timer starts or restarts when the events variable contains event1
// The timer stops and resets when the events variable contains event2
// The timer resets when the events variable contains event3 or the visitor closes their browser
// Sets eVar1 to the number of seconds between event1 and event2, rounded to the nearest 2-second benchmark
s.eVar1 = getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");

// The timer starts when the events variable contains event1. It does NOT restart with subsequent hits that also contain event1
// The timer records a "lap" when the events variable contains event2. It does not stop the timer.
// The timer resets when the events variable contains event3 or if more than 20 days pass since the timer started
// The timer is stored in a cookie labeled "s_20"
// Sets eVar4 to the number of hours between event1 and event2, rounded to the nearest 90-minute benchmark
s.eVar4 = getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");

// Similar to the above timer in eVar4, except the return value is returned in seconds/minutes/hours/days depending on the timer length.
// The timer expires after 1 day.
s.eVar4 = getTimeBetweenEvents("event1", true, "event2", true);
```

## 版本記錄

### 3.0 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### 2.1 (2018 年 5 月 26 日)

* 因應新版 `formatTime` 外掛程式的變更進行調整。

### 2.0 (2019 年 4 月 6 日)

* 外掛程式全面重寫/重新分析。
