---
title: manageVars
description: 一次變更多個 Analytics 變數的值。
feature: Appmeasurement Implementation
exl-id: b80d1c43-7e79-443e-84fb-1f1edffca461
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 83%

---

# Adobe 外掛程式：manageVars

{{plug-in}}

`manageVars` 外掛程式可讓您一次操控多個 Analytics 變數的值。您也可以將值設為小寫，或同時從多個變數值中移除不必要的字元。如果您想一次清除多個變數的值，Adobe 建議使用此外掛程式。

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
   * 動作類型：初始化 manageVars
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
/* Adobe Consulting Plugin: manageVars v3.0 (Requires AppMeasurement) */
function manageVars(cb,l,il){var g=cb,c=l,d=il;if("-v"===g)return{plugin:"manageVars",version:"3.0"};var f=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();if("undefined"!==typeof f){f.contextData.manageVars="3.0";f.blankVars=function(a){this[a]&&(0>a.indexOf("contextData")?this[a]="":(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]="")))};f.lowerCaseVars=function(a){this[a]&&("events"!==a&&-1===a.indexOf("contextData")?(this[a]=this[a].toString(),0!==this[a].indexOf("D=")&&(this[a]=this[a].toLowerCase())):-1<a.indexOf("contextData")&&(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=this.contextData[a].toString().toLowerCase())))};f.cleanStr=function(a){function b(a){if("string"===typeof a){for(a=a.replace(/<\/?[^>]+(>|$)/g,"").trim().replace(/[\u2018\u2019\u201A]/g,"'").replace(/\t+/g,"").replace(/[\n\r]/g," ");-1<a.indexOf("  ");)a=a.replace(/\s\s/g," ");return a}return""}this[a]&&"function"===typeof b&&(0>a.indexOf("contextData")?this[a]=b(this[a]):(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=b(this.contextData[a].toString()))))};f.pt=function(a,b,c,d){if(a&&this[c]){a=a.split(b||",");b=a.length;for(var e,f=0;f<b;f++)if(e=this[c](a[f],d))return e}};if(!f[g])return!1;c=c||"";d=d||!0;var b,e="pageName,purchaseID,channel,server,pageType,campaign,state,zip,events,products,transactionID";for(b=1;76>b;b++)e+=",prop"+b;for(b=1;251>b;b++)e+=",eVar"+b;for(b=1;6>b;b++)e+=",hier"+b;for(b=1;4>b;b++)e+=",list"+b;for(b in f.contextData)e+=",contextData."+b;if(c){if(1==d)e=c.replace("['",".").replace("']","");else if(0==d){c=c.split(",");d=e.split(",");e="";for(x in c)for(y in-1<c[x].indexOf("contextData")&&(c[x]="contextData."+c[x].split("'")[1]),d)c[x]===d[y]&&(d[y]="");for(y in d)e+=d[y]?","+d[y]:""}f.pt(e,",",g,0);return!0}return""===c&&d?(f.pt(e,",",g,0),!0):!1}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`manageVars` 函數會使用以下引數：

* **`cb`** (必要，字串)：外掛程式用來操控 Analytics 變數的回呼函數名稱。您可以使用類似 `cleanStr` 的 Adobe 函數或您自己的自訂函數。
* **`l`** (選用，字串)：您要操控之 Analytics 變數的逗號分隔清單。若未設定，則預設為所有 Adobe Analytics 變數，包括：
   * `pageName`
   * `purchaseID`
   * `channel`
   * `server`
   * `pageType`
   * `campaign`
   * `state`
   * `zip`
   * `events`
   * `products`
   * `transactionID`
   * 所有 Prop
   * 所有 eVar
   * 所有階層變數
   * 所有清單變數
   * 所有上下文資料變數
* **`Il`** (選用，布林值)：如果要&#x200B;*排除* `l` 引數中宣告的變數清單而非包括，則設為 `false`。預設為 `true`。

呼叫此函數不會傳回任何內容。 而是根據所需的回呼函數變更 Analytics 變數的值。

## 呼叫範例

### 範例 #1

下列程式碼...

```js
manageVars("lowerCaseVars");
```

...會將上述所有變數的值變更為小寫版本。唯一的例外是事件變數，因為有些事件（如scAdd、scCheckout等）會區分大小寫，且不應採用小寫

### 範例 #2

下列程式碼...

```js
manageVars("lowerCaseVars", "events", false);
```

...實際上會產生與第一個範例完全相同的結果，因為事件變數預設為不會變為小寫。

### 範例 #3

下列程式碼...

```js
manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

...只會變更 (例如變為小寫) eVar1、eVar2、eVar3 和 list2 的值

### 範例 #4

下列程式碼...

```js
manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

...會變更 (例如變為小寫) 除了 eVar1、eVar2、eVar3 和 list2 EXCEPT 以外上述所有變數的值

### 範例 #5

下列程式碼...

```js
manageVars("cleanStr");
```

...會變更上述所有變數的值，包括事件變數。具體而言，cleanStr 回呼函數會對每個變數的值執行下列動作：

* 移除 HTML 編碼
* 移除值開頭和結尾的空格
* 以直式單引號(`'`)取代左/右單引號
* 以空格取代定位字元、換行字元和歸位字元
* 以單空格取代所有雙（或三等）空格

## 版本記錄

### 3.0 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### 2.1 (2019 年 1 月 14 日)

* Explorer 11 瀏覽器的錯誤修正。
* 針對 `s.cleanStr` 所做變更，現在使用一般 `cleanStr` 函數。

### 2.0 (2018 年 5 月 7 日)

* 單點發行 (包括外掛程式全面重新分析/重寫)。
* 新增 `cleanStr` 回呼函數
