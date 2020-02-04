---
title: getTimeBetweenEvents
description: 測量兩個事件之間的時間量。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobe外掛程式：getTimeBetweenEvents

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以協助您從Adobe Analytics中獲得更多價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外掛 `getTimeBetweenEvents` 程式可讓您追蹤任何兩個Analytics事件（包括購物車和自訂事件）之間的時間長度。 在追蹤結帳程式完成或您想測量時間的任何其他程式所花費的時間時，此功能十分有用。 如果您沒有任何想測量轉換所需時間的轉換程式，則此外掛程式是不必要的。

## 使用Adobe Experience Platform Launch擴充功能安裝增效模組

Adobe提供擴充功能，讓您使用最常用的增效模組。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 按一下所要的屬性。
1. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下「目錄 [!UICONTROL 」按鈕]
1. 安裝和發佈 [!UICONTROL Common Analytics Plugins] extension
1. 對於您想要使用外掛程式的任何「啟動規則」，請新增具有下列設定的動作：
   * 擴充功能：常見Analytics外掛程式
   * 動作類型：初始化addProductEvar
1. 儲存並發佈規則的變更

## 使用Launch自訂程式碼編輯器安裝外掛程式

如果您不想使用外掛程式擴充功能，則可使用自訂程式碼編輯器。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 按一下所要的屬性。
1. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下 [!UICONTROL Adobe Analytics延伸模組下的「設定] 」按鈕。
1. 展開「使 [!UICONTROL 用自訂程式碼] accordion設定追蹤」，此會顯示 [!UICONTROL 「開啟編輯器] 」按鈕。
1. 開啟自訂程式碼編輯器，並將下方提供的外掛程式碼貼入編輯視窗。
1. 儲存變更並發佈至Analytics擴充功能。

## 使用AppMeasurement安裝外掛程式

在Analytics追蹤物件實例化（使用）後，將下列程式碼複製並貼至AppMeasurement檔案中的任 `s_gi`何位置。 保留您實作中的程式碼注釋和版本號碼，有助於Adobe疑難排解任何潛在問題。

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

該方 `getTimeBetweenEvents` 法使用以下引數：

* **`ste`**（必要，字串）:啟動計時器事件。 以逗號分隔的Analytics事件字串，以「啟動計時器」。
* **`rt`**（必要，布林）:重新啟動計時器選項。 如果每`true`次變數包含啟動計時器事件時`events`要重新啟動計時器，則設定為。 如果`false`您不希望計時器在看到啟動計時器事件時重新啟動，則設定為。
* **`stp`**（必要，字串）:停止計時器事件。 逗號分隔的Analytics事件字串，「停止計時器」。
* **`res`**（必要，布林）:重設計時器選項。 如果`true`要記錄計時器啟動後的時間，請設定為AND在計時器停止後重置計時器。 如果`false`您要記錄時間，但不要停止計時器，請設定為。 如果設定為`false`，則計時器在事件變數記錄停止事件後繼續運行。
   > [!TIP] 如果您將此引數設為 `false`，強烈建議 `rte` 設定下方引數。
* **`cn`**（可選，字串）:儲存第一個事件時間的Cookie名稱。 預設為`"s_tbe"`。
* **`etd`**（可選，整數）:Cookie的過期時間（以天為單位）。 設為`0`在瀏覽器作業結束時過期。 未設定時，預設為1天。
* **`fmt`**（可選，字串）:秒數傳回的時間格式（預設為無）
   * `"s"` 數秒
   * `"m"` 幾分鐘
   * `"h"` 數小時
   * `"d"` 天
   * 未設定時，返回值的格式基於以下規則：
      * 只要不到一分鐘，就會四捨五入到最接近的5秒基準。 例如，10秒，15秒
      * 一分鐘到一小時之間的任何內容都會四捨五入至最接近的1/2分鐘基準。 例如，30.5分鐘，31分鐘
      * 一小時到一天之間的任何值，都會四捨五入至最接近的四分之一小時基準值。 例如，2.25小時，3.5小時
      * 任何大於一天的項目都會四捨五入至最接近的日期基準。 例如，1天、3天、9天
* **`bml`**（可選，數字）:根據引數格式的捨入基準的長`fmt`度。 例如，如果引數`fmt`為且`"s"`此引數為`2`，則返回值會四捨五入至最接近的2秒基準。 如果`fmt`引數`"m"`為且此引數為`0.5`，則返回值會四捨五入至最接近的半分鐘基準。
* **`rte`**（可選，字串）:移除或刪除計時器之Analytics事件的逗號分隔字串。 預設為無。

呼叫此方法會傳回一個整數，表示以所需格式顯示開始計時器事件和停止計時器事件之間的時間量。

## 呼叫範例

### 範例#1

下列程式碼……

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");
```

...is configured to behace follows:

* s.events包含event1時，計時器便會啟動。
* 每次s.events包含event1時，計時器就會重新啟動
* s.events包含event2時，計時器將停止
* 每次s.events包含event2時，計時器都會重設（即移至0秒）
* 當s.events包含event3或訪客關閉其瀏覽器時，計時器也會重設
* 記錄event1和event2之間的實際時間時，外掛程式會將eVar1設定為兩個設定之間的秒數，四捨五入至最接近的2秒基準（例如0秒、2秒、4秒、10秒、184秒等）
* 如果s.events在計時器啟動之前包含event2，則完全不會設定eVar1。

### 範例#2

下列程式碼……

```js
s.eVar1 = s.getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");
```

...is configured to behace follows:

* s.events包含event1時，計時器便會啟動。
* 計時器不會在每次s.events包含event1時重新啟動，而原始計時器仍會繼續執行
* s.events包含event2時，計時器不會停止，但外掛程式會記錄自記錄原始event1設定以來的時間
* 計時器儲存在名為&quot;s_20&quot;的Cookie中
* 只有在s.events包含event3時，或是自計時器啟動以來已經過20天時，計時器才會重設
* 當記錄（原始）event1和event2之間的時間時，外掛程式會將eVar1設定為兩個設定之間的小時數，四捨五入至最接近的1 1/2小時基準（例如0小時、1.5小時、3小時、7.5小時、478.5小時等）

### 範例#3

下列程式碼……

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true);
```

...將產生與上述第一個範例類似的結果；不過，eVar1的值會在秒、分鐘、小時或天內傳回，視計時器的最終長度而定。  此外，計時器將在首次設定後1天過期，而非訪客關閉其瀏覽器時。

## 版本記錄

### 2.1（2018年5月26日）

* 適應對新版外掛程式所做 `formatTime` 的變更。

### 2.0（2018年4月6日）

* 外掛程式的完整重寫／重新分析。
