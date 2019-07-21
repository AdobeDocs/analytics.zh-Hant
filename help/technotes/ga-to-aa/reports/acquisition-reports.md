---
title: Adobe Analytics中的贏取報表
description: 瞭解如何使用分析工作區建立贏取型報表。
translation-type: tm+mt
source-git-commit: 71899840dd5b401c6892b6ad5088d4a32fd07042

---


# 贏取報表

「贏取」報表顯示您如何取得網站訪客。

In Adobe Analytics, these reports are known as **Marketing Channels**. 他們需要一些基本的初始設定，但允許更容易自訂的頻道檢視。

> [!IMPORTANT]
>
> 設定行銷渠道處理規則以使用這些報表。See [Getting Started with Marketing Channels](../../../components/c-marketing-channels/c-getting-started-mchannel.md) for information on how to best configure Marketing Channels in your organization.

此頁面假設使用者具備使用分析工作區的基本知識。See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## 所有流量-頻道

顯示訪客用於到達您網站之所有管道的匯總檢視。

1. In the Components menu, locate the **Marketing Channel** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## 所有流量-樹狀圖

顯示頻道流量的樹狀結構。此報表類似於「所有流量-管道」，但以不同方式顯示。

1. 按一下左側的「視覺效果」圖示，然後拖曳樹狀圖視覺化至空白自由表格上方的工作區上。
2. Click the Components icon on the left, then drag the **Marketing Channel** dimension onto the large freeform table area labeled 'Drop a dimension here'.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.
4. 請注意，其他度量會建立額外的樹狀圖。如果只需要一個樹狀圖：
   1. 按一下所需度量的頂端儲存格，代表樹狀結構。
   2. Shift+按一下相同量度欄的最後一個儲存格，以反白標示欄藍色。如果正確完成，視覺化中會顯示一個樹狀結構。
   3. 按一下樹狀圖視覺化右上角的彩色點，然後按一下核取方塊「鎖定選取範圍」。

樹狀圖可套用至任何維度，而不只是行銷管道。

## 所有流量-來源/中型

來源和中型報表顯示驅動網站流量的網域。

* **「來源** 」主要維度可在「分析工作區」中做為 **「反向連結網域** 」維度使用。
* **「分析工作區」中提供「中** 主要維度」做為 **「反向連結類型」** 維度。
* **「關鍵字** 」主要維度可用於「分析工作區」作為 **「搜尋關鍵字** 」維度。

1. 在元件選單中，找出上述所要的維度，並將它拖曳至標示為「拖曳到此處」的大型自由表格區域。
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

如需詳細資訊，請參閱元件使用指南中的下列頁面：

* [反向連結網域](../../../components/c-variables/dimensionslist/reports-referring-domains.md)
* [反向連結類型](../../../components/c-variables/dimensionslist/reports-ref-types.md)
* [搜尋關鍵字](../../../components/c-variables/dimensionslist/reports-search-keywords.md)

## 所有流量-反向連結

* **「來源** 」主要維度可在「分析工作區」中做為 **「反向連結網域** 」維度使用。
* **「著陸頁面** 」主要維度可在「分析工作區」中做為 **「登入頁面** 」維度使用。

1. In the components menu, locate the **Referring Domain** or **Entry Page** dimension and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Referring Domain](../../../components/c-variables/dimensionslist/reports-referring-domains.md) dimension in the Components user guide for more information.

## Google Ads Reports和Search Console報表

Adobe在分析工作區中使用名為Advertising Analytics的功能，引入來自多個平台的廣告和搜尋資料，包括Google。

廣告分析功能需要設定來傳回資料。See [Advertising Analytics Help](../../../integrate/c-advertising-analytics/overview.md) for details on how to enable these additional dimensions in Analysis Workspace.

## Social 報表

除了社交網路之外，Social報表還提供類似於其個別行為報表的資訊。此資料可透過結合維度與區段，在分析工作區中使用。

有時候訪客會在同一工作階段中透過多個管道到達您的網站。例如，訪客點按社交媒體頁面，接著幾分鐘後瀏覽搜尋引擎到達您的網站。在這種情況下，非社交網域可能會出現在此報表中。如果您想要排除非社交網域，請依瀏覽排序報表，或建立區段副本以根據點擊而非瀏覽。See [Segmentation Containers](../../../components/c-segmentation/seg-overview.md) in the Components user guide for more information.

### 社交-網路反向連結

「網路反向連結」報表顯示哪些社交網路網域推動您網站的流量。This data is available in Analysis Workspace using the **Referring Domain** dimension and **Visits from Social Sites** segment.

1. In the Components menu, locate the **Referring Domain** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. In the Components menu, locate the **Visits from Social Sites** segment and drag in onto the small area just above the freeform table labeled 'Drop a segment here'.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

### Social-著陸頁面

「著陸頁面」報告顯示訪客透過社交網路按一下連結後到達的頁面。This data is available in Analysis Workspace using the **Entry Page** dimension and **Visits from Social Sites** segment.

1. In the Components menu, locate the **Entry Page** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. In the Components menu, locate the **Visits from Social Sites** segment and drag in onto the small area just above the freeform table labeled 'Drop a segment here'.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

### 社交-轉換

「轉換」報表會顯示社交網路內容中的電子商務資料。需要額外實施才能在兩個平台上使用這些報告；Adobe建議您與實施顧問合作，以確保「分析工作區」中已正確設定資料。

### Social-外掛程式

「外掛程式」報表顯示訪客如何在您的網站上與內嵌社交媒體外掛程式互動。在分析工作區中需要額外實施。Adobe建議與實施顧問合作，以確保正確收集資料。

### Social-使用者流量

「使用者」流量報告會顯示到達社交網路之訪客的路徑資料。

1. 按一下左側的視覺效果圖示，並拖曳流量視覺化至自由表格上方的工作區上
2. Click the Components icon on the left, then drag the **Visits from Social Sites** segment onto the small area just above the flow visualization labeled 'Drop a Segment here'.
3. Locate the **Pages** dimension, then click the Arrow icon to reveal page values. 維度值是黃色的。
4. 找出所要的頁面值，並將其拖曳至中心中標示為「維度或項目」的空格
5. 此流量報告為互動式報表。按一下任何值，將流量展開至後續或先前頁面。使用右鍵功能表展開或收合欄。也可以在相同的流量報表中使用不同維度。

## 促銷活動-所有

The campaigns report is available in Analysis Workspace using the **Tracking Code** dimension. 請注意，使用追蹤代碼維度需要額外實作來收集資料。

您可以使用自訂變數(eVar)在Adobe Analytics中收集UTM參數。Adobe建議與實施顧問合作，以確保在Adobe Analytics中準確收集追蹤代碼值。

1. In the Components menu, locate the **Tracking Code** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## 促銷活動-付費關鍵字

付費關鍵字報表顯示訪客在訪客點按付費搜尋連結後，如何執行每個關鍵字。The **Search Keywords - Paid** dimension is available in Analysis Workspace, but requires a one-time setup of paid search detection to collect data. See [Paid Search Detection](../../../admin/admin/paid-search-detection/paid-search-detection.md) in the Admin user guide for setup details.

1. In the Components menu, locate the **Search Keyword - Paid** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## 促銷活動-有機關鍵字

有機關鍵字報表顯示在訪客點按來自搜尋引擎的有機搜尋連結後，每個關鍵字的執行方式。The **Search Keywords - Natural** dimension is available in Analysis Workspace. 請注意，如果未設定付費搜尋偵測，此維度會同時收集付費和免費關鍵字。

1. In the Components menu, locate the **Search Keyword - Natural** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## 成本分析

此報告顯示付費行銷管道的瀏覽、成本和收入績效資料。Adobe提供專屬的產品，以提供稱為Adobe Advertising Cloud的見解。如果您的組織有意使用此產品，請聯絡組織的客戶經理。
