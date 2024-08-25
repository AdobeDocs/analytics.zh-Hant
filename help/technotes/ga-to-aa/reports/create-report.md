---
title: 在 Analysis Workspace 中建立基本報表
description: 瞭解如何在 Analysis Workspace 中建立以熟悉 Google Analytics 等協力廠商工具的使用者為對象之格式的基本報表。
feature: Third-party Integration
exl-id: 513da3f1-ad24-4d5b-bc35-dbcd3694cbdf
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 100%

---

# 在 Analysis Workspace 中建立基本報表 (Google Analytics 使用者適用)

Analysis Workspace (Adobe Analytics 內的主要功能之一) 為使用者提供強大的區域，以便對收集的資料取得任何深入分析。Google Analytics 和 Adobe Analytics 的報表非常不同：

* Google Analytics 中的報表結構可讓您選取特定類型的資料，例如地域位置或反向連結流量。該平台使用預製式報表檢視，根據預期的最佳方式檢視該資料。
* Analysis Workspace 中的報表結構提供空白畫布，擁有更多彈性可符合確切的報表需求。

由於 Analysis Workspace 的運作方式更像畫布，而非預製報表，因此從 Google Analytics 重新建立報表時，只需使用正確的視覺效果和元件即可。

## 工作區中使用的主要詞彙

* **面板**&#x200B;是工作區的首要組成部分。在幾乎所有情況下，都會使用自由面板。
* 所有自由面板都是由&#x200B;**視覺效果**&#x200B;組成。其目的是以不同格式呈現資料。絕大部分的情況下，該格式是表格，但有時候也可以是環圈圖或線條圖。Google Analytics 中的許多報表都是由兩種視覺效果組成：線條圖和自由表格。
* **元件**&#x200B;可放置於視覺效果中，以傳回資料。能以多種不同的方式混合元件，以符合報表需求。
   * **維度**&#x200B;是變數值，且通常包含文字。範例包括頁面名稱、反向連結或地域國家。它們最常列為表格中的列。
   * **量度**&#x200B;通常表示某個事件或某種類型的轉換。範例包括頁面檢視等常見事件，或是購買或註冊這類更重要的事件。它們最常被視為表格中的欄，以顯示每個維度發生之事件的次數。
   * **區段**&#x200B;是您資料的子集，其行為與 Google Analytics 中的區段類似。它們可讓您建立自訂的篩選器，讓您專注在資料的特定部分。
   * **日期範圍**&#x200B;可讓您依事件發生時間來整理資料。它們是隨時間變化之檢視趨勢的骨幹，通常與量度搭配使用。

## 在工作區中建立基本報表

將正確的元件拖曳至工作區畫布，以建立「所有頁面」報表 (類似 Google Analytics 中的報表)。

1. 使用您的 Adobe ID 認證登入 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
1. 按一下右上角 9 個方塊的圖示，然後按一下 Analytics 彩色標誌。
1. 在上方的導覽列按一下「工作區」。
1. 按一下「建立新專案」按鈕。
1. 在模組快顯視窗中，確認已選取「空白專案」，然後按一下「建立」。
1. 左側會顯示含有維度、量度、區段和日期範圍的清單。找出「頁面」維度 (顯示為橙色)，將該維度拖曳至畫布上標示「將維度放置在此處」的位置。
1. 您會看到顯示本月最上層頁面的報表。Analysis Workspace 會自動在報表中填入[發生次數](/help/components/metrics/occurrences.md)量度。
1. Google Analytics 中的表格通常包含 7-8 個量度。找出「跳出率」量度 (顯示為綠色)，並將該量度拖曳至「發生次數」量度標頭旁。如果將「跳出率」量度拖曳到「發生次數」旁，兩個量度會並排顯示。
1. 許多量度可以並排放置，方法是將量度拖曳至現有量度標頭旁。如需如何取得 Google Analytics 中[經常使用之量度](common-metrics.md)的相關資訊，請參閱常用量度。

   ![新增量度](/help/technotes/ga-to-aa/assets/new_metric.png)

## 從在工作區中預先建立的報表範本開始

存取專案範本，以建立「內容使用」範本 (類似 Google Analytics 中的「所有頁面」報表)。

1. 按一下「建立新專案」按鈕。
1. 找出並連按兩下「所有範本」下方所列的「內容使用 (網頁)」圖示。
1. 瀏覽每個預先建立的視覺效果：「登入頁面流量」、「最上層頁面表格」、「退出頁面流量」、「登入網站區域流量」和「最上層網站區域表格」。

   ![範本選取](/help/technotes/ga-to-aa/assets/content_consumption_template.png)

## 透過工具進行實驗

Analysis Workspace 是報表工具，對於資料收集沒有影響。任意將元件拖曳到專案中查看何者有效，並不會造成任何不良影響。您可以將不同的維度與量度組合拖曳到工作區專案中，瞭解哪一種組合適合自己。

如果您意外將無效的元件拖曳到 Workspace 專案中，或者想要返回之前的步驟，請按下 ctrl+Z (Windows) 或 cmd+Z (Mac)，藉此還原上一次執行的動作。您也可以按一下左上方功能表中的&#x200B;*[!UICONTROL 「專案] > [!UICONTROL 新專案」]*，以空白顯示窗開始操作。

Adobe 已將許多功能放入 Analysis Workspace 的滑鼠右鍵內容功能表中。大部份的視覺效果和元件都可以按一下滑鼠右鍵，以取得更詳細的分析和互動功能。請考慮在工作區中以滑鼠右鍵按一下元件，以查看有哪些可用選項。

## 瞭解要使用的維度和量度

如果您熟悉 Analysis Workspace，並想要重新建立通常在 Google Analytics 中檢視的特定報表，請在其各自的頁面上找出報表：

* [即時報表](realtime-reports.md)
* [客群報告](audience-reports.md)
* [贏取報表](acquisition-reports.md)
* [行為報表](behavior-reports.md)
* [轉換報表](conversions-reports.md)
