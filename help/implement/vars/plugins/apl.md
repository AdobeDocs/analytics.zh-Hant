---
title: apl (appendToList)
description: 將值附加至支援多個值的變數。
feature: Appmeasurement Implementation
exl-id: 08ca43f4-f2cc-43fb-a8eb-7c9dd237dfba
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 90%

---

# Adobe 外掛程式：apl (appendToList)

{{plug-in}}

`apl` 外掛程式可讓您安全地將新值新增至以清單分隔的變數，如 [`events`](../page-vars/events/events-overview.md)、[`linkTrackVars`](../config-vars/linktrackvars.md)、[`list`](../page-vars/list.md) 等。

* 如果您要新增的值不存在於變數中，程式碼會將值新增至字串的結尾。
* 如果您要新增的值已存在於變數中，此外掛程式不會變更值。此功能可讓您的實施避免重複值。
* 如果您要新增值的目的地變數為空，外掛程式會將變數設為新值。

如果您想要將新值新增至現有變數，而且該變數包含由分隔值組成的字串，Adobe 建議您使用此外掛程式。如果您偏好將包含分隔值之變數的字串串連起來，則不需要使用此外掛程式。

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
   * 動作類型：初始化 APL (附加至清單)
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
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: apl (appendToList) v4.0 */
function apl(lv,va,d1,d2,cc){var b=lv,d=va,e=d1,c=d2,g=cc;if("-v"===b)return{plugin:"apl",version:"4.0"};var h=function(){if("undefined"!==typeof window.s_c_il)for(var k=0,b;k<window.s_c_il.length;k++)if(b=window.s_c_il[k],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof h&&(h.contextData.apl="4.0");window.inList=window.inList||function(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1};if(!b||"string"===typeof b){if("string"!==typeof d||""===d)return b;e=e||",";c=c||e;1==c&&(c=e,g||(g=1));2==c&&1!=g&&(c=e);d=d.split(",");h=d.length;for(var f=0;f<h;f++)window.inList(b,d[f],e,g)||(b=b?b+c+d[f]:d[f])}return b};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`apl` 函數會使用以下引數：

* **`lv`** (必要，字串)：為變數，其中包含要新增新值的目的地項目分隔清單
* **`vta`** (必要，字串)：為逗號分隔的新值清單，可新增至 `lv` 引數的值。
* **`d1`** (可選，字串)：用來分隔各個值的分隔字元已包含在 `lv` 引數中。若未設定，則預設為逗號 (`,`)。
* **`d2`** (可選，字串)：輸出分隔字元。若未設定，預設值與 `d1` 相同。
* **`cc`** (可選，布林)：指出是否使用區分大小寫檢查的標幟。如果是 `true`，複製檢查會區分大小寫。如果是 `false` 或未設定，複製檢查將不區分大小寫。預設為 `false`。

`apl` 函數會傳回 `lv` 引數的值，再加上 `vta` 引數中任何非重複的值。

## 範例

```js
// Set the events variable to "event22,event24,event23".
s.events = "event22,event24";
s.events = apl(s.events,"event23");

// The events variable remains unchanged because the apl function does not add duplicate values
s.events = "event22,event23";
s.events = apl(s.events,"event23");

// Set the events variable to "event23" if the events variable is blank
s.events = "";
s.events = apl(s.events,"event23");

// Append a value to eVar5. The value of prop4 remains unchanged.
// The value of eVar5 is "hello|people|today".
s.prop4 = "hello|people";
s.eVar5 = apl(s.prop4, "today", "|");

// Sets prop4 to "hello|people,today". Be mindful of correct delimiters!
s.prop4 = "hello|people";
s.prop4 = apl(s.prop4, "today");

// Sets the events variable to "event22,event23,EVentT23". Be mindful of capitalization when using the cc argument!
s.events = "event22,event23";
s.events = apl(s.events,"EVenT23", ",", ",", true);

// Sets the events variable to "event22,event23,event24,event25".
s.events = "event22,event23";
s.events = apl(s.events, "event23,event24,event25");

// Sets linkTrackVars to "events,eVar1,campaign".
// The last three arguments at the end of this apl call are not necessary because they match the default argument values.
s.linkTrackVars = "events,eVar1";
s.linkTrackVars = apl(s.linkTrackVars, "campaign", ",", ",", false);

// This apl call does not do anything because the code does not assign the returned value to a variable.
s.events = "event22,event24";
apl(s.events, "event23");

// Sets the list2 variable to "apple-APPLE-Apple".
// Since the two delimiter arguments are different, the value passed in is delimited by "|", then joined together by "-".
s.list2 = "apple|APPLE";
s.list2 = apl(s.list2, "Apple", "|", "-", true);

// Sets the list3 variable to "value1,value1,value1" (unchanged).
// Only new values are deduplicated. Existing duplicate values remain.
s.list3 = "value1,value1,value1";
s.list3 = apl(s.list3,"value1");
```

## 版本記錄

### 4.0 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

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

* 現在會使用 `inList` 函數來處理比較作業

### 2.0（2016 年 1 月 26 日）

* `d` (分隔字元) 引數現在為選用項目 (預設值為逗號)
* `u` (區分大小寫標幟) 引數現在為選用項目 (預設值為不區分大小寫)
* 不論 `u` (區分大小寫標幟) 引數為何，如果值已存在於清單中，外掛程式就不會再將值附加至清單
