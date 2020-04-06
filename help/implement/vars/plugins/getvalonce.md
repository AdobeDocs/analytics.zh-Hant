---
title: getValOnce
description: 防止 Analytics 變數連續設為相同值兩次。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adobe 外掛程式：getValOnce

>[!IMPORTANT] 此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`getValOnce` 外掛程式可防止變數多次設為等於相同值。Adobe 建議您在訪客重新整理頁面或多次造訪指定頁面時，使用此外掛程式來移除重複發生次數。如果您不擔心 Analysis Workspace 中的「發生次數」量度，就不需要此外掛程式。

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
   * 動作類型：初始化 getValOnce
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
/* Adobe Consulting Plugin: getValOnce v2.0 */
s.getValOnce=function(vtc,cn,et,ep){if(vtc&&(cn=cn||"s_gvo",et=et||0,ep="m"===ep?6E4:864E5,vtc!==this.c_r(cn))){var e=new Date;e.setTime(e.getTime()+et*ep);this.c_w(cn,vtc,0===et?0:ep);return vtc}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getValOnce` 方法使用以下引數：

* **`vtc`** (必要，字串)：要檢查的變數，查看它之前是否設為相同值
* **`cn`** (選用，字串)：包含要檢查之值的 Cookie 名稱。預設為 `"s_gvo"`
* **`et`** (選用，整數)：Cookie 的有效期，單位為天 (或分鐘，視 `ep` 引數而定)。預設為 `0`，在瀏覽器作業階段結束時到期
* **`ep`** (選用，字串)：只有在也設定了 `et` 引數時才設定此引數。如果您希望 `et` 引數在幾分鐘內而不是幾天內到期，請將此引數設為 `"m"`。預設為 `"d"`，以天為單位設定 `et` 引數。

如果 `vtc` 引數與 Cookie 值相符，此方法會傳回空字串。如果 `vtc` 引數與 Cookie 值不相符，則方法會將 `vtc` 引數傳回為字串。

## 呼叫範例

### 範例 #1

使用此呼叫可防止接下來 30 天內相同值連續傳入 s.campaign 多次：

```js
s.campaign=s.getValOnce(s.campaign,"s_campaign",30);
```

在上述呼叫中，外掛程式會先比較 s_campaign Cookie 中已包含的值與來自目前 s.campaign 變數的值。如果不相符，外掛程式會將 s_campaign Cookie 設為等於來自 s.campaign 的新值，然後傳回新值。接下來 30 天都會進行這項比較

### 範例 #2

使用此呼叫可防止在整個作業階段中設定相同的值：

```js
s.eVar2=s.getValOnce(s.eVar2,"s_ev2",0,"m");
```

此程式碼可防止使用者作業階段期間將相同的值連續傳入 s.eVar2 多次。它也會忽略 epargument (呼叫結尾處) 中的「m」值，因為到期時間設為 0。此程式碼也會將比較值儲存在 s_ev2 Cookie 中。

## 版本記錄

### 2.0

* 單點發行 (重新編譯，程式碼大小較小)。

### 1.1

* 新增選項，可透過 `t` 參數選擇有效期的分鐘數或天數。
* 修正用來限制 `k` 變數僅限外掛程式使用的範圍。這項變更可防止干擾頁面上的其他程式碼。
