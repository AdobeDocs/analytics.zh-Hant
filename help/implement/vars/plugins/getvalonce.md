---
title: getValOnce
description: 防止Analytics變數一列設為相同值兩次。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobe外掛程式：getValOnce

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以協助您從Adobe Analytics中獲得更多價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外掛 `getValOnce` 程式可防止變數多次設定為等於相同值。 Adobe建議您在訪客重新整理頁面或多次瀏覽指定頁面時，使用此外掛程式來去重複資料。 如果您不擔心分析工作區中的「發生次數」度量，就不需要此外掛程式。

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
/* Adobe Consulting Plugin: getValOnce v2.0 */
s.getValOnce=function(vtc,cn,et,ep){if(vtc&&(cn=cn||"s_gvo",et=et||0,ep="m"===ep?6E4:864E5,vtc!==this.c_r(cn))){var e=new Date;e.setTime(e.getTime()+et*ep);this.c_w(cn,vtc,0===et?0:ep);return vtc}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

該方 `getValOnce` 法使用以下引數：

* **`vtc`**（必要，字串）:要檢查的變數，並查看它之前是否設定為相同值
* **`cn`**（可選，字串）:包含要檢查之值的Cookie名稱。 預設為`"s_gvo"`
* **`et`**（可選，整數）:Cookie的過期時間以天(或分鐘，視引數而`ep`定)。 預設為`0`，會在瀏覽器作業結束時過期
* **`ep`**（可選，字串）:僅當設定了引數時`et`才設定此引數。 如果您希望引`"m"`數在幾分鐘內過`et`期，而不是天數，請將此引數設為。 預設為`"d"`，以天為單`et`位設定引數。

如果引 `vtc` 數和Cookie值相符，此方法會傳回空字串。 如果引 `vtc` 數和Cookie值不相符，則方法會將引數傳 `vtc` 回為字串。

## 呼叫範例

### 範例#1

使用此呼叫可防止在接下來30天內，相同值連續傳入s.campaign多次：

```js
s.campaign=s.getValOnce(s.campaign,"s_campaign",30);
```

在上述呼叫中，外掛程式會先比較s_campaign cookie中已包含的值與目前s.campaign變數中的值。   如果未進行比對，外掛程式會將s_campaign cookie設定為來自s.campaign的新值，然後傳回新值。   這種比較會持續30天

### 範例#2

使用此呼叫可防止在整個作業中設定相同的值：

```js
s.eVar2=s.getValOnce(s.eVar2,"s_ev2",0,"m");
```

此程式碼可防止相同值在使用者作業期間連續多次傳入s.eVar2。  它也會忽略參數中的&quot;m&quot;值（在呼叫結束時），因為到期時間設為0。   程式碼也會將比較值儲存在s_ev2 cookie中。

## 版本記錄

### 2.0

* 點數發行（重新編譯，程式碼大小較小）。

### 1.1

* 已新增選項，可透過參數選擇到期的分鐘或 `t` 天。
* 已修正用來 `k` 限制變數僅限外掛程式的變數範圍。 這項變更可防止頁面上其他程式碼的干擾。
