---
title: formatTime
description: 將數秒轉換為數分鐘、數小時等等等。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobe外掛程式：formatTime

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以協助您從Adobe Analytics中獲得更多價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外 `formatTime` 掛程式可讓您花費任意秒數，並以分組格式呈現，四捨五入為所需的基準值。 如果您想要以秒為單位擷取時間值，並將其轉換為貯體格式（例如分鐘、天或周）,Adobe建議使用此外掛程式。 如果您不想將第二個值分段為時間捨入格式，則不需要此外掛程式。

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
   * 動作類型：初始化formatTime
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
/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

該方 `formatTime` 法使用以下引數：

* **`ns`** （必要，整數）:轉換或格式化的秒數
* **`tf`** （可選，字串）:返回秒數的格式類型；預設為秒
   * 如果您 `"d"` 想要以天為單位的時間，請設為（預設會捨入至最接近的1/4天基準）
   * 如果您 `"h"` 想要時間（以小時為單位），請設為（預設會捨入至最接近的1/4小時基準）
   * 如果您 `"m"` 想要時間（以分鐘為單位），請設定為（預設會捨入至最接近的1/2分鐘基準）
   * 如果您 `"s"` 想要時間（以秒為單位），請設定為（預設會捨入至最接近的5秒基準）
* **`bml`** （可選，數字）:捨入基準的長度。 預設為引數中所列的基準 `tf` 。

方法返回使用參數中指定的單位格式化的秒 `tf` 數。 如果未 `tf` 設定引數：

* 只要不到一分鐘，就會四捨五入到最接近的5秒基準
* 一分鐘到一小時之間的任何內容都會四捨五入至最接近的1/2分鐘基準
* 一小時到一天之間的任何內容，都會四捨五入至最接近的四分之一小時基準
* 任何大於一天的項目都會四捨五入至最接近的日期基準

## 範例

### 範例#1

下列程式碼……

```js
s.eVar1 = s.formatTime(38242);
```

...將s.eVar1設為&quot;10.5小時&quot;

傳入的引數- 38242秒——等於10小時、37分鐘和22秒。  由於此呼叫中未設定tf引數，且傳入的秒數介於一小時和一天之間，外掛程式會傳回轉換為最接近四分之一小時基準的秒數。

### 範例#2

下列程式碼……

```js
s.eVar1 = s.formatTime(38250);
```

...will set s.eVar1 equal to &quot;10.75 hours&quot;傳入的引數- 38250秒——等於10小時、37分鐘和30秒。  在此例中，捨入傳遞至最接近的季度小時基準的秒數，會將最終值設為10.75小時

### 範例#3

下列程式碼……

```js
s.eVar1 = s.formatTime(38242, "m");
```

...將s.eVar1設為&quot;637.5分鐘&quot;

在這種情況下，&quot;m&quot;引數會強制外掛程式將秒數轉換為最接近的半分鐘基準

### 範例#4

下列程式碼……

```js
s.eVar1 = s.formatTime(38242, "m", 20);
```

...將s.eVar1設為&quot;640分鐘&quot;

tf引數值(&quot;m&quot;)強制外掛程式將秒數轉換為分鐘，但bml引數值(20)也強制外掛程式將分鐘轉換捨去至最接近的20分鐘基準。

### 範例#5

下列程式碼……

```js
s.eVar1 = s.formatTime(125, "s", 2);
```

...將s.eVar1設為&quot;126秒&quot;，這是最接近的2秒基準為125秒

### 範例#6

下列程式碼……

```js
s.eVar1 = s.formatTime(125, "m", 3);
```

...將s.eVar1設為&quot;3分鐘&quot;，這是最接近3分鐘的基準為125秒

### 範例#7

下列程式碼……

```js
s.eVar1 = s.formatTime(145, "m", .4);
```

...將s.eVar1設為&quot;2.4分鐘&quot;，此為最接近的2/5分鐘基準(例如.4 = 2/5)至145秒

## 版本記錄

### 1.1（2018年5月21日）

* 新增引 `bml` 數，讓捨入更具彈性

### 1.0（2018年4月15日）

* 初始發行。
