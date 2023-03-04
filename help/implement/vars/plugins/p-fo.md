---
title: p_fo (僅限頁面優先)
description: 確保每頁只引發一次特定常式。
feature: Variables
exl-id: e82d77f9-2ea9-4b1b-b645-b12879c344ec
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 100%

---

# Adobe 外掛程式：p_fo (僅限頁面優先)

{{plug-in}}

`p_fo` 外掛程式是公用程式，可檢查特定 JavaScript 物件是否存在。如果物件不存在，外掛程式將會建立該物件並傳回 `true`。如果頁面上已存在 JavaScript 物件，則會傳回 `false`。若要在頁面上執行一次程式碼，此外掛程式很實用。其他多個外掛程式依賴此程式碼才能運作。如果您不擔心某個頁面上程式碼執行的次數，或不使用任何相依的外掛程式，就不需要這個外掛程式。

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize p_fo
1. Save and publish the changes to the rule.-->

## 使用自訂程式碼編輯器安裝外掛程式

如果您不想使用外掛程式擴充功能，可以使用自訂程式碼編輯器。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的屬性。
1. 前往[!UICONTROL 擴充功能]索引標籤，然後按一下 Adobe Analytics 擴充功能底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
1. 展開[!UICONTROL 使用自訂程式碼設定追蹤]摺疊式功能表，便會顯示[!UICONTROL 「開啟編輯器」]按鈕。
1. 開啟自訂程式碼編輯器，並將下方提供的外掛程式程式碼貼入編輯視窗中。
1. 儲存並發佈 Analytics 擴充功能的變更。

## 使用 AppMeasurement 安裝外掛程式

Analytics 追蹤物件實例化 (使用 [`s_gi`](../functions/s-gi.md)) 後，將下列程式碼複製並貼到 AppMeasurement 檔案中的任何位置。保留您實作中的程式碼備註和版本號碼，有助於 Adobe 疑難排解任何可能問題。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v3.0 (Requires AppMeasurement) */
function p_fo(c){if("-v"===c)return{plugin:"p_fo",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c){a=b;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.p_fo="3.0");window.__fo||(window.__fo={});if(window.__fo[c])return!1;window.__fo[c]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`p_fo` 函數會使用以下引數：

* **on** (必要，字串)：外掛程式所建立的 JavaScript 物件名稱 (如果頁面上尚未存在此物件)。

如果此物件尚未存在，則此函數會傳回 `true` 並建立該物件。 如果此物件已存在，則此函數會傳回 `false`。

## 呼叫範例

### 範例 #1

以下程式碼將檢查頁面中是否存在「myobject」物件。如果「myobject」物件不存在，則程式碼會建立「myobject」物件並傳回 true 值。因此，條件陳述式中的程式碼 (即 Console.log(&#39;hello&#39;);) 將會執行。

另一方面，如果 p_fo 呼叫發生時「myobject」物件已存在，p_fo 函數便會傳回 false 值，因此條件陳述式會被視為 false。在這種情況下，條件陳述式中的程式碼將不會執行。

```js
if(p_fo("myobject"))
{
  console.log("hello");
}
```

**注意：**&#x200B;每當新頁面物件/DOM 載入 (或目前頁面重新載入) 時，on 引數中指定的物件就不再存在，因此在頁面載入完成後 p_fo 外掛程式初次執行時，會再次傳回 true。

## 版本記錄

### 3.0 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### 2.0

* 單點發行 (重新編譯，程式碼大小較小)。
* 將傳回值類型從整數變更為布林值

### 1.0

* 首次發行。
