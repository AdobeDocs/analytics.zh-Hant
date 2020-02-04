---
title: apl(appendToList)
description: 將值附加至支援多個值的變數。
translation-type: tm+mt
source-git-commit: e08f3e168a779f9678a109d7f533761629cd38f3

---


# Adobe外掛程式：apl(appendToList)

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以利您運用Adobe Analytics獲得更大價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外掛 `apl` 程式可讓您安全地將新值新增至以清單分隔的變數，例如 `events``linkTrackVars`、清單變數等。

* 如果您要新增的值不存在於變數中，則程式碼會將值新增至字串的結尾。
* 如果您要新增的值已存在於變數中，則此外掛程式不會變更值。 此功能可讓您的實施避免重複值。
* 如果您要新增至的變數為空，則外掛程式會將變數設為新值。

如果您想要新增值至包含分隔值字串的現有變數，Adobe建議使用此外掛程式。 如果您偏好串連包含分隔值之變數的字串，則不需要此外掛程式。

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
/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

該方 `apl` 法使用以下引數：

* **`lv`**（必要，字串）:包含項目分隔清單的變數，以新增值至
* **`vta`**（必要，字串）:要添加到引數值的新值的逗號分隔`lv`清單。
* **`d1`**（可選，字串）:分隔字元，用來分隔已包含在引數中的個別`lv`值。  未設定時，預設為逗`,`號()。
* **`d2`**（可選，字串）:輸出分隔字元。 預設值與未設定時`d1`相同。
* **`cc`**（可選，布林）:指示是否使用區分大小寫檢查的旗標。 如`true`果是，複製檢查區分大小寫。 如果`false`未設定，複製檢查將不區分大小寫。 預設為`false`。

方 `apl` 法返回引數的值加 `lv` 上引數中任何非重複的 `vta` 值。

## 呼叫範例

### 範例#1

若...

```js
s.events = "event22,event24";
```

...下列程式碼會執行……

```js
s.events = s.apl(s.events, "event23");
```

...s.events的最終值為：

```js
s.events = "event22,event24,event23";
```

### 範例#2

若...

```js
s.events = "event22,event23";
```

...下列程式碼會執行……

```js
s.events = s.apl(s.events, "event23");
```

...s.events的最終值仍為：

```js
s.events = "event22,event23";
```

在此範例中，由於s.events已包含&quot;event23&quot;，因此apl呼叫對s.events未做任何變更

### 範例#3

若...

```js
s.events = ""; //blank value
```

...下列程式碼會執行……

```js
s.events = s.apl(s.events, "event23");
```

...s.events的最終值將是……

```js
s.events = "event23";
```

### 範例#4

若...

```js
s.prop4 = "hello|people";
```

...下列程式碼會執行……

```js
s.eVar5 = s.apl(s.prop4, "today", "|");
```

...s.prop4的最終值仍將是……

```js
s.prop4 = "hello|people";
```

...但s.eVar5的最終值將是

```js
s.eVar5 = "hello|people|today";
```

請記住，外掛程式只會傳回值；它不一定會「重設」透過lv引數傳入的變數。

### 範例#5

若...

```js
s.prop4 = "hello|people";
```

...下列程式碼會執行……

```js
s.prop4 = s.apl(s.prop4, "today");
```

...s.prop4的最終值將是……

```js
s.prop4 = "hello|people,today";
```

請務必在lv引數值中的內容與d1/d2引數中的內容之間保持分隔字元的一致性

### 範例#6

若...

```js
s.events = "event22,event23";
```

...下列程式碼會執行……

```js
s.events = s.apl(s.events,"EVenT23", ",", ",", true);
```

...s.events的最終值為：

```js
s.events = "event22,event23,EVentT23";
```

雖然此範例不實用，但它顯示使用區分大小寫的旗標時需要小心。

### 範例#7

若...

```js
s.events = "event22,event23";
```

...下列程式碼會執行……

```js
s.events = s.apl(s.events, "event23,event24,event25");
```

...s.events的最終值為：

```js
s.events = "event22,event23,event24,event25");
```

外掛程式不會將&quot;event23&quot;新增至s.events，因為它已存在於s.events中。  但是，它會將event24和event25新增至s.events，因為之前s.events中都未包含這兩個項目。

### 範例#8

若...

```js
s.linkTrackVars = "events,eVar1";
```

...下列程式碼會執行……

```js
s.linkTrackVars = s.apl(s.linkTrackVars, "campaign", ",", ",", false);
```

...s.linkTrackVars的最終值將是：

```js
s.linkTrackVars = "events,eVar1,campaign";
```

最後三個論點(即&quot;,&quot;, &quot;,&quot;, false)不是必要的，但也不會因為設定與預設引數值相符而「傷害任何內容」。

### 範例#9

若...

```js
s.events = "event22,event24";
```

...下列程式碼會執行……

```js
s.apl(s.events, "event23");
```

...s.events的最終值仍為：

```js
s.events = "event22,event24";
```

自行執行外掛程式（未將傳回值指派給變數）並不會實際「重設」透過lv引數傳入的變數。

### 範例#10

若...

```js
s.list2 = "casesensitivevalue|casesensitiveValue"
```

...下列程式碼會執行……

```js
s.list2 = s.apl(s.list2, "CasESensiTiveValuE", "|", "-", true);
```

...s.list2的最終值為：

```js
s.list2 = "casesensitivevalue-casesensitiveValue-CasESensiTiveValuE"
```

由於兩個分隔字元引數不同，傳入的值將由第一個分隔字元引數(&quot;|&quot;)分隔，然後由第二個分隔字元引數(&quot;-&quot;)連結在一起

## 版本記錄

### 3.2（2019年9月25日）

* 已修正使用舊 `apl` 版外掛程式之呼叫的相容性問題
* 移除控制台警告以縮小大小
* 新增 `inList 2.1`

### 3.1（2018年4月22日）

* `d2` 參數現在預設為未設定 `d1` 時的引數值

### 3.0（2018年4月16日）

* 外掛程式的完整重新分析／重寫
* 新增進階錯誤檢查
* 此引 `vta` 數現在可一次接受多個值
* 已新增 `d2` 引數以格式化傳回值
* 將引數 `cc` 變更為布林值

### 2.5（2016年2月18日）

* 現在使用比 `inList` 較處理的方法

### 2.0（2016年1月26日）

* `d` （分隔字元）引數現在為可選（預設為逗號）
* `u` （區分大小寫標幟）引數現在為可選（預設為不區分大小寫）
* 不論 `u` （區分大小寫標幟）引數為何，外掛程式不會再附加值至清單（如果值已存在於清單中）