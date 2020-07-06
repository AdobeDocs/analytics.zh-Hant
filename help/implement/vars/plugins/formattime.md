---
title: formatTime
description: 將秒數轉換為等同的分鐘數、小時數等。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 100%

---


# Adobe 外掛程式：formatTime

>[!IMPORTANT]
>
> 此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`formatTime` 外掛程式可讓您以分段格式呈現任何秒數，並且四捨五入到所需的基準值。如果您想要以秒為單位擷取時間值，再轉換為分段格式 (如分鐘、天或週)，Adobe 建議您使用此外掛程式。如果您不想將以秒為單位的值分段為時間捨入格式，則不需要此外掛程式。

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
   * 動作類型：初始化 formatTime
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
/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`formatTime` 方法使用以下引數：

* **`ns`** (必要，整數)：要轉換或格式化的秒數
* **`tf`** (可選，字串)：傳回秒數的格式類型；預設為秒
   * 如果您想要以天為單位的時間，請設為 `"d"` (預設會捨入為最接近的 1/4 天基準)
   * 如果您想要以小時為單位的時間，請設為 `"h"` (預設會捨入為最接近的 1/4 小時基準)
   * 如果您想要以分鐘為單位的時間，請設為 `"m"` (預設會捨入為最接近的 1/2 分鐘基準)
   * 如果您想要以秒為單位的時間，請設為 `"s"` (預設會捨入為最接近的 5 秒基準)
* **`bml`** (可選，數字)：捨入基準的長度。預設值為 `tf` 引數中所列的基準

此方法會傳回格式化後的秒數，使用的格式為在 `tf` 參數中指定的單位。如果 `tf` 引數未設定：

* 小於一分鐘的值會捨入為最接近的 5 秒基準
* 介於一分鐘到一小時之間的值，會捨入為最接近的 1/2 分鐘基準
* 介於一小時到一天之間的值，會捨入為最接近的四分之一小時基準
* 大於一天的值會捨入為最接近的天基準

## 範例

### 範例 #1

下列程式碼...

```js
s.eVar1 = s.formatTime(38242);
```

...會將 s.eVar1 設為「10.5 小時」

傳入的引數 (38242 秒) 等於 10 小時 37 分鐘 22 秒。由於此呼叫未設定 tf 引數，而且傳入的秒數介於一小時和一天之間，所以外掛程式會傳回轉換為最接近四分之一小時基準的秒數。

### 範例 #2

下列程式碼...

```js
s.eVar1 = s.formatTime(38250);
```

...會將 s.eVar1 設定為「10.75 小時」
傳入的引數 (38250 秒) 等於 10 小時 37 分鐘 30 秒。在此例中，將傳入秒數捨入為最接近的四分之一小時基準，會將最終值設為 10.75 小時

### 範例 #3

下列程式碼...

```js
s.eVar1 = s.formatTime(38242, "m");
```

...會將 s.eVar1 設為「637.5 分鐘」

在這種情況下，「m」引數會強迫外掛程式將秒數轉換為最接近的 ½ 分鐘基準

### 範例 #4

下列程式碼...

```js
s.eVar1 = s.formatTime(38242, "m", 20);
```

...會將 s.eVar1 設為「640 分鐘」

tf 引數值 (「m」) 會強迫外掛程式將秒數轉換為分鐘，但 bml 引數值 (20) 也會強迫外掛程式將分鐘轉換捨入為最接近的 20 分鐘基準。

### 範例 #5

下列程式碼...

```js
s.eVar1 = s.formatTime(125, "s", 2);
```

...會將 s.eVar1 設為「126 秒」，這是最接近 125 秒的 2 秒基準

### 範例 #6

下列程式碼...

```js
s.eVar1 = s.formatTime(125, "m", 3);
```

...會將 s.eVar1 設為「3 分鐘」，這是最接近 125 秒的 3 分鐘基準

### 範例 #7

下列程式碼...

```js
s.eVar1 = s.formatTime(145, "m", .4);
```

...會將 s.eVar1 設為「2.4 分鐘」，這是最接近 145 秒的 2/5 分鐘基準 (如 .4 = 2/5)

## 版本記錄

### 1.1 (2018 年 5 月 21 日)

* 新增 `bml` 引數，讓捨入更具有彈性

### 1.0 (2018 年 4 月 15 日)

* 首次發行。
