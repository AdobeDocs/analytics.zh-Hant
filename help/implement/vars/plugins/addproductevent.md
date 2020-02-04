---
title: addProductEvent
description: 新增自訂事件至產品和事件變數。
translation-type: tm+mt
source-git-commit: e08f3e168a779f9678a109d7f533761629cd38f3

---


# Adobe外掛程式：addProductEvent

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以利您運用Adobe Analytics獲得更大價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外掛 `addProductEvent` 程式會新增數值或貨幣事件至變 `products` 數。 如果您想要新增數值或貨幣事件至變數，而不需擔心產品字串格式，Adobe `products` 建議使用此外掛程式。 如果您未在變數中使用數值或貨幣事件，則不需要此外掛程 `products` 式。

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
/* Adobe Consulting Plugin: addProductEvent v1.0 (Requires apl v3.1 and inList v2.0+ plug-ins) */
s.addProductEvent=function(en,ev,ap){var s=this;if("string"===typeof en)if(ev=isNaN(ev)?"1":String(ev),ap=ap||!1,s.events= s.apl(s.events,en),s.products){var e=s.products.split(",");ap=ap?0:e.length-1;for(var a;ap<e.length;ap++)a=e[ap].split(";") ,a[4]&&a[4].includes("event")?a[4]=a[4]+"|"+en+"="+ev:a[5]?a[4]=en+"="+ev:a[4]||(a[3]||(a[3]=""),a[2]||(a[2]=""),a[1]||(a[1]=""),a[4]=en+"="+ev),e[ap]=a.join(";");s.products=e.join(",")}else s.products=";;;;"+en+"="+ev};

/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

該方 `addProductEvent` 法使用以下引數：

* **`en`**（必要，字串）:要新增至變數中最後一個項目的`products`事件。 如果變`products`數為空，則會建立「空白」產品項目，並附加事件（及其值）。
* **`ev`**（必要，字串）:在引數中指派給數值或貨幣事件的`en`值。  預設為`1`未設定時。
* **`ap`**（可選，布林）:如果產品變數目前包含多個產品項目，則值(`true`或`1`)會將事件新增至所有產品項目。  預設為`false`未設定時。

它 `addProductEvent` 不傳回。 而是將事件及其值新增至變 `products` 數。 此外掛程式也會自動將事件新增至變 `events` 數，因為此處也需要它。

## Cookie

addProductEvent外掛程式不會建立或使用任何Cookie

## 呼叫範例

### 範例#1

若...

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
s.events="purchase"
```

...下列程式碼會執行……

```js
s.addProductEvent("event35", "25");
```

...s.products的最終值為：

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25;event35=25"
```

...而s.events的最終值將是：

```js
s.events="purchase,event35"
```

### 範例#2

若...

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
```

...下列程式碼會執行……

```js
s.addProductEvent("event35", 25, 1);
```

...s.products的最終值為：

```js
s.products=";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25"
```

當第三個引數等於true（或1）時，每個產品項目都會將呼叫中指定的事件新增至其值

### 範例#3

若...

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
```

...下列程式碼會執行……

```js
s.addProductEvent("event33", "12");
s.addProductEvent("event34", "10");
s.addProductEvent("event35", "15");
```

...s.products的最終值……

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"
```

...和s.events將設定如下：

```js
s.events="purchase,event2,event33,event34,event35"
```

### 範例#4

若...

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
```

...下列程式碼會執行……

```js
s.addProductEvent("event33", "12", 1);
s.addProductEvent("event34", 10, 1); //The second argument can be an integer or a string representing an integer/number
s.addProductEvent("event35", "15", 1);
```

...s.products的最終值……

```js
s.products=";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue, ;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15"
```

...和s.events將設定如下：

```js
s.events="purchase,event2,event33,event34,event35"
```

### 範例#5

如果未設定s.products，並執行下列程式碼……

```js
s.addProductEvent("event35", "25");
```

...s.products的最終值為：

```js
s.products=";;;;event35=25"
```

在此情況下，event35也會附加至s.events的結尾

## 版本記錄

### 1.0（2019年10月7日）

* 首次發行。
