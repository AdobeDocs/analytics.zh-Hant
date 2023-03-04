---
title: inList
description: 檢查某值是否包含在另一個以字元分隔的值中。
feature: Variables
exl-id: 7eedfd01-2b9a-4fae-a35b-433ca6900f27
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 100%

---

# Adobe 外掛程式：inList

{{plug-in}}

`inList` 外掛程式可讓您檢查某值是否已存在於分隔字串或 JavaScript 陣列物件中。有其他多種外掛程式依賴 `inList` 外掛程式才能運作。此外掛程式可提供比 JavaScript 方法 `indexOf()` 更明顯的優點，其不會比對字串的一部分。例如，如果您使用此外掛程式來檢查 `"event2"`，它將不會比對包含 `"event25"` 的字串。如果您不需要檢查分隔字串或陣列中的值，或您想要使用自己的 `indexOf()` 邏輯，就不需要此外掛程式。

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize inList
1. Save and publish the changes to the rule.-->

## 使用自訂程式碼編輯器安裝外掛程式

如果您不想使用外掛程式擴充功能，可以使用自訂程式碼編輯器。

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
/* Adobe Consulting Plugin: inList v3.0 */
function inList(lv,vtc,d,cc){var b=lv,e=vtc,c=d,f=cc;if("-v"===b)return{plugin:"inList",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.inList="3.0");if("string"!==typeof e)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==f&&e===b[c]||e.toLowerCase()===b[c].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`inList` 函數會依據其輸入傳回布林值。 它會使用以下引數：

* **`lv`** (必要，字串或陣列)：要搜尋的分隔值清單或 JavaScript 陣列物件
* **`vtc`** (必要，字串)：要搜尋的值
* **`d`** (選用，字串)：用於分隔 `lv` 引數中個別值的分隔字元。若未設定，則預設為逗號 (`,`)。
* **`cc`** (選用，布林值)：如果設為 `true` 或 `1`，則會進行區分大小寫的檢查。 如果設為 `false` 或省略，則會進行不區分大小寫的檢查。預設為 `false`。

如果找到相符項目，呼叫此函數會傳回 `true`，若找不到相符項目則會傳回 `false`。

## 範例

```js
// Returns true
s.events = "event22,event24";
if(inList(s.events,"event22")) {
    // Code will execute
}

// Returns false because event2 is not an exact match in the string
s.events = "event22,event24";
if(inList(s.events,"event2")) {
    // Code will not execute
}

// Returns true because of the NOT operator
s.events = "event22,event24";
if(!inList(s.events,"event23")) {
    // Code will execute
}

// Returns false because of the case-sensitive check
s.events = "event22,event23";
if(inList(s.events,"EVenT23","",true)) {
    // Code will not execute
}

// Returns false because of a mismatched delimiter, treating "events,eVar1" as a single value
s.linkTrackVars = "events,eVar1";
if(inList(s.linkTrackVars,"eVar1","|")) {
    // Code will not execute
}
```

## 版本記錄

### 3.0 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### v2.1 (2019 年 9 月 26 日)

* 新增非布林值的 `cc` 引數選項。例如，`1` 是有效的大小寫檢查值。

### v2.0 (2018 年 4 月 17 日)

* 單點發行 (重新編譯，程式碼大小較小)。

### v1.01 (2017 年 9 月 27 日)

* 最佳化程式碼以縮小大小

### v1.0 (2009 年)

* 首次發行。
