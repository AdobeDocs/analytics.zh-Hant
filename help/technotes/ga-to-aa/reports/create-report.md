---
title: 在分析工作區中建立基本報表
description: 瞭解如何在分析工作區中建立以熟悉第三方工具（例如Google Analytics）的使用者為對象的格式的基本報表。
translation-type: tm+mt
source-git-commit: 099662d021c1919f0760e79154536cfd0e23e959

---


# 在分析工作區中為Google Analytics使用者建立基本報表

分析工作區（Adobe Analytics的主要功能之一）為使用者提供強穩的區域，以便對收集的資料取得任何見解。 Google Analytics和Adobe Analytics的報表非常不同：

* Google Analytics中的報表結構可讓您選取特定類型的資料，例如地理位置或反向連結流量。 該平台使用預製式報告檢視，以預期的最佳方式檢視該資料。
* 分析工作區中的報表結構提供空白畫布，提供更彈性的彈性，以符合精確的報表需求。

由於「分析工作區」的運作方式更像畫布，而非預製報表，因此從Google Analytics重新建立報表只需使用正確的視覺化和元件即可。

## Workspace中使用的主要詞語

* **面板** ，是工作區的首要組成部分。 在幾乎所有情況下，都會使用自由面板。
* **視覺化** ，會組成所有自由面板。 其目的是以不同格式呈現資料。 該格式的大多數時間是表格，但其它時間可以是環圈圖或折線圖。 Google Analytics中的許多報表都由兩種視覺化組成：折線圖和自由表格。
* **元件** (Components)會置於視覺化中，以傳回資料。 元件可以以多種不同的方式混合，以符合報告需求。
   * **維度** 是變數值，通常包含文字。 範例包括頁面名稱、反向連結或地理國家。 它們最常列為表格中的列。
   * **量度** 通常表示某個事件或某種類型的轉換。 範例包括常見事件，例如頁面檢視，或更重要的事件，例如購買或註冊。 它們最常被視為表格中的欄，以顯示每個維度發生事件的次數。
   * **區段** 是您資料的子集，其行為與Google Analytics中的區段類似。 它們可讓您建立自訂的篩選，讓您專注在資料的特定部分。
   * **日期範圍** ，可讓您依事件發生時間來組織資料。 它們是隨時間變化的檢視趨勢的骨幹，通常與量度搭配使用。

## 在工作區中建立基本報表

將正確的元件拖曳至工作區畫布，以建立「所有頁面」報表（類似Google Analytics中的報表）。

1. 使用您的 Adobe ID 憑證登入 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
1. 按一下右上角 9 個方塊的圖示，然後按一下 Analytics 彩色標誌。
1. 在上方的導覽列按一下「Workspace」。
1. 按一下「建立新專案」按鈕。
1. 在模組快顯視窗中，確認已選取「空白專案」，然後按一下「建立」。
1. 在左側，會顯示維度、量度、區段和日期範圍的清單。 找到「頁面」維度（彩色橘色），並拖曳至標有「拖曳維度到此處」的畫布上。
1. 您可以看到顯示本月最熱門頁面的報表。 Analysis Workspace automatically populates the report with the [Occurrences](/help/components/c-variables/c-metrics/metrics-occurrences.md) metric.
1. Google Analytics中的表格通常包含7-8個量度。 找到「反彈率」量度（彩色綠色），並拖曳至「發生次數」量度標題旁。 如果您將「反彈率」量度拖曳至「發生次數」旁，兩個量度會並排顯示。
1. 許多量度可以並排放置，方法是拖曳量度至現有量度標題旁。 如需 [如何取得Google Analytics中通常使用之量度的資訊](common-metrics.md) ，請參閱常用量度。

   ![新度量](/help/technotes/ga-to-aa/assets/new_metric.png)

## 從工作區中預先建立的報告範本開始

存取專案範本，以建立「內容使用」範本（類似於Google Analytics中的「所有頁面」報表）。

1. 按一下「建立新專案」按鈕。
1. 找到並連按兩下「所有範本」下方所列的「內容消費(Web)」圖示。
1. 瀏覽每個預先建立的視覺化：登入頁面流量、頂層頁面表格、退出頁面流量、登入網站區域流量和頂層網站區域表格。

   ![範本選擇](/help/technotes/ga-to-aa/assets/content_consumption_template.png)

## 透過工具進行實驗

Analysis Workspace 是報表工具，對於資料收集沒有影響。任意將元件拖曳到專案中查看何者有效，並不會造成任何不良影響。您可以將不同的維度與量度組合拖曳到 Workspace 專案中，了解哪一種組合適合自己。

如果您意外將無效的元件拖曳到 Workspace 專案中，或者想要返回之前的步驟，請按下 ctrl+Z (Windows) 或 cmd+Z (Mac)，藉此還原上一次執行的動作。You can also start with a clean slate by clicking *[!UICONTROL Project]>[!UICONTROL New]*in the upper left menu.

Adobe已將許多功能放入「分析工作區」的右鍵上下文選單中。 大部份的視覺化項目和元件都可以按一下滑鼠右鍵，以取得更詳細的分析和互動功能。 請考慮在工作區中以滑鼠右鍵按一下元件，以查看有哪些可用選項。

## 瞭解要使用的維度和量度

如果您熟悉分析工作區，並想要重新建立通常在Google Analytics中檢視的特定報表，請在其各自的頁面上找到報表：

* [即時報表](realtime-reports.md)
* [觀眾報告](audience-reports.md)
* [贏取報告](acquisition-reports.md)
* [行為報告](behavior-reports.md)
* [轉換報表](conversions-reports.md)
