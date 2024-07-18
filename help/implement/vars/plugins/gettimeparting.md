---
title: getTimeParting
description: 測量特定動作發生的時間。
feature: Variables
exl-id: 3fab36c8-a006-405a-9ef1-2547c2b36b0d
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 77%

---

# Adobe 外掛程式：getTimeParting

{{plug-in}}

`getTimeParting` 外掛程式可讓您擷取網站上所發生任何可測量活動的時間詳細資訊。若要依指定日期範圍內任何可重複的時間區隔方式來劃分量度，此外掛程式非常有用。例如，您可以比較一週內兩天之間的轉換率，例如所有週日比較所有週四。您也可以比較一天中的時段，例如所有早上比較所有晚上。

Analysis Workspace 提供類似且現成可用的維度，其格式與此外掛程式稍有不同。如需詳細資訊，請參閱分析使用手冊中的[時間分段維度](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md)。有些組織認為 Analysis Workspace 的現成維度已夠用。

>[!IMPORTANT]
>
>此外掛程式 4.0+版本與先前版本有顯著的差別。Adobe 強烈建議您「從頭開始」實施此外掛程式。參考 4.0 版之前外掛程式的程式碼與此外掛程式的目前版本不相容。

## 使用Web SDK擴充功能安裝外掛程式

Adobe提供擴充功能，可讓您搭配Web SDK使用最常用的外掛程式。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下左側的&#x200B;**[!UICONTROL 標籤]**，然後按一下所需的標籤屬性。
1. 按一下左側的&#x200B;**[!UICONTROL 擴充功能]**，然後按一下&#x200B;**[!UICONTROL 目錄]**&#x200B;標籤
1. 尋找並安裝&#x200B;**[!UICONTROL 常用Web SDK外掛程式]**&#x200B;擴充功能。
1. 按一下左側的&#x200B;**[!UICONTROL 資料元素]**，然後按一下所需的資料元素。
1. 使用下列設定來設定所需的資料元素名稱：
   * 擴充功能：常見Web SDK外掛程式
   * 資料元素： `getTimeParting`
1. 設定右側的`Time Zone`引數。
1. 儲存並發佈資料元素的變更。

## 手動實作Web SDK安裝外掛程式

此外掛程式尚不支援在Web SDK的手動實作中使用。

## 使用Adobe Analytics擴充功能安裝外掛程式

Adobe提供擴充功能，可讓您搭配Adobe Analytics使用最常用的外掛程式。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往[!UICONTROL 擴充功能]標記，然後按一下[!UICONTROL 「目錄」]按鈕
1. 安裝並發佈[!UICONTROL 常用 Analytics 外掛程式]擴充功能
1. 如果您尚未執行上述步驟，請使用下列設定建立標示為「初始化外掛程式」的規則：
   * 條件：無
   * 事件：核心 - 已載入資料庫 (頁面頂端)
1. 使用下列設定將動作新增至上述規則：
   * 擴充功能：常用 Analytics 外掛程式
   * 動作類型：初始化 getTimeParting
1. 儲存並發佈規則的變更。

## 使用自訂程式碼編輯器安裝外掛程式

如果您不想使用常見Analytics外掛程式擴充功能，可以使用自訂程式碼編輯器。

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
/* Adobe Consulting Plugin: getTimeParting v6.3 (No Prerequisites Needed) */
function getTimeParting(t){var c=t;if("-v"===t)return{plugin:"getTimeParting",version:"6.3"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c){a=b;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.getTimeParting="6.3");c=document.documentMode?void 0:c||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:c,minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getTimeParting` 函數會使用以下引數：

**`t`** (選用但建議使用，字串)：將訪客的當地時間轉換為該時區的時區名稱。預設為 UTC/GMT 時間。如需有效值的完整清單，請參閱 Wikipedia 上的 [TZ 資料庫時區清單](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)。

常見的有效值包括：

* `"America/New_York"` 為美國東部時間
* `"America/Chicago"` 為美國中部時間
* `"America/Denver"` 為美國山區時間
* `"America/Los_Angeles"` 為美國太平洋時間

呼叫此函數會傳回包含下列內容的字串，並以直立線符號 (`|`) 分隔：

* 當年
* 當月
* 該月某日
* 當週某日
* 當下時間 (AM/PM)

## 範例

```js
// Use the following code if the visitor resides in Paris, France
s.eVar8 = getTimeParting("Europe/Paris");

// Use the following code if the visitor resides in San Jose, California
s.eVar17 = getTimeParting("America/Los_Angeles");

// Use the following code if the visitor resides in Ghana.
// Note that Ghana is in GMT time, the default time zone that the plug-in uses with no argument
s.eVar22 = getTimeParting();

// Internet Explorer only returns the visitor's local time. Use this conditional statement to accommodate IE visitors
if(!document.documentMode) s.eVar39 = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";

// Given a visitor from Denver Colorado visits a site on August 31, 2020 at 9:15 AM
// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 PM"
s.eVar10 = getTimeParting("Europe/Athens");

// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 AM"
s.eVar11 = getTimeParting("America/Nome");

// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=8:45 PM"
s.eVar12 = getTimeParting("Asia/Calcutta");

// Returns the string value "year=2020 | month=September | date=1 | day=Saturday | time=1:15 AM"
s.eVar13 = getTimeParting("Australia/Sydney");
```

## 版本記錄

### 6.3 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### 6.2 (2019 年 11 月 5 日)

* 小錯誤修正
* 縮小整體程式碼大小

### 6.1 (2018 年 11 月 26 日)

* Internet Explorer 瀏覽器的修正。這類變數可傳回時間，但只能使用訪客的當地時間。

### 6.0 (2018 年 8 月 14 日)

* 全面重寫以符合國際標準。現在可適當轉換日光節約時間和所有時區。

### 5.0 (2018 年 4 月 17 日)

* 單點發行 (程式碼經重新編譯且大小較小)
* 移除 `tpDST` 參數的必要性，因為現在會自動偵測日光節約時間的開始/結束日期

>[!CAUTION]
>
>此外掛程式的先前版本無法適用未來的所有年份。如果您使用此外掛程式的先前版本，Adobe 強烈建議您升級到最新版本，以避免發生 JavaScript 錯誤和遺失資料。如果升級此外掛程式不可行，請確保外掛程式代碼中的 `s._tpdst` 變數包含未來的適當年份。

### 4.0 (2016 年 8 月 22 日)

* 提供全新的解決方案，現在包含年、月、日資訊。
