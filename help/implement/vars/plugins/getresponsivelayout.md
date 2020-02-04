---
title: getResponsiveLayout
description: 判斷目前檢視的網站版面。
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe外掛程式：getResponsiveLayout

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以協助您從Adobe Analytics中獲得更多價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外 `getResponsiveLayout` 掛程式可讓您追蹤訪客目前正在檢視的互動式設計網站版本。 如果您的網站使用自適應設計，而您想要追蹤訪客檢視的網站版本，Adobe建議使用此外掛程式。 如果您的網站未使用互動式設計，則不需要此外掛程式。

## 使用Adobe Experience Platform Launch擴充功能安裝增效模組

Adobe提供擴充功能，讓您使用最常用的增效模組。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 按一下所要的屬性。
1. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下「目錄 [!UICONTROL 」按鈕]
1. 安裝和發佈 [!UICONTROL Common Analytics Plugins] extension
1. 如果您尚未建立，請使用下列設定建立標示為「初始化外掛程式」的規則：
   * 條件：無
   * 事件：核心——載入的程式庫（頁面頂端）
1. 使用下列設定將動作新增至上述規則：
   * 擴充功能：常見Analytics外掛程式
   * 動作類型：初始化getResponsiveLayout
1. 儲存並發佈規則的變更。

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
/* Adobe Consulting Plugin: getResponsiveLayout v1.0 */
var getResponsiveLayout=function(ppw,plw,tw){if(!(isNaN(ppw)||isNaN(plw)||isNaN(tw)||plw<ppw||tw<plw)){var b=window.innerWidth|| document.documentElement.clientWidth||document.body.clientWidth;return(ppw<plw&&b<=plw?b<=ppw?"phone portrait layout":"phone landscape layout":b<=plw?"phone layout":b<=tw?"tablet layout":"desktop layout")+":"+b+"x"+(window.innerHeight|| document.documentElement.clientHeight||document.body.clientHeight)}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

該方 `getResponsiveLayout` 法使用以下引數：

* **`ppw`**（必要，整數）:瀏覽器視窗在頁面從手機縱向版面切換為手機橫向版面之前所能擁有的最大像素寬度
* **`plw`**（必要，整數）:從手機橫向版面切換為平板電腦版面之前，瀏覽器視窗所能擁有的像素最大寬度
* **`tw`**（必要，布林）:從平板電腦版面切換至桌上型版面之前，瀏覽器視窗所能擁有的像素最大寬度

呼叫此方法會傳回包含兩個部分的字串。 第一部分使用下列值，視瀏覽器寬度和上述引數而定：

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"` （適用於不同時具有縱向和橫向版面的網站）
* `"tablet layout"`
* `"desktop layout"`

傳回字串的第二部分是瀏覽器的寬度和高度尺寸。 例如, `"desktop layout:1243x700"`.

## 呼叫範例

### 範例#1

若...

* 當瀏覽器寬度大於500像素時，您的網站會從手機縱向模式切換為手機橫向模式
* 當瀏覽器寬度大於700像素時，您的網站會從手機橫向模式切換為平板電腦模式
* 當瀏覽器寬度大於1000像素時，您的網站會從平板電腦模式切換至案頭模式

...下列程式碼會將eVar10設定為等於目前的互動式設計版面，以做為訪客的體驗以及瀏覽器的寬度和尺寸

```js
s.eVar10 = getResponsiveLayout(500, 700, 1000);
```

### 範例#2

若...

* 您的網站只有手機模式、平板電腦模式和案頭模式
* 當瀏覽器寬度大於500像素時，您的網站會從手機模式切換為平板電腦模式
* 當瀏覽器寬度大於1,100像素時，您的網站會從平板電腦模式切換至案頭模式

...下列程式碼會將eVar10設定為等於目前的互動式設計版面，以做為訪客的體驗以及瀏覽器的寬度和尺寸

```js
s.eVar10 = getResponsiveLayout(500, 500, 1100);
```

## 版本記錄

### 1.0（2018年5月2日）

* 首次發行。
