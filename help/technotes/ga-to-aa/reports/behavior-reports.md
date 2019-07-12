---
title: Adobe Analytics中的行為報告
description: 瞭解如何在Adobe Analytics中建立行為報告
translation-type: tm+mt
source-git-commit: 71899840dd5b401c6892b6ad5088d4a32fd07042

---


# 行為報告

行為報表顯示使用者如何與您的網站互動的資訊。

此頁面假設使用者具備使用分析工作區的基本知識。See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## 行為流程

您可以使用流量視覺化來重新建立行為流程報表。

1. 按一下左側的視覺效果圖示，並拖曳流量視覺化至自由表格上方的工作區上
2. Locate the **Page** dimension, then click the Arrow icon to reveal page values. 維度值是黃色的。
3. 找出所要的頁面值，並將其拖曳至中心中標示為「維度或項目」的空格
4. 此流量報告為互動式報表。按一下任何值，將流量展開至後續或先前頁面。使用右鍵功能表展開或收合欄。也可以在相同的流量報表中使用不同維度。

![流量報表](../assets/flow.png)

## 網站內容-所有頁面

頁面報表顯示網站上個別頁面的績效。

1. In the Components menu, locate the **Pages** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

另外，Adobe提供一些預先建立的工作區，稱為範本。內容消費(Web)範本提供類似於所有頁面報表的值。

1. Click *[!UICONTROL Project] &gt; [!UICONTROL New]*, which opens a modal window with project options.
2. 按一下內容消費(網頁)範本，然後按一下「建立」。

## 網站內容-內容Drill Drill

內容詳細分析報表可讓您查看URL結構的頁面流量。在分析工作區中需要額外實施。Adobe建議與實施顧問合作，以確保正確收集資料。

## 網站內容-著陸頁面

著陸頁面報告會顯示網站上的排名最前的著陸頁面。Landing pages are available in Analysis Workspace as the **Entry Page** dimension.

1. In the Components menu, locate the **Entry Page** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Adobe recommends using the **Visits** metric for this dimension.

## 網站內容-退出頁面

退出頁面報告會顯示成為個人瀏覽最後一頁的排名最前的頁面。它可在相同名稱的分析工作區中使用。

1. In the Components menu, locate the **Exit Page** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Adobe recommends using the **Visits** metric for this dimension.

## 網站速度報告

網站速度報告顯示頁面載入的速度，顯示提高頁面載入時間的機會。

這項功能需要在兩個平台上進行額外的實施；Adobe建議您與實施顧問合作，以確保「分析工作區」中已正確設定資料。[效能計時外掛程式](../../../implement/js-implementation/plugins/performancetiming.md) 通常指派給eVar，以取得Adobe Analytics中的效能資料。

## 網站搜尋報告

網站搜尋報告提供訪客如何使用網站內部搜尋功能的深入分析。

這項功能需要在兩個平台上進行額外的實施；Adobe建議您與實施顧問合作，以確保「分析工作區」中已正確設定資料。通常會從查詢字串參數提取內部搜尋詞，並放入eVar中以進行報告。

## 事件報告

事件在Google和Adobe Analytics之間有一些重大結構差異。兩者都需要額外的實施變更，以便在其個別平台上正常運作。

* 在Google Analytics中，事件會在您的實施中定義為文字。事件有類別、動作和標籤。
* 在Adobe Analytics中，事件首先會在管理控制台中設定，在該處指派識別碼。此識別碼用於實施代碼中。例如:
   1. 您可以將「管理控制台」中的event設定為「註冊」。
   2. 在實施中，您會在註冊確認頁面上的事件變數中加入event1。每次顯示註冊確認頁面時，event就會增加。
   3. 在分析工作區中，「註冊」會以度量的形式出現在任何報表中。

由於此功能需要實施變更，Adobe建議您與實施顧問合作，以確保「分析工作區」正確設定資料。

## 發行者報告

類似Google要求與Google廣告管理員的聯繫，Adobe提供專屬的產品，以提供稱為Adobe Advertising Cloud的見解。如果您的組織有意使用此產品，請聯絡組織的客戶經理。
