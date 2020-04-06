---
title: manageVars
description: 一次變更多個 Analytics 變數的值。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adobe 外掛程式：manageVars

>[!IMPORTANT] 此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`manageVars` 外掛程式可讓您一次操控多個 Analytics 變數的值。您也可以將值設為小寫，或同時從多個變數值中移除不必要的字元。如果您想一次清除多個變數的值，Adobe 建議使用此外掛程式。

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
   * 動作類型：初始化 manageVars
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
/* Adobe Consulting Plugin: manageVars v2.1 (Requires pt plug-in and other necessary callback plug-ins) */
s.manageVars=function(cb,l,il){var s=this;if(!s[cb])return!1;l=l||"";il=il||!0;var a,d="pageName,purchaseID,channel,server, pageType,campaign,state,zip,events,products,transactionID";for(a=1;76>a;a++)d+=",prop"+a;for(a=1;251>a;a++)d+=",eVar"+a;for(a=1;6>a;a++)d+=",hier"+a;for(a=1;4>a;a++)d+=",list"+a;for(a in s.contextData)d+=",contextData."+a;if(l){if(1==il)d=l.replace("['", ".").replace("']","");else if(0==il){l=l.split(",");il=d.split(",");d="";for(x in l)for(y in-1<l[x].indexOf("contextData")&& (l[x]="contextData."+l[x].split("'")[1]),il)l[x]===il[y]&&(il[y]="");for(y in il)d+=il[y]?","+il[y]:""}s.pt(d,",",cb,0);return!0} return""===l&&il?(s.pt(d,",",cb,0),!0):!1};

/* Adobe Consulting Plugin: lowerCaseVars for manageVars (Requires manageVars plug-in) */
s.lowerCaseVars=function(v){var s=this;s[v]&&("events"!==v&&-1===v.indexOf("contextData")?(s[v]=s[v].toString(),0!== s[v].indexOf("D=")&&(s[v]=s[v].toLowerCase())):-1<v.indexOf("contextData")&&(v=v.substring(v.indexOf(".")+1),s.contextData[v]&& (s.contextData[v]=s.contextData[v].toString().toLowerCase())))};

/* Adobe Consulting Plugin: cleanStr for manageVars (Requires manageVars and cleanStr plug-ins) */
s.cleanStr=function(v){var s=this;s[v]&&"function"!==typeof cleanStr&&(0>v.indexOf("contextData")?s[v]=cleanStr(s[v]): (v=v.substring(v.indexOf(".")+1),s.contextData[v]&&(s.contextData[v]=cleanStr(s.contextData[v].toString()))))};

/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"").trim().replace(/[\u2018\u2019\u201A]/g, "'").replace(/\t+/g,"").replace(/[\n\r]/g," ");for(;-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};

/* Adobe Consulting Plugin: pt v2.01 */
s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`manageVars` 方法使用以下引數：

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

呼叫此方法不會傳回任何內容，而是根據所需的回呼函數變更 Analytics 變數的值。

## 呼叫範例

### 範例 #1

下列程式碼...

```js
s.manageVars("lowerCaseVars");
```

...會將上述所有變數的值變更為小寫版本。唯一的例外是事件變數，因為有些事件 (例如 scAdd、scCheckout 等)區分大小寫，且不應變為小寫

### 範例 #2

下列程式碼...

```js
s.manageVars("lowerCaseVars", "events", false);
```

...實際上會產生與第一個範例完全相同的結果，因為事件變數預設為不會變為小寫。

### 範例 #3

下列程式碼...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

...只會變更 (例如變為小寫) eVar1、eVar2、eVar3 和 list2 的值

### 範例 #4

下列程式碼...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

...會變更 (例如變為小寫) 除了 eVar1、eVar2、eVar3 和 list2 EXCEPT 以外上述所有變數的值

### 範例 #5

下列程式碼...

```js
s.manageVars("cleanStr");
```

...會變更上述所有變數的值，包括事件變數。具體而言，cleanStr 回呼函數會對每個變數的值執行下列動作：

* 移除 HTML 編碼
* 移除值開頭和結尾的空格
* 以單引號 (&#39;) 取代左/右單引號 (例如 ’)
* 以空格取代定位字元、換行字元和歸位字元
* 以單空格取代所有雙 (或三以上)空格

## 版本記錄

### 2.1 (2019 年 1 月 14 日)

* Explorer 11 瀏覽器的錯誤修正。
* 針對 `s.cleanStr` 所做變更，現在使用一般 `cleanStr` 函數。

### 2.0 (2018 年 5 月 7 日)

* 單點發行 (包括外掛程式全面重新分析/重寫)。
* 新增 `cleanStr` 回呼函數
