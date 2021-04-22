---
title: p_fo (僅限頁面優先)
description: 確保每頁只引發一次特定常式。
exl-id: e82d77f9-2ea9-4b1b-b645-b12879c344ec
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '628'
ht-degree: 100%

---

# Adobe 外掛程式：p_fo (僅限頁面優先)

>[!IMPORTANT]
>
>此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`p_fo` 外掛程式是公用程式，可檢查特定 JavaScript 物件是否存在。如果物件不存在，外掛程式將會建立該物件並傳回 `true`。如果頁面上已存在 JavaScript 物件，則會傳回 `false`。若要在頁面上執行一次程式碼，此外掛程式很實用。其他多個外掛程式依賴此程式碼才能運作。如果您不擔心某個頁面上程式碼執行的次數，或不使用任何相依的外掛程式，就不需要這個外掛程式。

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
   * 動作類型：初始化 p_fo
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
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v3.0 (Requires AppMeasurement) */
function p_fo(c){if("-v"===c)return{plugin:"p_fo",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c){a=b;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.p_fo="3.0");window.__fo||(window.__fo={});if(window.__fo[c])return!1;window.__fo[c]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`p_fo` 方法使用以下引數：

* **on** (必要，字串)：頁面上尚未存在物件時，外掛程式所建立的 JavaScript 物件之名稱。

如果物件尚不存在，則此方法會傳回 `true` 並建立該物件。如果物件已存在，則此方法會傳回 `false`。

## 呼叫範例

### 範例 #1

以下程式碼將檢查頁面中是否存在「myobject」物件。如果「myobject」物件不存在，則程式碼會建立「myobject」物件並傳回 true 值。因此，條件陳述式中的程式碼 (即 Console.log(&#39;hello&#39;);) 將會執行。

另一方面，如果 p_fo 呼叫發生時「myobject」物件已存在，p_fo 函數便會傳回 false 值，因此條件陳述式會被視為 false。在這種情況下，條件陳述式中的程式碼將不會執行。

```javascript
if(s.p_fo("myobject"))
{
  console.log("hello");
}
```

**注意：**&#x200B;每當新頁面物件/DOM 載入 (或目前頁面重新載入) 時，on 引數中指定的物件就不再存在，因此在頁面載入完成後 p_fo 外掛程式第一次執行時，會再次傳回 true。

## 版本記錄

### 3.0 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### 2.0

* 單點發行 (重新編譯，程式碼大小較小)。
* 將傳回值類型從整數變更為布林值

### 1.0

* 首次發行。
