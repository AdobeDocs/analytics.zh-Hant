---
title: 自由表格
description: 瞭解自由表格和自由表格產生器
translation-type: tm+mt
source-git-commit: ce06a5ca2caeb266c729947c76e93c611502e6d9

---


# 自由表格

在分析工作區中，自由表格不僅是資料表格，也是互動式視覺化。 您可以將元件組合拖放 [至行](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) 和欄，以建立自訂表格供您分析。 每個元件被丟棄時，表格會立即更新，以便您進行快速分析。

可以通過多種方式自定義表：

* **「行」**
   * 每個維度列在分頁之前最多可顯示400列。 您可以調整專案的檢視密度，將更多列放入單一畫 [面中](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html)。
   * 行可以按其他元件劃分。 若要一次劃分多列，只需選取多列，然後將下一個元件拖曳至選取的列上。 進一步瞭解划 [分](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html)。
   * 可以篩選 [行](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/pagination-filtering-sorting.html) ，以顯示縮減的項目集。 「列設定」下方提供其 [他設定](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/table-settings.html)。

* **「欄」**
   * 元件可堆疊在欄內，以建立分段量度、跨標籤分析等。
   * 每個欄的檢視都可在欄設定下 [調整](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html)。
   * 您可透過右鍵功能表 [使用數個動作](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html)。 根據您按一下表頭、行或列，菜單提供不同的操作。

## 自由表格產生器

如果您偏好先將數個元件新增至表格，然後再轉譯資料，則可啟用「自由表格產生器」。 啟用建立工具後，您可以拖放許多維度、劃分、度量和區段，以建立可回答更複雜問題的表格。 資料不會即時更新，只要您按一下「建立」，資料就會 **[!UICONTROL 更新]**。

當您有複雜的資料問題需要詢問，而且您想要建立表格來回答您的問題時，表格產生器是節省時間的選項。 表格產生器的其他優點包括：

* 以您所需的確切格式排清單格，毋需等待每個動作轉譯。
* 快速執行最多4個劃分層級。
* 定義每個表格列和維度欄的「列」和「劃分」設定。
* **[!UICONTROL 依預設]**，依表格各層級的「位置」劃分(在傳統的「自由表格」中，預設值為「依**[!UICONTROL &#x200B;項目劃分]**」)。
* 手動對表中的靜態行排序。 例如，如果您想要量度列以特定順序顯示。
* 在轉譯實際資料之前，先預覽表格格式。

觀看「自由表格產生器」的實際 [運作](https://youtu.be/GUMWiJAmMGI)。

## 匯出自由表格資料

自由表格中的資料可透過下列幾種方式從分析工作區複製：

* 按一下右鍵表標題，然後選擇「復 **[!UICONTROL 制到剪貼簿」]**。 這將導出完整（可見）表。
* 反白顯示表格中的特定儲存格，按一下滑鼠右鍵並選取「複製 **[!UICONTROL 至剪貼簿]**」，或使用Ctrl + c快速鍵。
* **[!UICONTROL 「專案>下載CSV]**」。 這會將專案中所有可見的表格匯出為CSV。
