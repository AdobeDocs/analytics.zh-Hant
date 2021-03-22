---
title: getResponsiveLayout
description: 決定目前檢視的網站配置。
translation-type: tm+mt
source-git-commit: 16d2bc13a71dfe0b9106dea03da5eaa9da4d704c
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 98%

---


# Adobe 外掛程式：getResponsiveLayout

>[!IMPORTANT]
>
>此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`getResponsiveLayout` 外掛程式可讓您追蹤訪客目前正在檢視的回應式設計網站版本。如果您的網站使用回應式設計，而您想要追蹤訪客檢視的網站版本，Adobe 建議使用此外掛程式。如果您的網站並非使用回應式設計，就不需要此外掛程式。

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
   * 動作類型：初始化 getResponsiveLayout
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
/* Adobe Consulting Plugin: getResponsiveLayout v1.1 (Requires AppMeasurement) */
var getResponsiveLayout=function(ppw,plw,tw){var c=ppw,b=plw,e=tw;if("-v"===c)return{plugin:"getResponsiveLayout",version:"1.1"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.getResponsiveLayout="1.1");if(!(isNaN(c)||isNaN(b)||isNaN(e)||b<c||e<b))return a=window.innerWidth||document.documentElement.clientWidth||document.body.clientWidth,(c<b&&a<=b?a<=c?"phone portrait layout":"phone landscape layout":a<=b?"phone layout":a<=e?"tablet layout":"desktop layout")+":"+a+"x"+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getResponsiveLayout` 方法使用以下引數：

* **`ppw`** (必要，整數)：頁面從手機直向配置切換為手機橫向配置之前，瀏覽器視窗的最大像素寬度
* **`plw`** (必要，整數)：頁面從手機橫向配置切換為平板電腦配置之前，瀏覽器視窗的最大像素寬度
* **`tw`** (必要，布林值)：頁面從平板電腦配置切換為桌上型電腦配置之前，瀏覽器視窗的最大像素寬度

呼叫此方法會傳回包含兩個部分的字串。第一部分使用下列值，視瀏覽器寬度和上述引數而定：

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"` (適用於並非直向和橫向配置均具備的網站)
* `"tablet layout"`
* `"desktop layout"`

傳回字串的第二部分是瀏覽器的寬度和高度維度。例如：`"desktop layout:1243x700"`。

## 呼叫範例

### 範例 #1

若...

* 瀏覽器寬度大於 500 像素時，網站會從手機直向模式切換為手機橫向模式
* 瀏覽器寬度大於 700 像素時，網站會從手機橫向模式切換為平板電腦模式
* 瀏覽器寬度大於 1000 像素時，網站會從平板電腦模式切換為桌上型電腦模式

...下列程式碼會將 eVar10 設為等於目前的回應式設計配置，做為訪客的體驗以及瀏覽器的寬度和維度

```js
s.eVar10 = getResponsiveLayout(500, 700, 1000);
```

### 範例 #2

若...

* 您的網站只有手機模式、平板電腦模式和桌上型電腦模式
* 瀏覽器寬度大於 500 像素時，網站會從手機模式切換為平板電腦模式
* 瀏覽器寬度大於 1,100 像素時，網站會從平板電腦模式切換為桌上型電腦模式

...下列程式碼會將 eVar10 設為等於目前的回應式設計配置，做為訪客的體驗以及瀏覽器的寬度和維度

```js
s.eVar10 = getResponsiveLayout(500, 500, 1100);
```

## 版本記錄

### 1.1（2021年3月19日）

* 已新增版本號碼作為內容資料。

### 1.0 (2018 年 5 月 2 日)

* 首次發行。
