---
title: getTimeBetweenEvents
description: 測量兩個事件之間的時間長度。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adobe 外掛程式：getTimeBetweenEvents

>[!IMPORTANT] 此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`getTimeBetweenEvents` 外掛程式可讓您追蹤任兩個 Analytics 事件 (包括購物車和自訂事件) 之間的時間長度。若想追蹤完成結帳程序所花費的時間，或想測量任何其他程序所需的時間，此外掛程式十分有用。如果您沒有想要測量任何轉換程序所需的時間，就不需要此外掛程式。

## 使用 Adobe Experience Platform Launch 擴充功能安裝外掛程式

Adobe 提供一個擴充功能，可讓您使用最常用的外掛程式。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
1. 按一下所需的屬性。
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. 安裝並發佈擴充 [!UICONTROL Common Analytics Plugins] 功能
1. 如果您尚未執行上述步驟，請使用下列設定建立標示為「初始化外掛程式」的規則：
   * 條件：無
   * 事件：核心 - 已載入程式庫 (頁面頂端)
1. 使用下列設定將動作新增至上述規則：
   * 擴充功能：常用 Analytics 外掛程式
   * 動作類型：初始化 getTimeBetweenEvents
1. 儲存並發佈規則的變更。

## 使用 Launch 自訂程式碼編輯器安裝外掛程式

如果您不想使用外掛程式擴充功能，可以使用自訂程式碼編輯器。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
1. 按一下所需的屬性。
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. 展開accordion [!UICONTROL Configure tracking using custom code] ，以顯示按 [!UICONTROL Open Editor] 鈕。
1. 開啟自訂程式碼編輯器，並將下方提供的外掛程式程式碼貼入編輯視窗中。
1. 儲存並發佈 Analytics 擴充功能的變更。

## 使用 AppMeasurement 安裝外掛程式

Analytics 追蹤物件實例化 (使用 [`s_gi`](../functions/s-gi.md)) 後，將下列程式碼複製並貼到 AppMeasurement 檔案中的任何位置。保留您實施中的程式碼備註和版本號碼，有助於 Adobe 疑難排解任何可能問題。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeBetweenEvents v2.1 (Requires formatTime and inList plug-ins) */
s.getTimeBetweenEvents=function(ste,rt,stp,res,cn,etd,fmt,bml,rte){var s=this;if("string"===typeof ste&&"undefined"!==typeof rt&&"string"===typeof stp&&"undefined"!==typeof res){cn=cn?cn:"s_tbe";etd=isNaN(etd)?1:Number(etd);var f=!1,g=!1,n=!1, p=ste.split(","),q=stp.split(",");rte=rte?rte.split(","):[];for(var h=s.c_r(cn),k,v=new Date,r=v.getTime(),c=new Date,a=0; a<rte.length;++a)s.inList(s.events,rte[a])&&(n=!0);c.setTime(c.getTime()+864E5*etd);for(a=0;a<p.length&&!f&&(f=s.inList(s.events,p[a]),!0!==f);++a);for(a=0;a<q.length&&!g&&(g=s.inList(s.events,q[a]),!0!==g);++a);1===p.length&&1===q.length&&ste===stp&&f&&g?(h&&(k=(r-h)/1E3),s.c_w(cn,r,etd?c:0)):(!f||1!=rt&&h||s.c_w(cn,r,etd?c:0),g&&h&&(k=(v.getTime()-h)/1E3,!0===res&&(n=!0)));!0===n&&(c.setDate( c.getDate()-1),s.c_w(cn,"",c));return k?s.formatTime(k,fmt,bml):""}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getTimeBetweenEvents` 方法使用以下引數：

* **`ste`** (必要，字串)：啟動計時器事件。用於「啟動計時器」的 Analytics 事件字串 (以逗號分隔)。
* **`rt`** (必要，布林值)：重新啟動計時器選項。如果每次 `events` 變數包含啟動計時器事件時都需重新啟動計時器，則設為 `true`。如果您不希望計時器在看到啟動計時器事件時重新啟動，則設為 `false`。
* **`stp`** (必要，字串)：停止計時器事件。用於「停止計時器」的 Analytics 事件字串 (以逗號分隔)。
* **`res`** (必要，布林值)：重設計時器選項。如果要記錄計時器啟動後的時間，並在計時器停止後重設計時器，請設為 `true`。如果要記錄時間但不要停止計時器，請設為 `false`。如果設為 `false`，則計時器會在事件變數記錄停止事件後繼續執行。
   > [!TIP] 如果將此引數設為 `false`，強烈建議設定下方的 `rte` 引數。
* **`cn`** (選用，字串)：儲存第一個事件時間的 Cookie 名稱。預設為 `"s_tbe"`。
* **`etd`** (選用，整數)：Cookie 的到期時間 (以天為單位)。設為 `0`，在瀏覽器作業階段結束時到期。若未設定，則預設為 1 天。
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

呼叫此方法會傳回一個整數，以所需格式表示啟動計時器事件和停止計時器事件之間的時間長度。

## 呼叫範例

### 範例 #1

下列程式碼...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");
```

...設為依照下列規則執行作業：

* s.events 包含 event1 時，計時器便會啟動。
* 每當 s.events 包含 event1 時，計時器都會重新啟動
* s.events 包含 event2 時，計時器便會停止
* 每當 s.events 包含 event2 時，計時器都會重設 (即回到 0 秒)
* 當 s.events 包含 event 3 或訪客關閉其瀏覽器時，計時器也會重設
* 記錄 event1 和 event2 之間的實際時間時，外掛程式會將 eVar1 設為等於所設定兩個事件之間的秒數，並捨入至最接近的 2 秒基準 (例如 0 秒、2 秒、4 秒、10 秒、184 秒等)
* 如果計時器啟動之前 s.events 包含 event2，則完全不會設定 eVar1。

### 範例 #2

下列程式碼...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");
```

...設為依照下列規則執行作業：

* s.events 包含 event1 時，計時器便會啟動。
* 該計時器不會在每次 s.events 包含 event1 時重新啟動，而原始計時器仍會繼續執行
* s.events 包含 event2 時，計時器不會停止，但外掛程式會記錄自記錄原始 event1 設定以來的時間
* 計時器儲存在名為「s_20」的 Cookie 中
* 只有在 s.events 包含 event3 時，或是自計時器啟動以來已經過 20 天，計時器才會重設
* 記錄 (原始) event1 和 event2 之間的時間時，外掛程式會將 eVar1 設為等於所設定兩個事件之間的小時數，並捨入至最接近的 1 又 1/2 小時基準 (例如 0 小時、1.5 小時、3 小時、7.5 小時、478.5 小時等)

### 範例 #3

下列程式碼...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true);
```

...將產生與上述第一個範例類似的結果，不過傳回的 eVar1 值格式可能為秒、分鐘、小時或天，視計時器的最終長度而定。此外，計時器將在首次設定後 1 天到期，而非訪客關閉其瀏覽器時。

## 版本記錄

### 2.1 (2018 年 5 月 26 日)

* 因應新版 `formatTime` 外掛程式的變更進行調整。

### 2.0 (2019 年 4 月 6 日)

* 外掛程式全面重寫/重新分析。
