---
title: getTimeParting
description: 測量特定動作發生的時間。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adobe 外掛程式：getTimeParting

>[!IMPORTANT] 此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`getTimeParting` 外掛程式可讓您擷取網站上所發生任何可測量活動的時間詳細資訊。若要依指定日期範圍內任何可重複的時間區隔方式來劃分量度，此外掛程式非常有用。例如，您可以比較一週內兩天之間的轉換率，例如所有週日比較所有週四。您也可以比較一天中的時段，例如所有早上比較所有晚上。

Analysis Workspace 提供類似且現成可用的維度，其格式與此外掛程式稍有不同。如需詳細資訊，請參閱分析使用手冊中的[時間分段維度](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md)。有些組織認為 Analysis Workspace 的現成維度已夠用。

>[重要] 此外掛程式的 4.0+ 版與舊版有顯著不同。Adobe 強烈建議您「從頭開始」實施此外掛程式。參考 4.0 版之前外掛程式的程式碼與此外掛程式的目前版本不相容。

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
   * 動作類型：初始化 getTimeParting
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
/* Adobe Consulting Plugin: getTimeParting v6.2 */
var getTimeParting=function(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getTimeParting` 方法使用下列引數：

**`t`** (選用但建議使用，字串)：將訪客的當地時間轉換為該時區的時區名稱。預設為 UTC/GMT 時間。如需有效值的完整清單，請參閱 Wikipedia 上的 [TZ 資料庫時區清單](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)。

常見的有效值包括：

* `"America/New_York"` 為美國東部時間
* `"America/Chicago"` 為美國中部時間
* `"America/Denver"` 為美國山區時間
* `"America/Los_Angeles"` 為美國太平洋時間

呼叫此方法會傳回包含下列內容的字串，並以縱線字元 (`|`) 分隔：

* 當年
* 當月
* 該月某日
* 當週某日
* 當下時間 (AM/PM)

## 呼叫範例

### 特定時區的範例

如果客戶位於法國巴黎，請使用下列範例程式碼：

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

迦納位於 UTC/GMT 時區內。此範例顯示在這類情況下，不需要使用外掛程式引數。

### 針對 Internet Explorer 瀏覽器說明

如果您想從 Internet Explorer 訪客中排除時間分段資料，請使用下列範例 (因為從 IE 瀏覽器傳回的值只能使用訪客的當地時間)

```js
if(!document.documentMode) s.eVarX = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";
```

### 呼叫結果

如果來自科羅拉多州丹佛市的訪客於 2020 年 8 月 31 日上午 9:15 造訪網站，

執行以下程式碼...

```js
s.eVar10 = getTimeParting("Europe/Athens");
```

...會將 s.eVar10 設為等於「year=2020 | month=August | date=31 | day=Friday | time=6:15 PM」

而若執行以下程式碼...

```js
s.eVar10 = getTimeParting("America/Nome");
```

...將 s.eVar10 設為 &quot;year=2020 | month=August | date=31 | day=Friday | time=6:15 AM&quot;

下列程式碼...

```js
s.eVar10 = getTimeParting("Asia/Calcutta");
```

...將 s.eVar10 設為 &quot;year=2020 | month=August | date=31 | day=Friday | time=8:45 PM&quot;

此外，若執行以下程式碼...

```js
s.eVar10 = getTimeParting("Australia/Sydney");
```

...會將 s.eVar10 設為等於 &quot;year=2020 | month=September | date=1 | day=Saturday | time=1:15 AM&quot;

## 版本記錄

### 6.2 (2019 年 11 月 5 日)

* 小錯誤修正
* 縮小整體程式碼大小

### 6.1 (2018 年 11 月 26 日)

* Internet Explorer 瀏覽器的修正。可以傳回時間，但只能使用訪客的當地時間。

### 6.0 (2018 年 8 月 14 日)

* 全面重寫以符合國際標準。現在可適當轉換日光節約時間和所有時區。

### 5.0 (2018 年 4 月 17 日)

* 單點發行 (程式碼經重新編譯且大小較小)
* 移除 `tpDST` 參數的必要性，因為現在會自動偵測日光節約時間的開始/結束日期

### 4.0 (2016 年 8 月 22 日)

* 提供全新的解決方案，現在包含年、月、日資訊。
