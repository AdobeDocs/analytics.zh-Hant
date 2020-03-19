---
title: getVisitNum
description: 追蹤訪客的目前瀏覽次數。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobe外掛程式：getVisitNum

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以協助您從Adobe Analytics中獲得更多價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外掛 `getVisitNum` 程式會傳回在所需天數內瀏覽網站的所有訪客的瀏覽次數。 分析工作區提供「瀏覽次數」維度，提供類似的功能。 如果您想要進一步控製造訪數目的增加方式，Adobe建議使用此外掛程式。 如果分析工作區中的內建「造訪次數」維度足以滿足您的報表需求，則此外掛程式是不必要的。

## 使用Adobe Experience Platform Launch擴充功能安裝增效模組

Adobe提供擴充功能，讓您使用最常用的增效模組。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 按一下所要的屬性。
1. 前往標 [!UICONTROL Extensions] 簽，然後按一下按 [!UICONTROL Catalog] 鈕
1. 安裝並發佈擴充 [!UICONTROL Common Analytics Plugins] 功能
1. 如果您尚未建立，請使用下列設定建立標示為「初始化外掛程式」的規則：
   * 條件：無
   * 事件：核心——載入的程式庫（頁面頂端）
1. 使用下列設定將動作新增至上述規則：
   * 擴充功能：常見Analytics外掛程式
   * 動作類型：初始化getVisitNum
1. 儲存並發佈規則的變更。

## 使用Launch自訂程式碼編輯器安裝外掛程式

如果您不想使用外掛程式擴充功能，則可使用自訂程式碼編輯器。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 按一下所要的屬性。
1. 前往標籤 [!UICONTROL Extensions] ，然後按一下Adobe Analytics [!UICONTROL Configure] 擴充功能下的按鈕。
1. 展開accordion [!UICONTROL Configure tracking using custom code] ，以顯示按 [!UICONTROL Open Editor] 鈕。
1. 開啟自訂程式碼編輯器，並將下方提供的外掛程式碼貼入編輯視窗。
1. 儲存變更並發佈至Analytics擴充功能。

## 使用AppMeasurement安裝外掛程式

在Analytics追蹤物件實例化（使用）後，將下列程式碼複製並貼至AppMeasurement檔案中的任 [`s_gi`](../functions/s-gi.md)何位置。 保留您實作中的程式碼注釋和版本號碼，有助於Adobe疑難排解任何潛在問題。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getVisitNum v4.11 (Requires endOfDatePeriod plug-in) */
s.getVisitNum=function(rp,erp){var s=this,c=function(rp){return isNaN(rp)?!1:(parseFloat(rp)|0)===parseFloat(rp)};rp=rp?rp:365;erp= "undefined"!==typeof erp?!!erp:c(rp)?!0:!1;var e=(new Date).getTime(),b=endOfDatePeriod(rp);if(s.c_r("s_vnc"+rp))var g=s.c_r("s_vnc"+rp).split("&vn="),d=g[1];if(s.c_r("s_ivc"))return d?(b.setTime(e+18E5),s.c_w("s_ivc",!0,b),d):"unknown visit number";if("undefined"!==typeof d)return d++,c=erp&&c(rp)?e+864E5*rp:g[0],b.setTime(c),s.c_w("s_vnc"+rp,c+"&vn="+d,b),b.setTime(e+ 18E5),s.c_w("s_ivc",!0,b),d;c=c(rp)?e+864E5*rp:endOfDatePeriod(rp).getTime();s.c_w("s_vnc"+rp,c+"&vn=1",b);b.setTime(e+18E5); s.c_w("s_ivc",!0,b);return"1"};

/* Adobe Consulting Plugin: endOfDatePeriod v1.1 */
var endOfDatePeriod=function(dp){var a=new Date,b=isNaN(dp)?0:Math.floor(dp);a.setHours(23);a.setMinutes(59);a.setSeconds(59); "w"===dp&&(b=6-a.getDay());if("m"===dp){b=a.getMonth()+1;var d=a.getFullYear();b=(new Date(d?d:1970,b?b:1,0)).getDate()-a.getDate()}a.setDate(a.getDate()+b);"y"===dp&&(a.setMonth(11),a.setDate(31));return a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

該方 `getVisitNum` 法使用以下引數：

* **`rp`** （可選，整數或字串）:造訪次數計數器重設前的天數。  預設為 `365` 未設定時。
   * 當此引數 `"w"`為時，計數器會在週末重設（本週六晚上11:59）
   * 當此引數 `"m"`為時，計數器會在月底（本月的最後一天）重設
   * 當此引數 `"y"`為時，計數器會在年底重設（12月31日）
* **`erp`** （可選，布林）:當引數 `rp` 為數字時，此引數會決定是否應延長瀏覽次數的有效期。 若設為 `true`，您網站的後續點擊會重設瀏覽次數計數器。 若設為 `false`，當造訪次數計數器重設時，您網站的後續點擊不會延長。 預設為 `true`。 當引數為字串時， `rp` 此引數無效。

當訪客在閒置30分鐘後返回您的網站時，瀏覽次數會增加。 呼叫此方法會傳回一個整數，代表訪客的目前瀏覽次數。

此外掛程式會設定第一方Cookie，稱 `"s_vnc[LENGTH]"` 為 `[LENGTH]` 其中是傳遞至引數的 `rp` 值。 For example, `"s_vncw"`, `"s_vncm"`, or `"s_vnc365"`. Cookie的值是Unix時間戳記的組合，代表存取計數器重設時間，例如週末、月末或閒置365天後。 也包含目前的瀏覽次數。 此外掛程式會設定另一個名為Cookie `"s_ivc"` 的Cookie，該Cookie會設 `true` 定為閒置30分鐘後過期。

## 呼叫範例

### 範例#1

對於最近365天內未瀏覽過網站的訪客，下列程式碼會將s.prop1設定為1:

```js
s.prop1=s.getVisitNum();
```

### 範例#2

若訪客在首次瀏覽後364天內回訪網站，下列程式碼會將s.prop1設為2:

```js
s.prop1=s.getVisitNum(365);
```

如果此訪客在第二次瀏覽後364天內返回網站，下列程式碼會將s.prop1設為3:

```js
s.prop1=s.getVisitNum(365);
```

### 範例#3

若訪客在首次瀏覽後179天內回訪網站，下列程式碼會將s.prop1設為2:

```js
s.prop1=s.getVisitNum(180,false);
```

不過，如果此訪客在第二次瀏覽後1天或多天返回網站，下列程式碼會將s.prop1設為1:

```js
s.prop1=s.getVisitNum(180,false);
```

當呼叫中的第二個引數等於false時，決定瀏覽次數何時應「重設」為1的例項會在訪客首次瀏覽網站後的「x」天數（在此範例中為365天）中做出決定。

當第二個引數等於true（或完全未設定）時，外掛程式只會在「x」天數後（在此範例中為365天），將訪客閒置數重設為1。

### 範例#4

對於目前這週（從星期日開始）首次瀏覽網站的所有訪客，下列程式碼會將s.prop1設為1:

```js
s.prop1=s.getVisitNum("w");
```

### 範例#5

對於在當月（從每月的第一天開始）首次瀏覽網站的所有訪客，下列程式碼會將s.prop1設為1:

```js
s.prop1=s.getVisitNum("m");
```

請記住，getVisitNum外掛程式不會考慮零售型日曆（例如4-5-4、4-4-5等）

### 範例#6

對於本年度（從1月1日開始）首次瀏覽網站的所有訪客，下列程式碼會將s.prop1設為1:

```js
s.prop1=s.getVisitNum("y");
```

### 範例#7

如果您想要追蹤某周訪客的瀏覽次數、該月訪客的瀏覽次數，以及該年訪客的瀏覽次數（全部在不同的Analytics變數內），您應使用類似下列的程式碼：

```js
s.prop1=s.getVisitNum("w");
s.prop2=s.getVisitNum("m");
s.prop3=s.getVisitNum("y");
```

在此情況下，外掛程式會建立3個不同的Cookie（每個時段各一個），以追蹤每個時段的個別瀏覽次數。

## 版本記錄

### 4.11（2019年9月30日）

* 修正引數明確 `erp` 設為的問題 `false`。

### 4.1（2018年5月21日）

* 將外 `endOfDatePeriod` 掛程式更新為v1.1。

### 4.0（2018年4月17日）

* 點數發行（重新編譯，程式碼大小較小）。
* 移除Cookie引數作為外掛程式，現在會根據引數動態產生 `rp` Cookie)

### 3.0（2016年6月5日）

* 徹底大修
* 結合各種外掛程式版本的所有舊 `getVisitNum` 版解決方案。
