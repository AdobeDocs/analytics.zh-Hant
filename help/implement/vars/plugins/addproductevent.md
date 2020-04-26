---
title: addProductEvent
description: 將自訂事件新增至產品和事件變數。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adobe 外掛程式：addProductEvent

>[!IMPORTANT] 此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`addProductEvent` 外掛程式會將數值或貨幣事件新增至 [`products`](../page-vars/products.md) 變數。如果您想要將數值或貨幣事件新增至 `products` 變數，又不想擔心產品字串格式，Adobe 建議您使用此外掛程式。如果您未在 `products` 變數中使用數值或貨幣事件，就不需要使用此外掛程式。

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
   * 動作類型：初始化 addProductEvent
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
/* Adobe Consulting Plugin: addProductEvent v1.0 (Requires apl v3.1 and inList v2.0+ plug-ins) */
s.addProductEvent=function(en,ev,ap){var s=this;if("string"===typeof en)if(ev=isNaN(ev)?"1":String(ev),ap=ap||!1,s.events= s.apl(s.events,en),s.products){var e=s.products.split(",");ap=ap?0:e.length-1;for(var a;ap<e.length;ap++)a=e[ap].split(";") ,a[4]&&a[4].includes("event")?a[4]=a[4]+"|"+en+"="+ev:a[5]?a[4]=en+"="+ev:a[4]||(a[3]||(a[3]=""),a[2]||(a[2]=""),a[1]||(a[1]=""),a[4]=en+"="+ev),e[ap]=a.join(";");s.products=e.join(",")}else s.products=";;;;"+en+"="+ev};

/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`addProductEvent` 方法使用以下引數：

* **`en`** (必要，字串)：要新增至 `products` 變數中最後一個項目的事件。如果 `products` 變數為空，系統會建立「空白」產品項目並附加事件 (與事件值)。
* **`ev`** (必要，字串)：`en` 引數中指派給數值或貨幣事件的值。若未設定，則預設為 `1`。
* **`ap`** (可選，布林)：如果產品變數目前包含多個產品項目，`true` 值 (或 `1`) 會將事件新增至所有產品項目。若未設定，則預設為 `false`。

`addProductEvent` 不傳回任何內容，而是將事件與事件值新增至 `products` 變數。此外掛程式也會自動將事件新增至 [`events`](../page-vars/events/events-overview.md) 變數，因為此處也需要它。

## Cookie

addProductEvent 外掛程式不會建立或使用任何 Cookie

## 呼叫範例

### 範例 #1

下列程式碼會將變 `s.products` 數設為 `";product1;3;300,;product2;2;122,;product3;1;25;event35=25"`。

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
s.events="purchase";
s.addProductEvent("event35", "25");
```

上述程式碼也會將變 `s.events` 數設為 `"purchase,event35"`

### 範例 #2

下列程式碼將變數 `s.products` 設為 `";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25"`

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvent("event35", 25, 1);
```

當呼叫中的第三個引 `addProductEvent` 數為 `true` (或 `1`)時，每個產品項目都會將呼叫中指定的事件新增至其值。

### 範例 #3

下列程式碼將變數 `s.products` 設為 `";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25";
s.events="purchase,event2";
s.addProductEvent("event33", "12");
s.addProductEvent("event34", "10");
s.addProductEvent("event35", "15");
```

上述程式碼也會將變 `s.events` 數設為 `"purchase,event2,event33,event34,event35"`

### 範例 #4

下列程式碼將變數 `s.products` 設為 `";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue, ;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
s.addProductEvent("event33", "12", 1);
s.addProductEvent("event34", 10, 1);
s.addProductEvent("event35", "15", 1);
```

上述程式碼也會將變 `s.events` 數設為 `"purchase,event2,event33,event34,event35"`。

>[!NOTE] 呼叫中的第二個引數可以是整數 **** ，或代表整數／數字的字串

### 範例 #5

如 `s.products` 果尚未設定，下列程式碼會將它設為 `";;;;event35=25"`

```js
s.addProductEvent("event35", "25");
```

上述程式碼也會附 `"event35"` 加至結 `s.events` 尾 **，若尚未設定，**&#x200B;上述程式碼會設定 `s.events``s.events` 為 `"event35"`

## 版本記錄

### 1.0 (2019 年 10 月 7 日)

* 首次發行。
