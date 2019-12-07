---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---



# 清單 Prop

清單 prop 是一份使用分隔字元的值清單，會在傳入至變數後，以個別明細項目的形式來報告。清單 prop 最常在含有使用者可選值的頁面上實施，例如具有核取方塊或選項按鈕的清單項目。清單 prop 在任何您需要於一個變數中定義多個值，但不想傳送多個影像要求的情況下皆適用。


<!-- 

list_props.xml

 -->

**考量事項**

* 清單 prop 只能對流量變數 ([prop](/help/implement/js-implementation/page-variables/propn.md)) 啟用。
* 您無法為清單 prop 啟用路徑分析和關聯。
* 幾乎每個報表都可獲得 Analytics 提供的瀏覽和獨特訪客資料，包括所有的清單 prop 報表在內。
* 清單 prop 支援分類功能。
* 任何自訂流量變數皆可成為清單 prop(例外: [pageName](/help/implement/js-implementation/page-variables/pagename.md)、[channel](/help/implement/js-implementation/page-variables/channel.md) 和 [server](/help/implement/js-implementation/page-variables/server.md))。

* 在相同的影像要求中定義重複值時，不會對例項進行重複資料刪除。

在「管理工具 &gt; 報表套裝 &gt; 流量變數」頁面上啟用「清單支援」接著選取分隔字元，即可將 Prop 變更為清單 Prop。常用的分隔字元有冒號、分號、逗號或垂直線。技術上而言，分隔字元可以是前 127 個 ASCII 字元中的任一個。

**實施範例**

在要求啟用清單 prop 時，請指定您要使用的分隔字元。在啟用您所選擇的&#x200B;*`s.prop`* 後，您可以在此變數中設定多個值，如下列範例所示:

以垂直線分隔的清單 prop，會傳入兩個值:

```js
s.prop1="Banner ad impression|Sidebar impression"
```

以逗號分隔的清單 prop，會傳入數個值:

```js
s.prop2="cerulean,vermilion,saffron"
```

清單 prop 也可以傳送單一值:

```js
s.prop3="Single value"
```

分隔字元可隨時變更。但實施必須符合新的分隔字元。若未使用正確的分隔字元，將使清單 prop 值在報表中被視為連結的單一明細項目。

由於清單 prop 仍屬於流量變數，因此仍受流量變數限制的規範。清單 prop 限定為 100 個位元組的資料，並且會受到區分大小寫設定的影響。

