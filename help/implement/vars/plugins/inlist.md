---
title: inList
description: 檢查是否有值包含在另一個以字元分隔的值中。
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Adobe外掛程式：inList

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以利您運用Adobe Analytics獲得更大價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外掛 `inList` 程式可讓您檢查分隔字串或JavaScript陣列物件中是否已有值。 其他數種外掛程式則依 `inList` 賴外掛程式運作。 此外掛程式可提供比JavaScript方法更明顯的優 `indexOf()` 勢，讓您不符合部分字串。 例如，如果您使用此外掛程式來檢查 `"event2"`，它將不符合包含的字串 `"event25"`。 如果您不需要檢查分隔字串或陣列中的值，或您想要使用自己的邏輯，則不需要此外掛程 `indexOf()` 式。

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
/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

該方 `inList` 法使用以下引數：

* **`lv`**（必要，字串或陣列）:要搜尋的分隔值清單或JavaScript陣列物件
* **`vtc`**（必要，字串）:要搜索的值
* **`d`**（可選，字串）:用於分隔引數中個別值的分隔`lv`字元。 未設定時，預設為逗`,`號()。
* **`cc`**（可選，布林）:如果設定為`true`，則會進行區分大小寫檢查。 如果設為`false`或省略，則會進行不區分大小寫的檢查。 預設為`false`。

如果找到 `true` 相符項目，並且找不到 `false` 相符項目，則呼叫此方法會傳回。

## 呼叫範例

### 範例#1

若...

```js
s.events="event22,event24";
```

...下列程式碼會執行……

```js
if(s.inList(s.events,"event22"))
```

...條件if陳述式為true

### 範例#2

若...

```js
s.events="event22,event24";
```

...下列程式碼會執行……

```js
if(s.inList(s.events,"event2"))
```

...條件if陳述式為false，因為inList呼叫未在event2和s.events中任一分隔值之間產生完全相符的情況

### 範例#3

若...

```js
s.events="event22,event24";
```

...下列程式碼會執行……

```js
if(!s.inList(s.events,"event23"))
```

...條件if陳述式為true，因為inList呼叫未在event23和s.events中任一分隔值之間產生完全相符的情況（請注意inList變數呼叫開頭的&quot;NOT&quot;運算子）。

### 範例#4

若...

```js
s.events = "event22,event23";
```

...下列程式碼會執行……

```js
if(s.inList(s.events,"EVenT23","",1))
```

...條件if陳述式為false。  雖然此範例不實用，但它顯示使用區分大小寫的旗標時需要小心。

### 範例#5

若...

```js
s.linkTrackVars = "events,eVar1";
```

...下列程式碼會執行……

```js
if(s.inList(s.linkTrackVars,"eVar1","|"))
```

...條件if陳述式為false。  傳入呼叫的d引數值(即&quot;|&quot;)假設s.linkTrackVars中的個別值以垂直號字元分隔，但實際上，值以逗號分隔。  在此情況下，外掛程式會嘗試在s.linkTrackVars的整個值(即&quot;events,eVar1&quot;)和要尋找的值(即&quot;eVar1&quot;)。

## 版本記錄

### v2.1（2019年9月26日）

* 已新增引數 `cc` 不是布林值的選項。 例如， `1` 是有效的大小寫檢查值。

### v2.0（2018年4月17日）

* 點數發行（重新編譯，程式碼大小較小）。

### v1.01（2017年9月27日）

* 最佳化程式碼以縮小大小

### v1.0(2009)

* 首次發行。


