---
title: addProductEvent
description: 將自訂事件新增至產品和事件變數。
translation-type: ht
source-git-commit: 3359ed8e7ef7979be57ca5ec9ca1803fc52afe88
workflow-type: ht
source-wordcount: '632'
ht-degree: 100%

---


# Adobe 外掛程式：addProductEvent

>[!IMPORTANT]
>
>此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

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
/* Adobe Consulting Plugin: addProductEvent v2.0 */
function addProductEvent(en,ev,ap){var f=en,g=ev,c=ap;if("-v"===f)return{plugin:"addProductEvent",version:"2.0"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,e;b<window.s_c_il.length;b++)if(e=window.s_c_il[b],e._c&&"s_c"===e._c)return e}();if("undefined"!==typeof d&&(d.contextData.addProductEvent="2.0",window.apl=window.apl||function(b,e,c,d,f){function g(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!b||"string"===typeof b){if("string"!==typeof e||""===e)return b;c=c||",";d=d||c;1==d&&(d=c,f||(f=1));2==d&&1!=f&&(d=c);e=e.split(",");k=e.length;for(var h=0;h<k;h++)g(b,e[h],c,f)||(b=b?b+d+e[h]:e[h])}return b},"string"===typeof f))if(g=isNaN(g)?"1":String(g),c=c||!1,d.events=window.apl(d.events,f),d.products){var l=d.products.split(","),m=l.length;c=c?0:m-1;for(var b;c<m;c++)b=l[c].split(";"),b[4]&&-1<b[4].indexOf("event")?b[4]=b[4]+"|"+f+"="+g:b[5]?b[4]=f+"="+g:b[4]||(b[3]||(b[3]=""),b[2]||(b[2]=""),b[1]||(b[1]=""),b[4]=f+"="+g),l[c]=b.join(";");d.products=l.join(",")}else d.products=";;;;"+f+"="+g};
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

以下程式碼會將 `s.products` 變數設為 `";product1;3;300,;product2;2;122,;product3;1;25;event35=25"`。

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
s.events="purchase";
s.addProductEvent("event35", "25");
```

上述程式碼也會將 `s.events` 變數設為 `"purchase,event35"`

### 範例 #2

以下程式碼會將 `s.products` 變數設為 `";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25"`

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvent("event35", 25, 1);
```

當 `addProductEvent` 呼叫中的第三個引數為 `true` (或 `1`) 時，每個產品項目都會在新增至其值的呼叫中指定此事件。

### 範例 #3

以下程式碼會將 `s.products` 變數設為 `";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25";
s.events="purchase,event2";
s.addProductEvent("event33", "12");
s.addProductEvent("event34", "10");
s.addProductEvent("event35", "15");
```

上述程式碼也會將 `s.events` 變數設為 `"purchase,event2,event33,event34,event35"`

### 範例 #4

以下程式碼會將 `s.products` 變數設為 `";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue, ;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
s.addProductEvent("event33", "12", 1);
s.addProductEvent("event34", 10, 1);
s.addProductEvent("event35", "15", 1);
```

上述程式碼也會將 `s.events` 變數設為 `"purchase,event2,event33,event34,event35"`。

>[!NOTE]
>
>呼叫中的第二個引數可為整數，**或者**&#x200B;代表整數/數字的字串

### 範例 #5

如果尚未設定 `s.products`，以下程式碼會將它設為 `";;;;event35=25"`

```js
s.addProductEvent("event35", "25");
```

上述程式碼也會將 `"event35"` 附加至 `s.events` 的結尾，**或者**&#x200B;若尚未設定 `s.events`，上述程式碼會將 `s.events` 設為 `"event35"`

## 版本記錄

### 2.0 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### 1.0 (2019 年 10 月 7 日)

* 首次發行。
