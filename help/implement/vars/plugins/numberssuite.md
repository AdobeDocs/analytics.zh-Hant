---
title: Numbers Suite
description: 產生並操控數字以用於其他 JavaScript 變數。
feature: Variables
exl-id: 7af88dce-baf3-4581-b5b6-0d6e41922266
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 100%

---

# Adobe 外掛程式：Numbers Suite

>[!IMPORTANT]
>
>此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

Numbers Suite 提供一系列 JavaScript 函數。其中包含下列外掛程式：

* **`zeroPad`**：在數字的開頭加上特定數量的零。如果變數需要特定位數，此外掛程式非常實用；例如當您使用 JavaScript 日期物件，且想要以兩位數 (而非僅一位數) 來格式化日期的月和日時。例如 `01/09/2020` 而非 `1/9/2020`。
* **`randomNumber`**：產生具有特定位數的隨機數。如果您部署協力廠商標記，而且想要防快取的隨機數，此外掛程式就相當實用。
* **`twoDecimals`**：將數字捨入至最接近的百位數。此外掛程式適用於貨幣用途，可讓您將數字捨入至有效的貨幣值。

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
    * Action Type: Initialize Numbers Suite
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

Analytics 追蹤物件實例化 (使用 [`s_gi`](../functions/s-gi.md)) 後，將下列程式碼複製並貼到 AppMeasurement 檔案中的任何位置。保留您實施中的程式碼備註和版本號碼，有助於 Adobe 疑難排解任何可能問題。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: zeroPad v1.0 */
function zeroPad(num,nod){num=parseInt(num);nod=parseInt(nod);if(isNaN(num)||isNaN(nod))return"";var c=nod-num.toString().length+ 1;return Array(+(0<c&&c)).join("0")+num};

/* Adobe Consulting Plugin: randomNumber v2.0 (zeroPad plug-in optional)*/
function randomNumber(nod){nod="number"===typeof nod?17>Math.abs(nod)?Math.round(Math.abs(nod)):17:10;for(var a="1",c=0;c<nod;c++) a+="0";a=Number(a);a=Math.floor(Math.random().toFixed(nod)*a)+"";a.length!==nod&&"undefined"!==typeof zeroPad&&(a=zeroPad(a,nod)); return a};

/* Adobe Consulting Plugin: twoDecimals v1.0 */
function twoDecimals(v){return"undefined"===typeof v||void 0===v||isNaN(v)?0:Number(Number(v).toFixed(2))};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`zeroPad` 函數會使用以下引數：

* **num** (必要，整數)：要填補的數字。 如果此引數包含小數，該函數會將其值四拾五入。
* **nod** (必要，整數)：最終傳回值的位數。如果要填補的數字位數小於要填補的位數，則外掛程式會將零加到 `num` 引數的開頭。

`randomNumber` 函數會使用以下引數：

* **nod** (選用，整數)：要產生的隨機數字位數。最大值為 17 位數。預設值為 10 位數。

`twoDecimals` 函數會使用以下引數：

* **val** (必要，數字)：要捨入到最接近百位數的數字 (以字串或數字物件表示)。

## 傳回

* **zeroPad** 函數傳回的字串等於 `num` 引數，但會在其值的開頭加上特定數量的零，以確保傳回值具有正確的位數。
* **randomNumber** 函數傳回的字串等於具有指定位數的隨機數。
* **twoDecimals** 函數會傳回捨入到最接近百位數的數字物件。

## 呼叫範例

### zeroPad 範例

```js
s.eVar25 = zeroPad(25.5562, 5) //sets eVar25 equal to "00025"

s.prop1 = zeroPad(25, 1) //sets prop1 equal to "25"

s.prop1 = zeroPad(232425235,23) //sets prop1 equal to "00000000000000232425235"
```

### randomNumber 範例

```js
s.eVar65 = randomNumber(15) //sets eVar65 equal to "721759731750342" or some other random 15-digit number

randomNumber() //returns a random 10-digit number but is useless since this isn't used in an expression

var j = randomNumber(35) //sets a variable named j equal to "15476068651810060" or another random 17-digit number
```

### twoDecimals 範例

```js
s.events = "event10=" + twoDecimals("85.4827128694") //sets s.events="event10=85.48"

var fivehundredthirtytwo = twoDecimals(532.000000001) //sets the variable fivehundredthirtytwo equal to 532

s.eVar65 = twoDecimals("672132.9699736457") //sets s.eVar65 equal to 672132.97
```

## 版本記錄

### 1.0 (2019 年 5 月 25 日)

* 首次發行。
