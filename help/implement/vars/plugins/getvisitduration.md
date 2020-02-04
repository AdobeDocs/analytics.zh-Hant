---
title: getVisitDuration
description: 追蹤訪客目前在網站上逗留的時間。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobe外掛程式：getVisitDuration

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以協助您從Adobe Analytics中獲得更多價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外 `getVisitDuration` 掛程式會追蹤訪客在網站上逗留至該時段的時間，以分鐘為單位。 如果您想要追蹤網站上截至該點的累計時間，或追蹤執行活動所花費的時間，Adobe建議使用此外掛程式。 此外掛程式不會追蹤事件之間的時間長度；如果需要此功能，請使 `getTimeBetweenEvents` 用外掛程式。

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
/* Adobe Consulting Plugin: getVisitDuration v2.0 */
s.getVisitDuration=function(){var d=new Date,c=d.getTime(),b=this.c_r("s_dur");if(isNaN(b)||18E5<c-b)b=c;var a=c-b;d.setTime(c+18E5); this.c_w("s_dur",b+"",d);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute": a+" minutes"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

方 `getVisitDuration` 法不使用任何引數。 它返回以下值之一：

* `"first hit of visit"`
* `"less than a minute"`
* `"1 minute"`
* `"[x] minutes"` (其 `[x]` 中是訪客登陸網站後所經過的分鐘數)

此外掛程式會建立名為的第一方Cookie `"s_dur"`，此為訪客登入網站後經過的毫秒數。 未活動30分鐘後，Cookie即過期。

## 呼叫範例

### 範例#1

下列程式碼……

```js
s.eVar10 = s.getVisitDuration();
```

...將一律將eVar10設定為訪客登陸網站後所經過的分鐘數

### 範例#2

下列程式碼……

```js
if(s.inList(s.events, "purchase")) s.eVar10 = s.getVisitDuration();
```

...使用inList外掛程式來檢查事件變數是否包含購買事件。  若是，eVar10將設為等於訪客開始瀏覽至購買時間之間的分鐘數。

### 範例#3

下列程式碼……

```js
s.prop10 = s.getVisitDuration();
```

...將一律設定prop10，等於訪客登入網站後所經過的分鐘數。  如果prop10已啟用路徑功能，這將很有用。  將「退出點」量度新增至prop10報表時，會顯示精細的「散點圖」報表，說明訪客離開網站前幾分鐘的瀏覽時間。

## 版本記錄

### 2.0（2018年5月2日）

* 點數發行（外掛程式的完整重新分析／重寫）。
