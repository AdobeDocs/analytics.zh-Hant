---
title: getPageLoadTime
description: 追蹤頁面載入所需的時間。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobe外掛程式：getPageLoadTime

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以協助您從Adobe Analytics中獲得更多價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外 `getPageLoadTime` 掛程式使用JavaScript效能物件，可讓您測量頁面完全載入所花的時間。 如果您想要測量頁面載入所需的時間，Adobe建議使用此外掛程式。

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
   * 動作類型：初始化getPageLoadTime
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
/* Adobe Consulting Plugin: getPageLoadTime v1.0 with performanceWriteFull, performanceWritePart, performanceCheck, and performanceRead helper functions (Requires p_fo plug-in) */
s.getPageLoadTime=function(){var a=this;if("undefined"!==typeof performance&&a.p_fo("performance")){var b=performance; b.clearResourceTimings();""!==a.c_r("s_plt")&&(0<b.timing.loadEventEnd&&clearInterval(a.pi),a._pltLoadTime=a.c_r("s_plt"),a._pltPreviousPage=a.c_r("s_pltp"),a.c_w("s_plt",""),a.c_w("s_pltp",""));0===b.timing.loadEventEnd?a.pi=setInterval(function(){a.performanceWriteFull()},250):0<b.timing.loadEventEnd&&(a.ptc?a.ptc===b.timing.loadEventEnd&&1===b.getEntries().length&&(a.pwp=setInterval(function(){a.performanceWritePart()},500)):a.performanceWriteFull())}};
s.performanceWriteFull=function(){var s=this,a=performance.timing;0<a.loadEventEnd&&(clearInterval(s.pi),""===s.c_r("s_plt")&& (s.c_w("s_plt",s.performanceCheck(a.loadEventEnd,a.navigationStart)),s.c_w("s_pltp",s.pageName)));s.ptc=a.loadEventEnd};
s.performanceWritePart=function(){var s=this,a=performance;0<a.getEntries().length&&(s.ppfe===a.getEntries().length? clearInterval(s.pwp):s.ppfe=a.getEntries().length);""===s.c_r("s_plt")&&(s.c_w("s_plt",((a.getEntries()[a.getEntries().length-1].responseEnd-a.getEntries()[0].startTime)/1E3).toFixed(2)),s.c_w("s_pltp",s.pageName))};
s.performanceCheck=function(a,b){if(0<=a&&0<=b)return 6E4>a-b&&0<=a-b?parseFloat((a-b)/1E3).toFixed(2):60};

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

方 `getPageLoadTime` 法不使用任何引數。 呼叫此方法時，不會傳回任何內容。 而是設定下列變數：

* `s._pltPreviousPage`:上一頁，以便您將載入時間與上一頁建立關聯
* `s._pltLoadTime`:上一頁載入所花費的秒數

getPageLoadTime外掛程式會建立兩個第一方Cookie:

* `s_plt`:上一頁載入所花費的時間（以秒為單位）。 在瀏覽器作業結束時過期。
* `s_pltp` 變數的值， `s.pageName` 如先前Adobe Analytics影像要求中所記錄。 在瀏覽器作業結束時過期。

## 呼叫範例

### 範例#1

正在運行以下代碼……

```js
if(s.pageName) s.getPageLoadTime();
if(s._pltPreviousPage)
{
  s.prop10 = s._pltLoadTime;
  s.prop11 = s._pltPreviousPage
  s.eVar10 = prop11;
  s.events = "event100=" + s._pltLoadTime;
}
```

...將執行下列操作：

* 設定s.pageName時執行getPageLoadTime外掛程式
* 將s.prop10設為上一頁的載入時間
* 將s.prop11和s.eVar10設為上一頁的名稱（如s.pageName中所記錄）
* 將event100設為自訂數值事件，等於上一頁的載入時間。   在此情況下，使用自訂事件可讓您取得上一頁（來自所有訪客／瀏覽）所有頁面載入的總時間量，因此使用計算量度來取得每個頁面的平均頁面載入時間

## 版本記錄

### 1.0（2018年5月22日）

* 首次發行。
