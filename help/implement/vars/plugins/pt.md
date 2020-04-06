---
title: pt
description: 對變數清單執行函數。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adobe 外掛程式：pt

>[!IMPORTANT] 此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`pt` 外掛程式會對 Analytics 變數清單執行函數或方法。例如，您可以選擇性地對多個變數執行 [`clearVars`](../functions/clearvars.md) 方法，而不需每次都手動呼叫該方法。其他多個外掛程式依賴此程式碼才能正確運作。如果您不需要一次對多個 Analytics 變數執行特定函數，或者您未使用任何相依外掛程式，就不需要此外掛程式。

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
   * 動作類型：初始化 pt
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
/* Adobe Consulting Plugin: pt v2.01 */
 s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`pt` 方法使用以下引數：

* **`l`** (必要，字串)：變數清單，包含 `cf` 引數的函數可針對此清單執行。
* **`de`** (選用，字串)：區分 `l` 引數中變數清單的分隔字元。預設為逗號 (`,`)。
* **`cf`** (必要，字串)：要針對 `l` 引數中包含的每個變數呼叫的 AppMeasurement 物件中，所包含的回呼函數名稱。
* **`fa`** (選用，字串)：如果 `cf` 引數中的函數會在執行時呼叫其他引數，請在此處納入它們。預設為 `undefined`。

如果回呼函數 (在 `cf` 引數中) 傳回值，呼叫此方法便會傳回值。

## 呼叫範例

### 範例 #1

下列程式碼是 getQueryParam 外掛程式的一部分。它會針對 URL 查詢字串 (fullQueryString) 中包含的每個鍵值組執行 getParameterValue 協助程式函數。若要擷取各個鍵值組，fullQueryString 必須以「&amp;」字元分隔並分割。parameterKey 會參考外掛程式特別嘗試從查詢字串中擷取的查詢字串參數

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

### 2.01 (2019 年 9 月 24 日)

* 小幅變更程式碼以縮小整體大小

### 2.0 (2018 年 4 月 17 日)

* 單點發行 (重新編譯，程式碼大小較小)。
* 新增對 H-Code 和 AppMeasurement 的支援。

### 1.0 (2013 年 9 月 23 日)

* 首次發行。
