---
title: cleanStr
description: 移除或取代字串中所有不必要的字元。
exl-id: d699dcd4-5e0a-40d3-b345-e5b1a077d393
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 82%

---

# Adobe 外掛程式：cleanStr

>[!IMPORTANT]
>
>此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`cleanStr` 外掛程式會移除或取代字串中所有不必要的字元，包括 HTML 標記字元、額外的空格、標籤和新行/歸位字元。它也能以直式單引號 (`'`) 取代左/右單引號 (`‘` 和 `’`)。如果您想從變數值中移除不必要的字元，Adobe建議使用此外掛程式，而Adobe Experience Platform中的「清除文字」功能無法滿足您的實作需求。 如果收集的資料不含不必要的字元，或資料收集UI中的「清除文字」功能已足夠，則不需要此外掛程式。

## 在Adobe Experience Platform中使用標籤安裝外掛程式

Adobe 提供一個擴充功能，可讓您使用最常用的外掛程式。

1. 使用您的AdobeID憑證登入[資料收集UI](https://experience.adobe.com/data-collection)。
1. 按一下所需的屬性。
1. 前往[!UICONTROL 擴充功能]標籤，然後按一下[!UICONTROL 「目錄」]按鈕
1. 安裝並發佈[!UICONTROL 常用 Analytics 外掛程式]擴充功能
1. 如果您尚未執行上述步驟，請使用下列設定建立標示為「初始化外掛程式」的規則：
   * 條件：無
   * 事件：核心 - 已載入程式庫 (頁面頂端)
1. 使用下列設定將動作新增至上述規則：
   * 擴充功能：常用 Analytics 外掛程式
   * 動作類型：初始化 cleanStr
1. 儲存並發佈規則的變更。

## 使用 自訂程式碼編輯器安裝外掛程式

如果您不想使用外掛程式擴充功能，可以使用自訂程式碼編輯器。

1. 使用您的AdobeID憑證登入[資料收集UI](https://experience.adobe.com/data-collection)。
1. 按一下所需的屬性。
1. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 擴充功能底下的[!UICONTROL 「設定」]按鈕。
1. 展開[!UICONTROL 使用自訂程式碼設定追蹤]摺疊式功能表，便會顯示[!UICONTROL 「開啟編輯器」]按鈕。
1. 開啟自訂程式碼編輯器，並將下方提供的外掛程式程式碼貼入編輯視窗中。
1. 儲存並發佈 Analytics 擴充功能的變更。

## 使用 AppMeasurement 安裝外掛程式

Analytics 追蹤物件實例化 (使用 [`s_gi`](../functions/s-gi.md)) 後，將下列程式碼複製並貼到 AppMeasurement 檔案中的任何位置。保留您實作中的程式碼備註和版本號碼，有助於 Adobe 疑難排解任何可能問題。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: cleanStr v2.0 (No Prerequisites Required) */
function cleanStr(str){var a=str;if("-v"===a)return{plugin:"cleanStr",version:"2.0"};a:{if("undefined"!==typeof window.s_c_il){var b=0;for(var c;b<window.s_c_il.length;b++)if(c=window.s_c_il[b],c._c&&"s_c"===c._c){b=c;break a}}b=void 0}"undefined"!==typeof b&&(b.contextData.cleanStr="2.0");if("string"===typeof a){a=a.replace(/<\/?[^>]+(>|$)/g,"");a=a.trim();a=a.replace(/[\u2018\u2019\u201A]/g,"'");a=a.replace(/\t+/g,"");for(a=a.replace(/[\n\r]/g," ");-1<a.indexOf("  ");)a=a.replace(/\s\s/g," ");return a}return""}
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

### 2.0 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### 1.0 (2018 年 4 月 15 日)

* 首次發行。
