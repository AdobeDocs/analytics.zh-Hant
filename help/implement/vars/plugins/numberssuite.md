---
title: Numbers Suite
description: 產生並控制數字以用於其他JavaScript變數。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobe外掛程式：Numbers Suite

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以協助您從Adobe Analytics中獲得更多價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

數字套裝提供一連串的JavaScript函式。 它包含下列外掛程式：

* **`zeroPad`**:在數字的開頭加上特定數目的零。 如果變數需要特定數位，例如您使用JavaScript日期物件，並想要以兩位數（而非一位數）格式化日期的月和日，此外掛程式就很有用。 例如， `01/09/2020` 而不是 `1/9/2020`。
* **`randomNumber`**:生成具有特定數字數的隨機數。 如果您部署協力廠商標籤，而且想要破壞快取的隨機數，此外掛程式就很有用。
* **`twoDecimals`**:把一個數字繞到衣櫥百號。 此外掛程式適用於貨幣用途，可讓您將數字捨入為有效的貨幣值。

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
   * 動作類型：初始化編號套件
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
/* Adobe Consulting Plugin: zeroPad v1.0 */
function zeroPad(num,nod){num=parseInt(num);nod=parseInt(nod);if(isNaN(num)||isNaN(nod))return"";var c=nod-num.toString().length+ 1;return Array(+(0<c&&c)).join("0")+num};

/* Adobe Consulting Plugin: randomNumber v2.0 (zeroPad plug-in optional)*/
function randomNumber(nod){nod="number"===typeof nod?17>Math.abs(nod)?Math.round(Math.abs(nod)):17:10;for(var a="1",c=0;c<nod;c++) a+="0";a=Number(a);a=Math.floor(Math.random().toFixed(nod)*a)+"";a.length!==nod&&"undefined"!==typeof zeroPad&&(a=zeroPad(a,nod)); return a};

/* Adobe Consulting Plugin: twoDecimals v1.0 */
function twoDecimals(v){return"undefined"===typeof v||void 0===v||isNaN(v)?0:Number(Number(v).toFixed(2))};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用增效模組

該方 `zeroPad` 法使用以下引數：

* **num** （必要，整數）:要貼的數字。 如果此引數包含小數，則該方法會四捨五入其值。
* **nod** （必要，整數）:最終返回值中的位數。 如果要加號的位數小於要加號的位數，則插件會將零加到引數的開 `num` 頭。

該方 `randomNumber` 法使用以下引數：

* **nod** （可選，整數）:要生成的隨機數字中的位數。 最大值為17位。 預設值為10位。

該方 `twoDecimals` 法使用以下引數：

* **val** （必要，編號）:要四捨五入到最接近百的數字（由字串或數字對象表示）。

## 傳回

* 零 **Pad方法傳回的字串等於**`num` 引數，但在其值的開頭加上特定數目的零，可確保傳回值具有正確數目的位數。
* randomNumber **方法** ，會傳回等於隨機數字的字串，其中包含所需數字數。
* twoDecimals **方法** ，返回捨入到最接近百分位數的數字對象。

## 呼叫範例

### zeroPad範例

```js
s.eVar25 = zeroPad(25.5562, 5) //sets eVar25 equal to "00025"

s.prop1 = zeroPad(25, 1) //sets prop1 equal to "25"

s.prop1 = zeroPad(232425235,23) //sets prop1 equal to "00000000000000232425235"
```

### randomNumber範例

```js
s.eVar65 = randomNumber(15) //sets eVar65 equal to "721759731750342" or some other random 15-digit number

randomNumber() //returns a random 10-digit number but is useless since this isn't used in an expression

var j = randomNumber(35) //sets a variable named j equal to "15476068651810060" or another random 17-digit number
```

### twoDecimals範例

```js
s.events = "event10=" + twoDecimals("85.4827128694") //sets s.events="event10=85.48"

var fivehundredthirtytwo = twoDecimals(532.000000001) //sets the variable fivehundredthirtytwo equal to 532

s.eVar65 = twoDecimals("672132.9699736457") //sets s.eVar65 equal to 672132.97
```

## 版本記錄

### 1.0（2019年5月25日）

* 首次發行。
