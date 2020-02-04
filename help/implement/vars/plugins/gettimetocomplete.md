---
title: getTimeToComplete
description: 測量完成任務所花費的時間。
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Adobe外掛程式：getTimeToComplete

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以利您運用Adobe Analytics獲得更大價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外 `getTimeToComplete` 掛程式會追蹤使用者在網站上完成程式所花的時間。 「時鐘」從呼叫動作時開 `start` 始，在呼叫動作時 `stop` 結束。 如果網站上的工作流程需要一些時間才能完成，而且您想瞭解訪客完成外掛程式所花的時間，Adobe建議您使用此外掛程式。 如果您網站上的工作流程耗時較短（少於3秒），因為精細度只會降至完整秒，就不需要使用此外掛程式。

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
/* Adobe Consulting Plugin: getTimeToComplete v3.1 (Requires formatTime and inList plug-ins) */
s.getTimeToComplete=function(sos,cn,exp){sos=sos?sos.toLowerCase():"start";if("stop"===sos||"start"===sos){cn=cn?cn:"s_gttc";exp=exp?exp:0;var s=this,d=s.c_r(cn),e=new Date;if("start"===sos&&!d)s.c_w(cn,e.getTime(),exp?new Date(e.getTime()+864E5*exp):0);else if("stop"===sos&&d)return sos=Math.round((e.getTime()-d)/1E3),s.c_w(cn,"",0),s.formatTime(sos)}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

該方 `getTimeToComplete` 法使用以下引數：

* **`sos`**（可選，字串）:設定為`"start"`要啟動計時器的時間。 設定為`"stop"`要停止計時器的時間。 預設為`"start"`。
* **`cn`**（可選，字串）:儲存開始時間的Cookie名稱。 預設為`"s_gttc"`。
* **`exp`**（可選，整數）:Cookie（和計時器）過期的天數。 預設為`0`，代表瀏覽器作業結束。

呼叫此方法會傳回一個字串，其中包含在和動作之間所花費的天數、小時數、分鐘數和／或 `"start"` 秒 `"stop"` 數。

## 呼叫範例

### 範例#1

使用這些呼叫可判斷訪客何時開始結帳程式，以及何時進行購買。

當訪客開始結帳時啟動計時器：

```js
if(s.events.indexOf("scCheckout") > -1) s.getTimeToComplete("start");
```

當訪客進行購買時停止計時器，並將prop1設定為停止與開始之間的時間差：

```js
if(s.events.indexOf("purchase") > -1) s.prop1 = s.getTimeToComplete("stop");
```

s.prop1會擷取完成購買程式所需的時間量

### 範例#2

如果您想要同時運行多個計時器（以測量不同的進程），則需要手動設定cn cookie參數。  例如，如果您想要測量完成購買所需的時間量，您應設定下列程式碼……

```javascript
if(s.inList(s.events, "scCheckout")) s.getTimeToComplete("start", "gttcpurchase");
if(s.inList(s.events, "purchase")) s.prop1 = s.getTimeToComplete("start", "gttcpurchase");
```

...但是，如果您也想測量（同時）填寫註冊表格所需的時間，您也會執行下列程式碼：

```js
if(s.inList(s.events, "event1")) s.getTimeToComplete("start", "gttcregister", 7);
if(s.inList(s.events, "event2")) s.prop2 = s.getTimeToComplete("stop", "gttcregister", 7);
```

在第二個範例中，event1是用來擷取註冊程式的開始，該註冊程式可能需要7天才能完成，因為無論原因為何，event2是用來擷取註冊的完成。  s.prop2會擷取完成註冊程式所需的時間量

## 版本記錄

### 3.1（2019年9月30日）

* 已新增第一個引數中需要「start」或「stop」值的邏輯。  傳入的所有其他值都會停止外掛程式的執行。
* 已將 `inList 2.0` 外掛程式更新至 `inList 2.1`。

### 3.0（2018年8月23日）

* 將外 `formatTime v1.0` 掛程式更新至 `formatTime v1.1`。

### 3.0（2018年4月17日）

* 點數發行（重新編譯，程式碼大小較小）。
* 微幅錯誤修正。

### 2.0 2016年6月21日)

* 已消除對外掛程 `p_fo` 式的依賴。
* 已新增與H程式碼和AppMeasurement的相容性。
* 已新增主控台記錄。
