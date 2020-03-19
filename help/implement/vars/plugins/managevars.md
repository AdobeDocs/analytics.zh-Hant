---
title: manageVars
description: 一次變更多個Analytics變數的值。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobe外掛程式：manageVars

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以協助您從Adobe Analytics中獲得更多價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外 `manageVars` 掛程式可讓您一次控制多個Analytics變數的值。 您也可以將值設為小寫，或同時從多個變數值中移除不必要的字元。 如果您想一次清除多個變數的值，Adobe建議使用此外掛程式。

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
   * 動作類型：初始化manageVars
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

該方 `manageVars` 法使用以下引數：

* **`cb`** （必要，字串）:外掛程式用來控制Analytics變數的回呼函式名稱。 您可以使用類似Adobe函式或 `cleanStr` 您自己的自訂函式。
* **`l`** （可選，字串）:您要操控之Analytics變數的逗號分隔清單。 未設定時，預設為所有Adobe Analytics變數，包括：
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
   * 所有Prop
   * 所有eVar
   * 所有階層變數
   * 所有清單變數
   * 所有上下文資料變數
* **`Il`** （可選，布林）:如果 `false` 要排除 *引數中宣告的變*`l` 數清單，則設為。 預設為 `true`。

呼叫此方法不會傳回任何內容。 它會根據所要的回呼函式變更Analytics變數的值。

## 呼叫範例

### 範例#1

下列程式碼……

```js
s.manageVars("lowerCaseVars");
```

...將上述所有變數的值變更為小寫版本。  唯一的例外是事件變數，因為有些事件（例如scAdd、scCheckout等）區分大小寫，不應小寫

### 範例#2

下列程式碼……

```js
s.manageVars("lowerCaseVars", "events", false);
```

...實際上會產生與第一個範例完全相同的結果，因為events變數預設不會小寫。

### 範例#3

下列程式碼……

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

...只會變更（例如小寫）eVar1、eVar2、eVar3和list2的值

### 範例#4

下列程式碼……

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

...將會變更（例如小寫）上述eVar1、eVar2、eVar3和list2 EXCEPT中所述的所有變數的值

### 範例#5

下列程式碼……

```js
s.manageVars("cleanStr");
```

...變更上述所有變數的值，包括事件變數。  具體而言，cleanStr回呼函式會對每個變數的值執行下列動作：

* 移除HTML編碼
* 移除值開頭和結尾處的空格
* 取代左／右單引號(例如』)，單引號(&#39;)
* 以空格替換制表符字元、換行符和歸位符
* 取代所有雙（或三等）空格，單空格

## 版本記錄

### 2.1（2019年1月14日）

* Internet Explorer 11瀏覽器錯誤修正。
* 變更 `s.cleanStr`，現在使用常規函 `cleanStr` 數。

### 2.0（2018年5月7日）

* 點數發行（包括外掛程式的完整重新分析／重寫）
* 已新增 `cleanStr` 回呼函式
