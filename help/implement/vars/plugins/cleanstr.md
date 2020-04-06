---
title: cleanStr
description: 移除或取代字串中所有不必要的字元。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adobe 外掛程式：cleanStr

>[!IMPORTANT] 此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`cleanStr` 外掛程式會移除或取代字串中所有不必要的字元，包括 HTML 標記字元、額外的空格、標籤和新行/歸位字元。It also replaces left/right single quotes (`‘` and `’`) with straight single quotes (`'`). 如果您想要移除變數值中不必要的字元，Adobe 建議您使用此外掛程式，而 Launch 中的「清除文字」功能無法滿足實施的需求。如果收集的資料不含不必要的字元，或是 Launch 中的「清除文字」功能足以滿足需求，那麼您就不需要此外掛程式。

## 使用 Adobe Experience Platform Launch 擴充功能安裝外掛程式

Adobe 提供一個擴充功能，可讓您使用最常用的外掛程式。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
1. 按一下所需的屬性。
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. 安裝並發佈擴充 [!UICONTROL Common Analytics Plugins] 功能
1. 如果您尚未執行上述步驟，請使用下列設定建立標示為「初始化外掛程式」的規則：
   * 條件：無
   * 事件：核心 - 已載入程式庫 (頁面頂端)
1. 使用下列設定將動作新增至上述規則：
   * 擴充功能：常用 Analytics 外掛程式
   * 動作類型：初始化 cleanStr
1. 儲存並發佈規則的變更。

## 使用 Launch 自訂程式碼編輯器安裝外掛程式

如果您不想使用外掛程式擴充功能，可以使用自訂程式碼編輯器。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
1. 按一下所需的屬性。
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. 展開accordion [!UICONTROL Configure tracking using custom code] ，以顯示按 [!UICONTROL Open Editor] 鈕。
1. 開啟自訂程式碼編輯器，並將下方提供的外掛程式程式碼貼入編輯視窗中。
1. 儲存並發佈 Analytics 擴充功能的變更。

## 使用 AppMeasurement 安裝外掛程式

Analytics 追蹤物件實例化 (使用 [`s_gi`](../functions/s-gi.md)) 後，將下列程式碼複製並貼到 AppMeasurement 檔案中的任何位置。保留您實施中的程式碼備註和版本號碼，有助於 Adobe 疑難排解任何可能問題。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"");str=str.trim(); str=str.replace(/[\u2018\u2019\u201A]/g,"'");str=str.replace(/\t+/g,"");for(str=str.replace(/[\n\r]/g," ");-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`cleanStr` 方法使用以下引數：

* **`str`** (必要，字串)：您要清除 HTML 編碼、額外空格、定位字元或其他不必要字元的值。

此方法會傳回 `str` 引數的值，並刪除所有不必要的字元。

## 範例

### 範例 #1

根據以下假設 (其中點代表空格，箭頭代表定位字元)

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

當您執行下列程式碼...

```js
s.eVar1 = cleanStr(s.eVar1)
```

...eVar1 將設為「this is a messystring」(移除所有額外空格和所有定位字元)

### 範例 #2

若...

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

...且下列程式碼執行...

```js
cleanStr(s.eVar1)
```

...s.eVar1 的最終值依然會是：

```js
"»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

自動執行外掛程式 (未將傳回值指派給變數) 並不會實際「重設」透過 str 引數傳入的變數。

## 版本記錄

### 1.0 (2018 年 4 月 15 日)

* 首次發行。
