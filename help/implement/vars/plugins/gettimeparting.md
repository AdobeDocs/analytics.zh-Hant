---
title: getTimeParting
description: 測量特定動作發生的時間。
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Adobe外掛程式：getTimeParting

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以利您運用Adobe Analytics獲得更大價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外掛 `getTimeParting` 程式可讓您擷取網站上發生任何可測量活動的詳細時間。 當您想要依指定日期範圍內任何可重複的時間劃分量度時，此外掛程式非常有用。 例如，您可以比較一週中兩天之間的轉換率，例如所有週日與所有週四。 您也可以比較一天中的時段，例如所有早晨與所有晚上。

「分析工作區」提供類似的現成可用尺寸，其格式與此外掛程式稍有不同。 如需詳 [細資訊，請參閱](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) 「分析使用指南」中的時間分割維度。 有些組織發現「分析工作區」的現成維度已足夠。

> [重要] ：此外掛程式的4.0+版與舊版有顯著不同。 Adobe強烈建議您「從頭開始」實作此外掛程式。 參照4.0版之前外掛程式的程式碼與此外掛程式的目前版本不相容。

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
/* Adobe Consulting Plugin: getTimeParting v6.2 */
var getTimeParting=function(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

方 `getTimeParting` 法使用下列引數：

**`t`**（可選但建議使用字串）:將訪客的當地時間轉換為的時區名稱。  預設為UTC/GMT時間。 如需[有效值的完整清單，請參閱](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)Wikipedia上的TZ資料庫時區清單。

常見有效值包括：

* `"America/New_York"` 適用於東部時間
* `"America/Chicago"` 適用於中央時間
* `"America/Denver"` 針對山地時間
* `"America/Los_Angeles"` 太平洋時間

呼叫此方法會傳回包含下列字串，並以垂直號(`|`)分隔：

* 本年度
* 當月
* 當月
* 星期幾
* 當前時間(AM/PM)

## 呼叫範例

### 特定時區的範例

如果客戶在法國巴黎，請使用下列范常式式碼：

```js
s.eVarX = getTimeParting("Europe/Paris");
```

如果客戶位於加州聖荷西：

```js
s.eVarX = getTimeParting("America/Los_Angeles");
```

如果客戶在非洲國家迦納：

```js
s.eVarX = getTimeParting();
```

迦納處於UTC/GMT時區內。  此範例顯示在此情況下，不需要外掛程式引數。

### Internet explorer瀏覽器的帳目

如果您想從Internet explorer訪客中排除時間分段資料，請使用下列範例（因為從IE瀏覽器傳回的值只能在訪客的當地時間）

```js
if(!document.documentMode) s.eVarX = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";
```

### 呼叫結果

如果來自科羅拉多州丹佛市的訪客於2020年8月31日上午9:15瀏覽網站，

正在運行以下代碼……

```js
s.eVar10 = getTimeParting("Europe/Athens");
```

...將s.eVar10設為&quot;year=2020&quot;|月=八月| date=31| day=星期五|時間=6:15 PM」

在下列程式碼中……

```js
s.eVar10 = getTimeParting("America/Nome");
```

...將s.eVar10設為&quot;year=2020&quot;|月=八月| date=31| day=星期五|時間=6:15 AM&quot;

下列程式碼……

```js
s.eVar10 = getTimeParting("Asia/Calcutta");
```

...將s.eVar10設為&quot;year=2020&quot;|月=八月| date=31| day=星期五|時間=8:45 PM&quot;

以下代碼……

```js
s.eVar10 = getTimeParting("Australia/Sydney");
```

...將s.eVar10設為&quot;year=2020&quot;|月=九月|日期=1| day=星期六|時間=1:15 AM&quot;

## 版本記錄

### 6.2（2019年11月5日）

* 小錯誤修正
* 降低整體程式碼大小

### 6.1（2018年11月26日）

* Internet explorer瀏覽器的修正。 他們可以傳回時間，但只能在訪客的當地時間傳回。

### 6.0（2018年8月14日）

* 完全改寫以符合國際標準。 現在可適當轉換日光節約和所有時區。

### 5.0（2018年4月17日）

* 點數發行（重新編譯，程式碼較小）
* 已移除對參數的需 `tpDST` 求，因為現在會自動偵測日光節約的開始／結束日期

### 4.0（2016年8月22日）

* 提供全新的解決方案，現在包含年份、月份和日期資訊。
