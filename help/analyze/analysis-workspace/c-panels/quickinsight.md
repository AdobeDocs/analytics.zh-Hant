---
description: 「快速洞察」建立工具是適用於新工作區使用者的工具，可引導他們建立資料表格和視覺化
title: 快速洞察建立工具
translation-type: tm+mt
source-git-commit: 0bf00f990a34768b93cef5d57a126ebe93087e91

---


# 快速洞察建立工具

>[!IMPORTANT]
>
>**[!UICONTROL Quick Insights]** 目前測試有限，目前尚未向所有Adobe Analytics客戶提供。

[!UICONTROL Quick Insights] 為非分析師和新使用者提供指引，以 [!UICONTROL Analysis Workspace] 瞭解如何快速輕鬆地回答業務問題。 對於想要快速回答簡單問題而不需要自行建立表格的進階使用者而言，它也是絕佳的工具。

當您第一次使用此功能 [!UICONTROL Analysis Workspace]時，可能會想知道哪些視覺化最有用、哪些維度和量度可促進深入資訊、拖放項目的位置、建立區段的位置等。

為協助您，並根據您公司在中的資料元件使用情況 [!UICONTROL Analysis Workspace], [!UICONTROL Quick Insights] 運用演算法來呈現您公司使用的最熱門維度、量度、區段和日期範圍。

[!UICONTROL Quick Insights] 幫助您

* 正確建立資料表格及隨附的視覺化 [!UICONTROL Analysis Workspace]。
* 瞭解基本元件和部分的術語和辭彙 [!UICONTROL Analysis Workspace]。
* 進行維度的簡單劃分、新增多個量度，或輕鬆在內部比較區段 [!UICONTROL Freeform table]。
* 變更或試用各種視覺化類型，以快速且直覺式的方式尋找分析的尋找工具。

## 基本關鍵術語

以下是您需要熟悉的一些基本辭彙。 每個資料表格包含2個或多個您用來述說資料故事的建置區塊（元件）。

| 構件（元件） | 定義 |
|---|---|
| [!UICONTROL Dimension] | 維度是量度資料的說明或特性，可在專案中檢視、劃分和比較。 它們是非數值和日期，可劃分為維度項目。 例如，「瀏覽器」或「頁面」是維度。 |
| [!UICONTROL Dimension item] | 維度項目是維度的個別值。 例如，瀏覽器維度的維度項目為「Chrome」、「Firefox」、「Edge」等。 |
| [!UICONTROL Metric] | 量度是有關訪客活動的量化資訊，例如瀏覽次數、點進、重新載入、平均逗留時間、件數、訂購、收入等。 |
| [!UICONTROL Visualization] | 工作區 [提供許多視覺化](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md) ，以建立資料的視覺化表示法，例如長條圖、環圈圖、直方圖、折線圖、地圖、散點圖等。 |
| [!UICONTROL Breakdown] | 劃分是將維度依其他維度劃分的一種方式。 在我們的範例中，您可以依行動裝置來劃分美國各州，以取得每個州的行動裝置瀏覽次數，或依行動裝置類型、地區、內部促銷活動等來劃分行動裝置。 |
| [!UICONTROL Segment] | 區段可讓您根據特性或網站互動來識別訪客的子集。 例如，您可以根據屬 [!UICONTROL Visitor] 性建立區段：瀏覽器類型、裝置、瀏覽次數、國家、性別或根據互動：促銷活動、關鍵字搜尋、搜尋引擎，或根據退出點和登入點：來自Facebook、已定義登陸頁面、反向連結網域或自訂變數的訪客：表單欄位、定義的類別、客戶ID。 |

## 快速洞察入門

1. 使用您所提供的認證登入Adobe Analytics。
1. 前往並 [!UICONTROL Workspace] 按一下 **[!UICONTROL Create New Project]** ，然後按一下 **[!UICONTROL Quick Insights]**。

   ![](assets/qibuilder.png)

1. 當您第一次開始時，請進行簡短的教學課程，教您一些基本 [!UICONTROL Quick Insights panel] 概念。 或者，按一下 **[!UICONTROL Skip Tutorial]**。
1. 選擇您的構建塊（也稱為元件）:維度（橘色）、量度（綠色）、區段（藍色）或日期範圍（紫色）您必須為要自動建立的表格至少選擇一個維度和一個量度。

   ![](assets/qibuilder2.png)

   您有三種選擇構造塊的方法：
   * 從左側導軌拖放。
   * 如果您知道您要尋找的是：開始輸入 [!UICONTROL Quick Insights] 內容，然後為您填空。
   * 按一下下拉式清單並搜尋清單。

1. 當您新增至少一個維度和一個量度時，將會為您建立下列項目：

   * 自由表格，其上方為垂直維度（此處為美國州）和水準度量（此處為瀏覽）。 查看下表：
   ![](assets/qibuilder3.png)

   * 隨附的視覺化，在此例中為長 [條圖](/help/analyze/analysis-workspace/visualizations/bar.md)。 產生的視覺化是根據您新增至表格的資料類型。 您可以按一下旁邊的下拉箭頭，以變更視覺化類型 **[!UICONTROL Bar]**。


1. （可選）按一下維度旁的>向右箭頭，以深入檢視維度項目。

1. 嘗試在「其他實用選項」下新增一些更精簡的功能。

## 其他實用選項

其他有用的提示會出現在中， [!UICONTROL Quick Insights Builder]其中一些提示會視您的最後動作而定。

* 首先，完成教學 **[!UICONTROL More tips]** 課程：透過說明(?)存取它的雙曲餘切值。 [!UICONTROL Quick Insights Panel]

   ![](assets/qibuilder4.png)

* **劃分依據**:您最多可針對維度使用3個層級的劃分，以深入探討您真正需要的資料。

   ![](assets/qibuilder5.png)

* **新增更多量度**:您最多可以使用AND運算子新增2個量度至表格。

   ![](assets/qibuilder6.png)

* **新增更多區段**:您最多可以使用AND或OR運算子來新增多達2個區段。 查看新增「行動使用者」或「忠誠訪客」時表格的變更。 它們彼此相鄰，位於量度上方。 如果您新增「行動使用者」和「忠誠訪客」，您會同時看到這兩個區段的結果，而且這些結果會堆疊在表格中。

   ![](assets/qibuilder7.png)

## 已知限制

如果您嘗試直接在表格中編輯，會 [!UICONTROL Quick Insights] 導致面板（填空工具）不同步。 您可以按一下面板 [!UICONTROL Quick Insights] 右上角的 **[!UICONTROL Resync Builder]** 設定，將它還原為先前的設定。

![](assets/qibuilder9.png)

在直接將任何內容新增至表格之前，您會收到警告：

![](assets/qibuilder8.png)

否則，直接建立會使表格現在像傳統的自由表格一樣運作，而沒有新使用者的實用功能。

