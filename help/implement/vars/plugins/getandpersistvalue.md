---
title: getAndPersistValue
description: 儲存值，以便稍後隨時擷取。
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe外掛程式：getAndPersistValue

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以協助您從Adobe Analytics中獲得更多價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外 `getAndPersistValue` 掛程式可讓您將值儲存在Cookie中，以便稍後在瀏覽期間擷取。 它的角色與Adobe Experience Platform Launch的「 [!UICONTROL 儲存持續] 」功能類似。 如果您想在設定變數後，在後續的點擊中自動將Analytics變數保留為相同值，Adobe建議使用此外掛程式。 如果啟動的「儲存持續時間  」功能已足夠，或者您不需要在後續點擊中將變數設定並保留至相同值，則不需要此外掛程式。 eVar的內建永續性不需要使用此外掛程式，因為這些變數會由Adobe在伺服器端持續存在。

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
   * 動作類型：初始化getAndPersistValue
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
/* Adobe Consulting Plugin: getAndPersistValue v2.0 */
s.getAndPersistValue=function(vtp,cn,ex){var b=new Date;cn=cn?cn:"s_gapv";(ex=ex?ex:0)?b.setTime(b.getTime()+864E5*ex): b.setTime(b.getTime()+18E5);vtp||(vtp=this.c_r(cn));this.c_w(cn,vtp,b);return vtp};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

該方 `getAndPersist` 法使用以下引數：

* **`vtp`**（必要）:要在頁面之間持續存留的值
* **`cn`**（可選）:儲存值的Cookie名稱。 如果未設定此引數，則會命名Cookie`"s_gapv"`
* **`ex`**（可選）:Cookie過期的天數。 如果此引數`0`已設定或未設定，Cookie會在瀏覽結束時過期（閒置30分鐘）。

如果已設定引 `vtp` 數中的變數，則外掛程式會設定Cookie，然後傳回Cookie值。 如果未設定引 `vtp` 數中的變數，則外掛程式只會傳回Cookie值。

## 範例

### 範例#1

下列程式碼會將eVar21設定為等於&quot;hello&quot;的值。  接著，程式碼會設定ev21gapv Cookie，其將於28天後到期，等於eVar21的值(即&quot;hello&quot;)。  然後程式碼會（重新）將eVar21設定為ev21gapv cookie的值。

```js
s.eVar21 = "hello";
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 範例#2

假設eVar21尚未設定在目前頁面上，但在過去28天內設定為等於上一頁的「hello」。   下列程式碼只會將eVar21設定為等於ev21gapv cookie的值(即&quot;hello&quot;)。  它不會重設ev21gapv Cookie，因為在呼叫函式之前，eVar21未在目前頁面上設定。

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 範例#3

假設eVar21尚未設定在目前頁面上，但在過去28天內設定為等於上一頁的「hello」。  下列程式碼僅會將prop35設為ev21gapv cookie的值(即&quot;hello&quot;)。  它不會設定eVar21。

```js
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 範例#4

下列程式碼會將eVar21設定為等於&quot;howdy&quot;的值。  然後，程式碼會設定（或重設）ev21gapv Cookie，其將於28天後到期，等於eVar21的值(即&quot;howdy&quot;)。  然後，程式碼會將prop35設定為ev21gapv cookie的值(即&quot;howdy&quot;)。

```js
s.eVar21 = "howdy";
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 範例#5

假設s.eVar21在過去28天內未在任何頁面上設定。  下列程式碼會將s.eVar21設定為無值，因為ev21gapv cookie會在上次設定後28天過期。

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 範例#6

下列程式碼會將eVar30設為「shopping」。  接著，它會設定s_gapv Cookie，此Cookie將在瀏覽器作業結束時過期，等於s.eVar30的值(即「購物」)。  然後，它會將s.eVar30設定為s_gapv cookie的值（亦即getAndPersistValue呼叫會傳回s_gapv cookie的值，在此例中為「shopping」）。

```js
s.eVar30 = "shopping";
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

如果s.eVar30未設定為作業階段期間檢視之任何其他頁面上的明確值，但是透過下列程式碼設定（在doPlugins中）。..

```js
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

...s.eVar30將設為「shopping」（即s_gapv cookie的持續值）

## 版本記錄

### 2.0（2018年4月16日）

* 點數發行（較小的程式碼大小）
* 現在，將0傳入 `ex` 引數中會強制在閒置30分鐘後過期，而非在瀏覽器作業結束時過期。

### 1.0（2016年1月18日）

* 首次發行。
