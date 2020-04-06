---
title: apl (appendToList)
description: 將值附加至支援多個值的變數。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adobe 外掛程式：apl (appendToList)

>[!IMPORTANT] 此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

The `apl` plug-in allows you to safely add new values to list-delimited variables, such as [`events`](../page-vars/events/events-overview.md), [`linkTrackVars`](../config-vars/linktrackvars.md), [`list`](../page-vars/list.md), and others.

* 如果您要新增的值不存在於變數中，程式碼會將值新增至字串的結尾。
* 如果您要新增的值已存在於變數中，此外掛程式不會變更值。此功能可讓您的實施避免重複值。
* 如果您要新增值的目的地變數為空，外掛程式會將變數設為新值。

如果您想要將新值新增至現有變數，而且該變數包含由分隔值組成的字串，Adobe 建議您使用此外掛程式。如果您偏好將包含分隔值之變數的字串串連起來，則不需要使用此外掛程式。

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
   * 動作類型：初始化 APL (附加至清單)
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
/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`apl` 方法使用以下引數：

* **`lv`** (必要，字串)：為變數，其中包含要新增新值的目的地項目分隔清單
* **`vta`** (必要，字串)：為逗號分隔的新值清單，可新增至 `lv` 引數的值。
* **`d1`** (可選，字串)：用來分隔各個值的分隔字元已包含在 `lv` 引數中。若未設定，則預設為逗號 (`,`)。
* **`d2`** (可選，字串)：輸出分隔字元。若未設定，預設值與 `d1` 相同。
* **`cc`** (可選，布林)：指出是否使用區分大小寫檢查的標幟。如果是 `true`，複製檢查會區分大小寫。如果是 `false` 或未設定，複製檢查將不區分大小寫。預設為 `false`。

`apl` 方法會傳回 `lv` 引數的值，再加上 `vta` 引數中任何非重複的值。

## 呼叫範例

### 範例 #1

若...

```js
s.events = "event22,event24";
```

...且下列程式碼執行...

```js
s.events = s.apl(s.events, "event23");
```

... s.events 的最終值將會是：

```js
s.events = "event22,event24,event23";
```

### 範例 #2

若...

```js
s.events = "event22,event23";
```

...且下列程式碼執行...

```js
s.events = s.apl(s.events, "event23");
```

... s.events 的最終值依然會是：

```js
s.events = "event22,event23";
```

在此範例中，由於 s.events 已包含「event23」，因此 apl 呼叫不會變更 s.events

### 範例 #3

若...

```js
s.events = ""; //blank value
```

...且下列程式碼執行...

```js
s.events = s.apl(s.events, "event23");
```

... s.events 的最終值將會是...

```js
s.events = "event23";
```

### 範例 #4

若...

```js
s.prop4 = "hello|people";
```

...且下列程式碼執行...

```js
s.eVar5 = s.apl(s.prop4, "today", "|");
```

... s.prop4 的最終值依然會是...

```js
s.prop4 = "hello|people";
```

...但 s.eVar5 的最終值將會是

```js
s.eVar5 = "hello|people|today";
```

請記住，外掛程式只會傳回值，不一定會「重設」透過 lv 引數傳入的變數。

### 範例 #5

若...

```js
s.prop4 = "hello|people";
```

...且下列程式碼執行...

```js
s.prop4 = s.apl(s.prop4, "today");
```

... s.prop4 的最終值將會是...

```js
s.prop4 = "hello|people,today";
```

請務必維持一致的分隔字元，亦即 lv 引數值中的分隔字元與 d1/d2 引數中的分隔字元必須一致

### 範例 #6

若...

```js
s.events = "event22,event23";
```

...且下列程式碼執行...

```js
s.events = s.apl(s.events,"EVenT23", ",", ",", true);
```

... s.events 的最終值將會是：

```js
s.events = "event22,event23,EVentT23";
```

雖然此範例並不實際，但呈現出使用區分大小寫的標幟時需謹慎的必要性。

### 範例 #7

若...

```js
s.events = "event22,event23";
```

...且下列程式碼執行...

```js
s.events = s.apl(s.events, "event23,event24,event25");
```

... s.events 的最終值將會是：

```js
s.events = "event22,event23,event24,event25");
```

外掛程式不會將「event23」新增至 s.events，因為它已存在於 s.events 中。然而，它會將 event24 和 event25 新增至 s.events，因為兩者先前都未包含在 s.events 中。

### 範例 #8

若...

```js
s.linkTrackVars = "events,eVar1";
```

...且下列程式碼執行...

```js
s.linkTrackVars = s.apl(s.linkTrackVars, "campaign", ",", ",", false);
```

...s.linkTrackVars 的最終值將會是：

```js
s.linkTrackVars = "events,eVar1,campaign";
```

此 apl 呼叫結尾的最後三個引數 (即「,」、「,」、false) 並非必要，不過也不會因為設定而造成任何影響，因為它們與預設引數值相符。

### 範例 #9

若...

```js
s.events = "event22,event24";
```

...且下列程式碼執行...

```js
s.apl(s.events, "event23");
```

... s.events 的最終值依然會是：

```js
s.events = "event22,event24";
```

自動執行外掛程式 (未將傳回值指派給變數) 並不會實際「重設」透過 lv 引數傳入的變數。

### 範例 #10

若...

```js
s.list2 = "casesensitivevalue|casesensitiveValue"
```

...且下列程式碼執行...

```js
s.list2 = s.apl(s.list2, "CasESensiTiveValuE", "|", "-", true);
```

...s.list2 的最終值將會是：

```js
s.list2 = "casesensitivevalue-casesensitiveValue-CasESensiTiveValuE"
```

由於兩個分隔字元引數不同，傳入的值將由第一個分隔字元引數 (「|」) 分隔，再由第二個分隔字元引數 (「-」) 連結在一起

## 版本記錄

### 3.2 (2019 年 9 月 25 日)

* 修正與 `apl` 呼叫之間的相容性問題，該呼叫使用舊版外掛程式
* 移除主控台警告以縮減大小
* 新增 `inList 2.1`

### 3.1 (2018 年 4 月 22 日)

* 如果 `d2` 引數未設定，其預設值現在為 `d1` 引數的值

### 3.0 (2018 年 4 月 16 日)

* 外掛程式全面重新分析/重寫
* 新增進階錯誤檢查
* `vta` 引數現在能一次接受多個值
* 新增 `d2` 引數以將傳回值格式化
* 將 `cc` 引數變更為布林值

### 2.5（2016 年 2 月 18 日）

* 現在使用 `inList` 方法來處理比較作業

### 2.0（2016 年 1 月 26 日）

* `d` (分隔字元) 引數現在為選用項目 (預設值為逗號)
* `u` (區分大小寫標幟) 引數現在為選用項目 (預設值為不區分大小寫)
* 不論 `u` (區分大小寫標幟) 引數為何，如果值已存在於清單中，外掛程式就不會再將值附加至清單