---
title: getVisitNum
description: 追蹤訪客的目前造訪次數。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adobe 外掛程式：getVisitNum

>[!IMPORTANT] 此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`getVisitNum` 外掛程式會傳回在指定天數內造訪過網站的所有訪客造訪次數。Analysis Workspace 提供的「造訪次數」維度具有類似功能。如果您想更深入控製造訪次數的增加方式，Adobe 建議使用此外掛程式。如果 Analysis Workspace 中的內建「造訪次數」維度足以滿足您的報表需求，就不需要此外掛程式。

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
   * 動作類型：初始化 getVisitNum
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
/* Adobe Consulting Plugin: getVisitNum v4.11 (Requires endOfDatePeriod plug-in) */
s.getVisitNum=function(rp,erp){var s=this,c=function(rp){return isNaN(rp)?!1:(parseFloat(rp)|0)===parseFloat(rp)};rp=rp?rp:365;erp= "undefined"!==typeof erp?!!erp:c(rp)?!0:!1;var e=(new Date).getTime(),b=endOfDatePeriod(rp);if(s.c_r("s_vnc"+rp))var g=s.c_r("s_vnc"+rp).split("&vn="),d=g[1];if(s.c_r("s_ivc"))return d?(b.setTime(e+18E5),s.c_w("s_ivc",!0,b),d):"unknown visit number";if("undefined"!==typeof d)return d++,c=erp&&c(rp)?e+864E5*rp:g[0],b.setTime(c),s.c_w("s_vnc"+rp,c+"&vn="+d,b),b.setTime(e+ 18E5),s.c_w("s_ivc",!0,b),d;c=c(rp)?e+864E5*rp:endOfDatePeriod(rp).getTime();s.c_w("s_vnc"+rp,c+"&vn=1",b);b.setTime(e+18E5); s.c_w("s_ivc",!0,b);return"1"};

/* Adobe Consulting Plugin: endOfDatePeriod v1.1 */
var endOfDatePeriod=function(dp){var a=new Date,b=isNaN(dp)?0:Math.floor(dp);a.setHours(23);a.setMinutes(59);a.setSeconds(59); "w"===dp&&(b=6-a.getDay());if("m"===dp){b=a.getMonth()+1;var d=a.getFullYear();b=(new Date(d?d:1970,b?b:1,0)).getDate()-a.getDate()}a.setDate(a.getDate()+b);"y"===dp&&(a.setMonth(11),a.setDate(31));return a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getVisitNum` 方法使用以下引數：

* **`rp`** (選用，整數或字串)：造訪次數計數器重設前的天數。若未設定，則預設為 `365`。
   * 此引數為 `"w"` 時，計數器會在當週結束時 (本週六晚上 11:59) 重設
   * 此引數為 `"m"` 時，計數器會在當月結束時 (本月的最後一天) 重設
   * 此引數為 `"y"` 時，計數器會在當年結束時 (12 月 31 日) 重設
* **`erp`** (選用，布林值)：`rp` 引數為數字時，此引數會決定是否應延長造訪次數的有效期。若設為 `true`，您網站的後續點擊會重設造訪次數計數器。若設為 `false`，造訪次數計數器重設時，您網站的後續點擊不會延長。預設為 `true`。`rp` 引數為字串時，此引數無效。

訪客閒置 30 分鐘後再返回您的網站時，造訪次數會增加。呼叫此方法會傳回一個整數，代表訪客目前的造訪次數。

此外掛程式會設定名為 `"s_vnc[LENGTH]"` 的第一方 Cookie，其中的 `[LENGTH]` 是傳入 `rp` 引數的值。例如 `"s_vncw"`、`"s_vncm"` 或 `"s_vnc365"`。Cookie 的值是 Unix 時間戳記的組合，代表造訪計數器重設的時間，例如當週結束時、當月結束時或閒置 365 天後。其中也包含目前的造訪次數。此外掛程式會設定另一個名為 `"s_ivc"` 的 Cookie，該 Cookie 設為 `true` 且閒置 30 分鐘後會到期。

## 呼叫範例

### 範例 #1

對於過去 365 天內未曾造訪過網站的訪客，下列程式碼會將 s.prop1 設為等於 1：

```js
s.prop1=s.getVisitNum();
```

### 範例 #2

對於首次造訪後 364 天內回訪網站的訪客，下列程式碼會將 s.prop1 設為等於 2：

```js
s.prop1=s.getVisitNum(365);
```

如果此訪客在第二次造訪後 364 天內回訪網站，下列程式碼會將 s.prop1 設為等於 3：

```js
s.prop1=s.getVisitNum(365);
```

### 範例 #3

對於首次造訪後 179 天內回訪網站的訪客，下列程式碼會將 s.prop1 設為等於 2：

```js
s.prop1=s.getVisitNum(180,false);
```

不過，如果此訪客在第二次造訪後 1 天或更多天內回訪網站，下列程式碼會將 s.prop1 設為等於 1：

```js
s.prop1=s.getVisitNum(180,false);
```

當呼叫中的第二個引數等於 false 時，決定何時應江造訪次數「重設」為 1 的常式，會在訪客首次造訪網站後的「x」天 (此範例中為 365 天) 內做出決定。

當第二個引數等於 true (或完全未設定) 時，外掛程式只會在訪客閒置「x」天 (此範例中為 365 天) 後將造訪次數重設為 1。

### 範例 #4

對於當週 (從週日開始) 首次造訪網站的所有訪客，下列程式碼會將 s.prop1 設為等於 1：

```js
s.prop1=s.getVisitNum("w");
```

### 範例 #5

對於當月 (從每月第一天開始) 首次造訪網站的所有訪客，下列程式碼會將 s.prop1 設為等於 1：

```js
s.prop1=s.getVisitNum("m");
```

請記得，getVisitNum 外掛程式不接受零售曆 (例如 4-5-4、4-4-5 等)

### 範例 #6

對於當年 (從 1 月 1 日開始) 首次造訪網站的所有訪客，下列程式碼會將 s.prop1 設為等於 1：

```js
s.prop1=s.getVisitNum("y");
```

### 範例 #7

如果您想要追蹤當週某訪客的造訪次數、當月某訪客的造訪次數，以及當年某訪客的造訪次數 (均在不同的 Analytics 變數內)，您應使用類似下列的程式碼：

```js
s.prop1=s.getVisitNum("w");
s.prop2=s.getVisitNum("m");
s.prop3=s.getVisitNum("y");
```

在此情況下，外掛程式會建立 3 個不同的 Cookie (每個時段各一個)，以追蹤每個時段的個別造訪次數。

## 版本記錄

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
