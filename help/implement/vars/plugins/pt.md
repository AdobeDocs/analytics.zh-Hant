---
title: pt
description: 在變數清單上執行函式。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobe外掛程式：pt

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以協助您從Adobe Analytics中獲得更多價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外掛 `pt` 程式會在Analytics變數清單上執行函式或方法。 例如，您可以選擇性地在數個變 [`clearVars`](../functions/clearvars.md) 數上執行方法，而不需每次手動呼叫方法。 其他數個外掛程式則依賴此程式碼才能正確執行。 如果您不需要一次對多個Analytics變數執行特定函式，或您未使用任何相依外掛程式，則不需要此外掛程式。

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
   * 動作類型：初始化pt
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
/* Adobe Consulting Plugin: pt v2.01 */
 s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

該方 `pt` 法使用以下引數：

* **`l`** （必要，字串）:參數中包含的函式可針對的變 `cf` 數清單。
* **`de`** （可選，字串）:分隔引數中變數清單的分隔 `l` 字元。 預設為逗號(`,`)。
* **`cf`** （必要，字串）:AppMeasurement物件中包含的回呼函式名稱，可針對引數中包含的每個變數來呼 `l` 叫。
* **`fa`** （可選，字串）:如果參數中的函式在 `cf` 運行時調用其他參數，請將它們包括在此處。 預設為 `undefined`。

如果回呼函式（在引數中）傳回值，呼叫此方 `cf` 法會傳回值。

## 呼叫範例

### 範例#1

下列程式碼是getQueryParam外掛程式的一部分。  它會針對URL查詢字串(fullQueryString)中包含的每個鍵值對，執行getParameterValue輔助函式。  在其他方式中，若要擷取每個金鑰值對，fullQueryString必須以&amp;符號和&quot;&amp;&quot;字元分隔並分離。 parameterKey會參照外掛程式特別嘗試從查詢字串擷取的查詢字串參數

```javascript
returnValue = s.pt(fullQueryString, "&", "getParameterValue", parameterKey)
```

上一行是執行類似下列程式碼的捷徑：

```js
var returnValue = "",
  parameters = fullQueryString.split("&"),
  parametersLength = parameters.length;
for(var i = 0; i < parametersLength; i++)
{
  returnValue = s.getParameterValue(parameters[i], parameterKey);
  if(returnValue !== "") break;
}
```

## 版本記錄

### 2.01（2019年9月24日）

* 小幅變更程式碼以縮小整體大小

### 2.0（2018年4月17日）

* 點數發行（重新編譯，程式碼大小較小）。
* 新增H程式碼和AppMeasurement的支援。

### 1.0（2013年9月23日）

* 首次發行。
