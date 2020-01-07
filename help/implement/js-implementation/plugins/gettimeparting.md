---
description: getTimeParting 外掛程式會在自訂變數中填入小時、星期幾、週末與工作日等自訂變數。Analysis Workspace 提供立即可用的時間分段維度。當 Analysis Workspace 之外的其他 Analytics 解決方案需要使用時間分段維度時，應使用此外掛程式。
keywords: Analytics Implementation
subtopic: Plug-ins
title: getTimeParting
topic: Developer and implementation
uuid: 74f696a3-7169-4560-89b2-478b3d8385e1
translation-type: tm+mt
source-git-commit: 73d20b23e38bc619c156c418c95096a94d2fdfce

---


# getTimeParting

getTimeParting外掛程式提供完整的分析解決方案，可讓您擷取網站上發生任何可測量活動的詳細時間。

如果您想要依指定日期範圍內任何可重複的時間劃分來劃分量度，則應使用getTimeParting外掛程式。  例如，getTimeParting外掛程式可讓您比較一週中兩天（例如所有週日與所有週四）、一天中兩個不同時段（例如所有上午與所有晚上），或甚至兩分鐘後（例如所有10:00 AM例項與所有10:01 AM例項）的轉換率您在報表中指定的日期範圍。

[!DNL Analysis Workspace] 提供類似的現成可用維度，其格式與此外掛程式的格式略有不同(請參 [閱](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.html))。  Adobe Consulting建議您閱讀本說明章節的其餘部分，以判斷此外掛程式是否以更符合您需求的方式提供資料。

如果您不需要依特定日期範圍的可重複時間劃分量度，則不需要使用getTimeParting外掛程式。  此外，如果您發現「時 [!DNL Analysis Workspace] 間分割維度」足夠，則不需要實作此外掛程式。

>[!CAUTION] getTimeParting外掛程式4.0+版提供的解決方案與舊版外掛程式提供的解決方案大不相同。  如果您選擇從4.0之前的版本升級，您應「從頭開始」實作解決方案。  換言之，您應設定全新的eVar —— 一個eVar —— 以保存外掛程式提供的資料，並在實作解決方案之前仔細閱讀本檔案。

>[!CAUTION] 此外：此版本的外掛程式與 *Microsoft Internet* explorer瀏覽器不完全相容，但外掛程式與Microsoft edge瀏覽器完全相容。   使用Internet explorer的訪客將可提供時間，但只能在其本地 *時區* ，而不能轉換為您指定的時區。  請參閱下列範例，以取得不會包含Internet explorer瀏覽器資料，但仍會說明其存在狀況的解決方案。

> [!NOTE]下列指示會要求您變更網站上的資料收集程式碼。此動作可能會影響到您網站上的資料收集，因此應由懂得使用及實施 [!DNL Analytics] 的開發人員執行。

> [!WARNING] 在部署至生產環境之前，請務必先測試所有外掛程式實作，以確保資料收集如預期般運作。

## 必備條件

無

## 實施方式

* 複製+貼上下列程式碼至AppMeasurement程式碼之「外掛程式」區段內的任意位置：

```function getTimeParting(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])}```

> [!NOTE] 您也可以使用Adobe Launch等標籤管理程式來部署外掛程式程式程式碼，而不需將它附加至AppMeasurement或任何其他分析解決方案

* 如下所述，在doPlugins函式中或您需要擷取時間分割資料的任何其他位置執行getTimeParting函式

**要傳入的參數**

* t:(**可選**，但建議使用字串)將訪客的當地時間轉換為的時區名稱。  預設為「Etc/GMT」，或未設定時的UTC/GMT時間。  請造 [訪https://en.wikipedia.org/wiki/List_of_tz_database_time_zones] ，以取得要輸入的完整值清單。

常見值包括：

* 東部時間的&quot;America/New_York&quot;
* 《美洲／芝加哥》(America/Chicago)
* 《美洲／丹佛》
* 太平洋時間的&quot;美國／洛杉磯&quot;

## 傳回

getTimeParting外掛程式會傳回包含下列項目的字串：

* 本年度
* 當月
* 目前日期（即當月的某天）
* 當天（即一週中的某天）
* 當前時間（非軍事時間）

上述各項目均以垂直號(&quot;|&quot;)字元分隔。

## 呼叫範例

如果您位於法國巴黎，且想要使用eVar10（在Adobe Analytics中）來擷取時間分段資料，請使用下列程式碼：

```s.eVar10 = getTimeParting("Europe/Paris")```

如果您位於加州聖荷西，請使用下列程式碼：

```s.eVar10 = getTimeParting("America/Los_Angeles")```

如果您位於非洲國家的迦納，請使用下列程式碼：

```s.eVar10 = getTimeParting();```

迦納處於UTC/GMT時區內。  因此，此示例說明在這種情況下不需要插件引數。

如果您位於紐約且不想包含來自Internet explorer訪客的資料，請使用下列程式碼（因為IE瀏覽器傳回的值只能在訪客的當地時間提供）

```if(!document.documentMode) s.eVar10 = getTimeParting("America/New_York");```
```else s.eVar10 = "Internet Explorer Visitors";```

**呼叫結果**

如果來自科羅拉多州丹佛市的訪客於2020年8月31日上午9:15瀏覽網站，請使用下列程式碼……

```s.eVar10 = getTimeParting("Europe/Athens");```

...會將s.eVar10設為 **year=2020|月=八月| date=31| day=星期一|時間=6:15 PM**

下列程式碼……

```s.eVar10 = getTimeParting("America/Nome");```

...會改為將s.eVar10設為 **year=2020|月=八月| date=31| day=星期一|時間=6:15 AM**

下列程式碼……

```s.eVar10 = getTimeParting("Asia/Calcutta");```

...會改為將s.eVar10設為 **year=2020|月=八月| date=31| day=星期一|時間=8:45 PM**

下列程式碼……

```s.eVar10 = getTimeParting("Australia/Sydney");```

...會改為將s.eVar10設為 **year=2020|月=九月|日期=1| day=星期二|時間=1:15 AM**

## Adobe Analytics設定

如果您想在Adobe Analytics中擷取時間分段資料，請設定具有下列特性的新eVar:

* 名稱：時間分割
* 配置：最近（最後一個）
* 過期時間：瀏覽
* 所有其他屬性使用提供的預設值
