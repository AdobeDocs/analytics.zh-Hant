---
title: inList
description: 檢查某值是否包含在另一個以字元分隔的值中。
translation-type: ht
source-git-commit: 27d151abe9bdf52c6eabdc3e9c785a99d08f971e
workflow-type: ht
source-wordcount: '743'
ht-degree: 100%

---


# Adobe 外掛程式：inList

>[!IMPORTANT]
>
>此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`inList` 外掛程式可讓您檢查某值是否已存在於分隔字串或 JavaScript 陣列物件中。有其他多種外掛程式依賴 `inList` 外掛程式才能運作。此外掛程式可提供比 JavaScript 方法 `indexOf()` 更明顯的優點，其不會比對字串的一部分。例如，如果您使用此外掛程式來檢查 `"event2"`，它將不會比對包含 `"event25"` 的字串。如果您不需要檢查分隔字串或陣列中的值，或您想要使用自己的 `indexOf()` 邏輯，就不需要此外掛程式。

## 使用 Adobe Experience Platform Launch 擴充功能安裝外掛程式

Adobe 提供一個擴充功能，可讓您使用最常用的外掛程式。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
1. 按一下所需的屬性。
1. 前往[!UICONTROL 擴充功能]標籤，然後按一下[!UICONTROL 「目錄」]按鈕
1. 安裝並發佈[!UICONTROL 常用 Analytics 外掛程式]擴充功能
1. 如果您尚未執行上述步驟，請使用下列設定建立標示為「初始化外掛程式」的規則：
   * 條件：無
   * 事件：核心 - 已載入程式庫 (頁面頂端)
1. 使用下列設定將動作新增至上述規則：
   * 擴充功能：常用 Analytics 外掛程式
   * 動作類型：初始化 inList
1. 儲存並發佈規則的變更。

## 使用 Launch 自訂程式碼編輯器安裝外掛程式

如果您不想使用外掛程式擴充功能，可以使用自訂程式碼編輯器。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
1. 按一下所需的屬性。
1. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 擴充功能底下的[!UICONTROL 「設定」]按鈕。
1. 展開[!UICONTROL 使用自訂程式碼設定追蹤]摺疊式功能表，便會顯示[!UICONTROL 「開啟編輯器」]按鈕。
1. 開啟自訂程式碼編輯器，並將下方提供的外掛程式程式碼貼入編輯視窗中。
1. 儲存並發佈 Analytics 擴充功能的變更。

## 使用 AppMeasurement 安裝外掛程式

Analytics 追蹤物件實例化 (使用 [`s_gi`](../functions/s-gi.md)) 後，將下列程式碼複製並貼到 AppMeasurement 檔案中的任何位置。保留您實施中的程式碼備註和版本號碼，有助於 Adobe 疑難排解任何可能問題。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: inList v3.0 */
function inList(lv,vtc,d,cc){var b=lv,e=vtc,c=d,f=cc;if("-v"===b)return{plugin:"inList",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.inList="3.0");if("string"!==typeof e)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==f&&e===b[c]||e.toLowerCase()===b[c].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`inList` 方法使用以下引數：

* **`lv`** (必要，字串或陣列)：要搜尋的分隔值清單或 JavaScript 陣列物件
* **`vtc`** (必要，字串)：要搜尋的值
* **`d`** (選用，字串)：用於分隔 `lv` 引數中個別值的分隔字元。若未設定，則預設為逗號 (`,`)。
* **`cc`** (選用，布林值)：如果設為 `true`，則會進行區分大小寫的檢查。如果設為 `false` 或省略，則會進行不區分大小寫的檢查。預設為 `false`。

如果找到相符項目，呼叫此方法會傳回 `true`，若找不到相符項目則會傳回 `false`。

## 呼叫範例

### 範例 #1

若...

```js
s.events="event22,event24";
```

...且下列程式碼執行...

```js
if(s.inList(s.events,"event22"))
```

...條件 if 陳述式將為 true

### 範例 #2

若...

```js
s.events="event22,event24";
```

...且下列程式碼執行...

```js
if(s.inList(s.events,"event2"))
```

...條件 if 陳述式將為 false，因為 inList 呼叫未在 event2 和 s.events 中任一分隔值之間找到完全相符的項目

### 範例 #3

若...

```js
s.events="event22,event24";
```

...且下列程式碼執行...

```js
if(!s.inList(s.events,"event23"))
```

...條件 if 陳述式將為 true，因為 inList 呼叫未在 event23 和 s.events 中任一分隔值之間找到完全相符的項目 (請留意 inList 變數呼叫開頭的「NOT」運算子)。

### 範例 #4

若...

```js
s.events = "event22,event23";
```

...且下列程式碼執行...

```js
if(s.inList(s.events,"EVenT23","",1))
```

...條件 if 陳述式將為 false。雖然此範例並不實際，但呈現出使用區分大小寫的標幟時需謹慎的必要性。

### 範例 #5

若...

```js
s.linkTrackVars = "events,eVar1";
```

...且下列程式碼執行...

```js
if(s.inList(s.linkTrackVars,"eVar1","|"))
```

...條件 if 陳述式將為 false。傳入呼叫的 d 引數值 (即「|」) 假設 s.linkTrackVars 中的個別值是以縱線字元分隔，但實際上值是以逗號分隔。在此情況下，外掛程式會嘗試在 s.linkTrackVars 的整個值 (即 &quot;events,eVar1&quot;) 和要尋找的值 (即 &quot;eVar1&quot;) 之間尋找相符項目。

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


