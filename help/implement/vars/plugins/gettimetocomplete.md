---
title: getTimeToComplete
description: 測量完成任務所花費的時間。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adobe 外掛程式：getTimeToComplete

>[!IMPORTANT] 此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`getTimeToComplete` 外掛程式會追蹤使用者在網站上完成程序所花的時間。「時鐘」從呼叫 `start` 動作時開始，在呼叫 `stop` 動作時結束。如果網站上有工作流程需要一些時間才能完成，而且您想瞭解訪客完成該工作流程所花的時間，Adobe 建議您使用此外掛程式。如果您網站上的工作流程耗時較短 (少於 3 秒)，就不需要使用此外掛程式，因為精細度只會降至完整秒。

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
   * 動作類型：初始化 getTimeToComplete
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
/* Adobe Consulting Plugin: getTimeToComplete v3.1 (Requires formatTime and inList plug-ins) */
s.getTimeToComplete=function(sos,cn,exp){sos=sos?sos.toLowerCase():"start";if("stop"===sos||"start"===sos){cn=cn?cn:"s_gttc";exp=exp?exp:0;var s=this,d=s.c_r(cn),e=new Date;if("start"===sos&&!d)s.c_w(cn,e.getTime(),exp?new Date(e.getTime()+864E5*exp):0);else if("stop"===sos&&d)return sos=Math.round((e.getTime()-d)/1E3),s.c_w(cn,"",0),s.formatTime(sos)}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
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
