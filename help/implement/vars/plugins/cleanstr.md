---
title: cleanStr
description: 從字串移除或取代所有不必要的字元。
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe外掛程式：cleanStr

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以協助您從Adobe Analytics中獲得更多價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外掛 `cleanStr` 程式會移除或取代字串中所有不必要的字元，包括HTML標籤字元、額外的空格、標籤和新行／換行符。 它也取代左／右單引號(`‘` 和 `’`)直單引號(`'`)。 如果您想要從變數值中移除不必要的字元，而Launch中的「清除文字」功能無法滿足您的實作需求，Adobe建議使用此外掛程式。 如果收集的資料不含不必要的字元，或Launch中的「清除文字」功能已足夠，則不需要此外掛程式。

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
   * 動作類型：初始化cleanStr
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
/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"");str=str.trim(); str=str.replace(/[\u2018\u2019\u201A]/g,"'");str=str.replace(/\t+/g,"");for(str=str.replace(/[\n\r]/g," ");-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

該方 `cleanStr` 法使用以下引數：

* **`str`**（必要，字串）:您要清除HTML編碼、額外空格、標籤或其他不必要字元的值。

方法返回引數的值，並刪 `str` 除所有不必要的字元。

## 範例

### 範例#1

假設下列項目（其中點代表空格，箭頭代表索引標籤字元）

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

當您執行下列程式碼時……

```js
s.eVar1 = cleanStr(s.eVar1)
```

...eVar1將設為&quot;this is a messystring&quot;（會移除所有額外空格和所有Tab字元）

### 範例#2

若...

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

...下列程式碼會執行……

```js
cleanStr(s.eVar1)
```

...s.eVar1的最終值仍為：

```js
"»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

自行執行外掛程式（未將傳回值指派給變數）並不會實際「重設」透過str引數傳入的變數。

## 版本記錄

### 1.0（2018年4月15日）

* 首次發行。
