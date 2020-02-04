---
title: p_fo（僅限頁面優先）
description: 確保每頁只觸發一次特定常式。
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Adobe外掛程式：p_fo（僅限頁面優先）

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以利您運用Adobe Analytics獲得更大價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外 `p_fo` 掛程式是一個公用程式，可檢查特定JavaScript物件是否存在。 如果對象不存在，則插件將建立該對象並返回 `true`。 如果頁面上已存在JavaScript物件，則會傳回該物件 `false`。 此外掛程式可讓您在頁面上執行一次程式碼。 其他數種外掛程式則仰賴此程式碼運作。 如果您不擔心某個頁面上執行程式碼的次數，或不使用任何相依的外掛程式，就不需要這個外掛程式。

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
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

該方 `p_fo` 法使用以下引數：

* **on** （必要，字串）:外掛程式在頁面上尚未存在時所建立的JavaScript物件名稱。

如果對象尚不存在，則此方法返回並 `true` 建立該對象。 如果對象已存在，則此方法返回 `false`。

## 呼叫範例

### 範例#1

以下代碼將檢查頁面中是否存在&quot;myobject&quot;對象。  如果&quot;myobject&quot;物件不存在，則程式碼會建立&quot;myobject&quot;物件並傳回true值。  因此，條件陳述式中的程式碼(即Console.log(&#39;hello&#39;);)將會執行。

另一方面，如果p_fo呼叫發生時&quot;myobject&quot;物件已存在，則p_fo函式會傳回false值，因此條件陳述式會被視為false。  在這種情況下，條件陳述式中的程式碼將不會執行。

```javascript
if(s.p_fo("myobject"))
{
  console.log("hello");
}
```

**** 注意：每當新頁面物件/DOM載入（或目前頁面重新載入）時，on引數中指定的物件將不再存在，因此p_fo外掛程式會在頁面載入完成後第一次執行時再次傳回true。

## 版本記錄

### 2.0

* 點數發行（重新編譯，程式碼大小較小）。
* 將傳回值類型從整數變更為布林值

### 1.0

* 首次發行。
