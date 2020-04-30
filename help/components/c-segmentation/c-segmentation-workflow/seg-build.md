---
description: 「區段產生器」提供畫布來拖放「量度維度」、「區段」和「事件」，以根據容器階層邏輯、規則和運算子來分段訪客。此一整合式開發工具可讓您建立並儲存簡單或複雜區段，用以識別跨瀏覽及頁面點擊的訪客屬性和動作。
title: 建立區段
topic: Segments
uuid: c01393df-ccdd-431c-83a6-3c2700bd4999
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# 區段產生器

The [!UICONTROL Segment Builder] provides a canvas to drag and drop Metrics, Dimensions, Segments, and Events to segment visitors based on container hierarchy logic, rules, and operators. 此一整合式開發工具可讓您建立並儲存簡單或複雜區段，用以識別跨瀏覽及頁面點擊的訪客屬性和動作。

>[!IMPORTANT]
>
>我們在 2019 年 6 月的版本中引入了維度歸因模型。請參閱下方「Web UI 功能」底下的第 6 項。

要存取「區段產生器」有數種方式：

* **Analytics頂端導覽**:按一 **[!UICONTROL Analytics]** 下> **[!UICONTROL Components]** > **[!UICONTROL Segments]**。
* **[!UICONTROL Analysis Workspace]**:按一 **[!UICONTROL Analytics]** 下> **[!UICONTROL Workspace]**，開啟專案，然後按一下 **[!UICONTROL + New]** > **[!UICONTROL Create Segment]**。
* **[!UICONTROL Reports & Analytics]**:按一 **[!UICONTROL Analytics]** 下> **[!UICONTROL Reports]**，開啟現有報表，然後按一下左側導覽 ![](assets/segment_icon.png) 中的區段圖示，然後按一下 **[!UICONTROL Add]**。
* **[!UICONTROL Ad Hoc Analysis]**: [在 Ad Hoc Analysis 中建立區段](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md#build-segments).
* **[!UICONTROL Report Builder]**:在報 [告建立工具中新增或編輯區段](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/data-requests/segmentation.html)。

## 區段產生器使用者介面 {#concept_643F2DF74C544796B58F4656ABC5F726}

The [!UICONTROL Segment Builder] lets you build simple or complex segments that identify visitor attributes and actions across visits and page hits. 它提供畫布來拖放量度維度、事件或其他區段，以根據容器階層邏輯、規則和運算子來劃分訪客。

## Web UI 功能 {#section_F61C4268A5974C788629399ADE1E6E7C}

The [!UICONTROL Segment Builder] lets you build and edit segments in the web UI (or in a [Java UI in Ad Hoc Analysis](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md)). 您可以新增規則定義和容器來微調您的區段、堆疊區段和巢狀內嵌區段。您也可以驗證有多少個頁面檢視、造訪和獨特訪客是從您目前的區段定義得出。然後儲存區段，以供未來使用。

存取「區段產生器」的方法有：:

* 顯示現有報表並按一下左側導覽中的區段圖示 ![](assets/segment_icon.png)。In the segment rail that displays, click **[!UICONTROL Add]**.

* From within the Segment Manager, clicking **[!UICONTROL + Add]**.
* 按一下「區段管理器」中的現有區段標題，以編輯「區段產生器」中的區段。

![](assets/segment_builder_ui.png)

1. **[!UICONTROL Title]**:可讓您命名或重新命名區段。
1. **[!UICONTROL Description]**:提供區段的說明。 如果您要共用區段，則必須提供說明。
1. **[!UICONTROL Tags]**:從現 [有標籤清單中挑選](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md) ，或建立新標籤，以標籤您所建立的區段。
1. **[!UICONTROL Definitions]**:這是您建立和設 [定區段、新增規則](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md)、巢狀內嵌容器及排序容器的地方。 可讓您透過選取容器並拖放維度、區段或量度至定義，來提供新區段的說明。
1. **[!UICONTROL Show]**: (頂層容器選擇器.) Lets you select the top-level [container](/help/components/c-segmentation/seg-overview.md) ( [!UICONTROL Visitor], [!UICONTROL Visit], [!UICONTROL Hit]). 預設的頂層容器為「點擊」容器。
1. **[!UICONTROL Options]**:（齒輪）圖示

   * **[!UICONTROL + Add container]**:可讓您新增容器（位於頂層容器下方）至區段定義。
   * **[!UICONTROL + Add container from selection]**:可讓您從「定義」欄位中選取的元素（多個）建立新容器。
   * **[!UICONTROL Exclude]**:可讓您排除一或多個維度、區段或量度來定義區段。

1. **[!UICONTROL Attribution Models]**:用於維度分段。 維度模型在循序區段中特別有用，例如支援「流量」視覺化的區段：

   * **[!UICONTROL Repeating]** (（預設值）:包含維度的例項和持續值。
   * **[!UICONTROL Instance]**: 包括維度的例項.
   * **[!UICONTROL Non-repeating instance]**:包含維的唯一實例（非重複）。
   ![](assets/attribution-models.jpg)

1. **[!UICONTROL Dimensions]**:維度會從「維度」清單中拖放（橘色側欄）。
1. **[!UICONTROL Comparison]**:您可以使用選取的運算子來比較和限制值。
1. **[!UICONTROL Value]**:您為維度、區段或量度輸入或選取的值。
1. **[!UICONTROL And/Or/Then]**:在容器或 [!UICONTROL AND/OR/THEN] 規則之間指派運算子。 THEN 運算子可用來[定義循序區段](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md)。
1. **[!UICONTROL Metric]**:（綠色側欄）從「量度」清單拖放的量度。
1. **[!UICONTROL Comparison]** 運算元：您可以使用選取的運算子來比較和限制值。
1. **[!UICONTROL Value]**:您為維度、區段或量度輸入或選取的值。
1. **[!UICONTROL X]**：(刪除) 可用來刪除這個部分的區段定義。
1. **[!UICONTROL Save]** 或 **[!UICONTROL Cancel]**:儲存或取消區段。 After clicking **[!UICONTROL Save]**, you are taken to the Segment Manager where you can manage the segment.
1. **[!UICONTROL Search]**:搜尋維度、區段或度量的清單。
1. **[!UICONTROL Dimensions]**:（清單）按一下標題以展開。
1. **[!UICONTROL Metrics]**:按一下標題以展開。
1. **[!UICONTROL Segments]**:按一下標題以展開。
1. **[!UICONTROL Report suite selector]**:可讓您選取此區段將儲存在下方的報表套裝。 您仍可以使用所有報表套裝中的區段。
1. **[!UICONTROL Segment Preview]**:可讓您預覽關鍵量度，以查看您是否有有效的區段，以及區段的廣度。 代表如果您套用此區段，可以預期看到的資料集劃分。Shows 3 concentric circles and a list to show the number and percentage of matches for [!UICONTROL Hits], [!UICONTROL Visits], and [!UICONTROL Visitors] for a segment run against a data set. 在您建立或對區段定義進行變更之後，此圖表會立即更新。
1. **[!UICONTROL Product Compatibility]**:提供您所建立區段與哪些Adobe Analytics產品(分析工作區、臨機 [!UICONTROL Reports & Analytics]分析、資料倉庫)相容的清單。 大多數區段與所有產品都相容。不過，並非所有運算子和維度均與所有 Analytics 產品相容，特別是 [Data Warehouse](/help/components/c-segmentation/seg-reference/seg-compatibility.md)。在您對區段定義進行變更之後，此圖表會立即更新。

含有內嵌日期範圍的區段在 Analysis Workspace 和 [!UICONTROL Reports & Analytics] 中持續以不同方式運作。在 Workspace 中，包含內嵌日期範圍的區段會覆寫面板日期範圍。相較之下，[!UICONTROL Reports & Analytics] 則提供報表日期範圍及區段內嵌日期範圍的交集。

**[!UICONTROL Publish to Experience Cloud (for `<report suite name>`)]**:（未在螢幕上顯示）只有在您要儲存此區段的報表套裝已啟用Experience Cloud時，才 [會顯示此選項](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md)。 By publishing a segment to the Experience Cloud, you can use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], and [!DNL Audience Manager]. 需要區段標題和說明。

>[!NOTE]您可以在 Analytics 中編輯或刪除發佈的區隔。如果該區隔正在使用中，系統會在您編輯該區隔時發出警告訊息。您無法刪除 Adobe [!DNL Target] 正在使用的已發佈區段。

![](assets/segment_publish_to_mac_copy.png)

>[!IMPORTANT]
>
>您必須將透過 Analytics 共用的對象數量限制為 20，以避免額外的程序延誤。透過 Analytics 與 Experience Cloud 共用的受眾不能超過 2,000 萬個不重複的成員。另外，由於快取關係，Experience Cloud 會在 12 小時之後才顯示 Analytics 中刪除的報表套裝資訊。

>[!IMPORTANT]
>
>訪客符合從 Analytics 共用的對象資格後，此資訊會延遲 24 至 48 小時才能在 [!DNL Target]、[!DNL Advertising Cloud] 和 [!DNL Campaign] 中操作。

## 建立區段 {#build-segments}

1. Simply drag a Dimension, Segment, or Metric Event from the left pane to the [!UICONTROL Definitions] field.

   ![](assets/drag_n_drop_dimension.png)

   The default top-level [!UICONTROL Hit] container is shown after dragging an element to [!UICONTROL Definitions]. You can change the container type to Visit or Visitor from the **[!UICONTROL Show]** drop-down menu.

1. 從下拉式功能表中設定[運算子](/help/components/c-segmentation/seg-reference/seg-operators.md)。
1. 針對選取的項目輸入或選取值。
1. Add additional containers if needed, using **[!UICONTROL And]**, **[!UICONTROL Or]**, or **[!UICONTROL Then]** rules.
1. 放置好容器且設定規則後，請在右上方的驗證圖表中查看區段的結果。驗證器會指出與您所建立區段相符之頁面檢視、造訪次數和獨特訪客的百分比與絕對數量。
1. Under **[!UICONTROL Tags]**, [tag](/help/components/c-segmentation/c-segmentation-workflow/seg-tag.md) the container by selecting an existing tag or creating a new one.
1. Click **[!UICONTROL Save]** to save the segment.

此時會進入[區段管理器](/help/components/c-segmentation/c-segmentation-workflow/seg-manage.md)，您可在此透過多種方式標記、共用及管理區段。

## 建立與巢狀內嵌容器 {#section_1C38F15703B44474B0718CEF06639EFD}

您可以[建立容器的架構](/help/components/c-segmentation/seg-overview.md)，然後在當中放置邏輯規則和運算子。

1. 按一下 **[!UICONTROL Options > Add Container]**.

   ![](assets/add_container.png)

   A new [!UICONTROL Hit] container opens without a [!UICONTROL Hit] (Page View) identified.

   ![](assets/new_container.png)

1. 視需要變更容器類型。
1. 從左側窗格拖曳「維度」、「區段」或「事件」至容器。
1. Continue to add new containers from the top-level **[!UICONTROL Options]** > **[!UICONTROL Add container]** button at the top of the definition, or add containers from within a container to nest logic.

   **或**

   選取一或多個規則，然後按一下 **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]**。 這會將您的選項轉變成個別容器。

## 在區段中使用日期範圍 {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

您可以建立包含滾動日期範圍的區段，以回答與持續性促銷活動或事件有關的問題。

舉例來說，您可以輕鬆建立包括「過去 60 天內購買過一次的人」的區段。

You create a Visit container and within it, add the [!UICONTROL Last 60 days] time range and the metric [!UICONTROL Orders is greater than or equal to 1], with an AND operator:

![](assets/date-ranges.png)

## 堆疊區段 {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

堆疊區段的運作方式是使用 &#39;and&#39; 運算子結合每個區段中的準則，然後套用結合後的準則。

例如，將「行動電話使用者」區段和「美國地區」區段堆疊在一起，只會傳回美國地區行動電話使用者的資料。

將這些區段想成可加到區段庫中的素材或模組，供想要的使用者使用。透過此方式，您便可以大量減少所需的區段數。例如，假設您有 40 個區段：

* 20 個代表不同國家/地區的行動電話使用者 (US_mobile、Germany_mobile、France_mobile、Brazil_mobile 等等)
* 20 個代表不同國家/地區的平板電腦使用者 (US_tablet、Germany_tablet、France_tablet、Brazil_tablet 等等)

透過將區段堆疊，您可以將區段的個數降至 22 個，並視需要加以堆疊。您將需要建立下列區段：

* 一個區段代表行動使用者
* 一個區段代表平板電腦使用者
* 20 個區段代表不同地區

>[!NOTE] 將兩個區段堆疊在一起時，預設會使用 AND 陳述式加以連結。無法變更為 OR 陳述式。

1. 前往「區段產生器」。
1. 提供區段的標題和說明。

   步驟結果 1。Click **[!UICONTROL Show Segments]** to bring up the list of segments in the left navigation.

   步驟結果 1。拖放您要堆疊到區段定義畫布的區段。以下是將現有區段「來自平板電腦的瀏覽」與「美國地區」堆疊在一起的區段範例：

   ![](assets/seg_stack2.png)

1. 儲存區段。

   步驟結果

## 使用區段範本 {#concept_5098446CC78D441E93B8E4D1D1EA6558}

範本代表舊有預先設定的套裝區段。

In the Segment Manager, click **[!UICONTROL Add]**, which takes you to the Segment Builder. 現在按一下「區段」圖示 ![](assets/segment_icon.png) 

以開啟區段欄。區段範本會出現在區段清單的底部。您可透過範本名稱左側的資料夾圖示加以認出：

![](assets/seg_template.png)

您可以將這些範本拖曳至「定義」畫布，然後依原有定義使用或是加以修改。

<table id="table_98B87D807E9344C9BEBF072C65D87B1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 範本名稱 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 放棄購物車 </td> 
   <td colname="col2">檢視已新增項目至購物車但並未訂購任何項目的訪客的相關資料。在區段定義中，容器是瀏覽。此循序區段的規則是 <p> 購物車新增非空值 </p> <p>Then </p> <p>訂購等於 0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 首次瀏覽次數 </td> 
   <td colname="col2">檢視最多僅存取過 1 次的訪客的相關資料。在區段定義中，容器是瀏覽。規則是 <p>瀏覽次數等於 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非購買者 </td> 
   <td colname="col2">檢視未參與訂購事件的訪客的相關資料。在區段定義中，容器是訪客。此區段使用「排除」邏輯。規則是 <p>訂購非空值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非單一頁面瀏覽 (非彈回) </td> 
   <td colname="col2">檢視瀏覽超過一次的訪客的相關資料。在區段定義中，容器是訪客。此區段使用「排除」邏輯。規則是 <p>單次存取非空值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 付費搜尋 </td> 
   <td colname="col2">檢視來自付費搜尋的訪客的相關資料。在區段定義中，容器是瀏覽。規則是 <p>付費搜尋等於 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 購買者 </td> 
   <td colname="col2">檢視參與訂購事件的訪客的相關資料。在區段定義中，容器是訪客。規則是 <p>訂購非空值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 回訪 </td> 
   <td colname="col2">檢視已瀏覽至少一次的訪客的相關資料。在區段定義中，容器是瀏覽。規則是 <p>瀏覽次數大於 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 單頁存取次數 </td> 
   <td colname="col2"> 檢視您看到單一頁面值之瀏覽中的資料，即使您可能在該次瀏覽期間提交多個頁面檢視亦同。帶有退出連結事件的單一頁面瀏覽會納入到區段中。在區段定義中，容器是瀏覽。規則是 <p>單頁存取次數等於 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 檢視未加到購物車的產品 </td> 
   <td colname="col2">檢視查看了產品但並未加任何項目到購物車的訪客的相關資料。在區段定義中，容器是瀏覽。此循序區段的規則是 <p>產品檢視非空值 </p> <p>Then </p> <p> 購物車新增等於 0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自促銷活動的瀏覽次數 </td> 
   <td colname="col2">檢視由促銷活動引薦過來的訪客的相關資料。在區段定義中，容器是瀏覽。規則是 <p>追蹤代碼非空值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自行動裝置的瀏覽次數 </td> 
   <td colname="col2">檢視使用行動裝置的訪客的相關資料。在區段定義中，容器是瀏覽。規則是 <p>行動裝置非空值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自免費搜尋的瀏覽次數 </td> 
   <td colname="col2">檢視不是來自付費搜尋的訪客的相關資料。在區段定義中，容器是瀏覽。規則是 <p>付費搜尋等於 0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自非行動裝置的瀏覽次數 </td> 
   <td colname="col2">檢視非使用行動裝置的訪客的相關資料。在區段定義中，容器是瀏覽。此區段使用「排除」邏輯。規則是 <p>行動裝置類型等於行動電話 </p> <p>或 </p> <p>行動裝置類型等於平板電腦。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自手機的瀏覽次數 </td> 
   <td colname="col2">檢視使用手機的訪客的相關資料。在區段定義中，容器是瀏覽。規則是 <p>裝置類型等於行動電話。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自搜尋引擎的瀏覽次數 </td> 
   <td colname="col2">檢視由搜尋引擎引薦過來的訪客的相關資料。在區段定義中，容器是瀏覽。規則是 <p>反向連結類型等於搜尋引擎。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自社交網站的瀏覽次數 </td> 
   <td colname="col2">檢視社交網站參照的訪客的相關資料。在區段定義中，容器是瀏覽。規則是 <p>反向連結類型等於社交網路. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自平板電腦的瀏覽次數 </td> 
   <td colname="col2">檢視使用平板電腦的訪客的相關資料。在區段定義中，容器是瀏覽。規則是 <p>裝置類型等於平板電腦。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 具有訪客 ID Cookie 的瀏覽次數 </td> 
   <td colname="col2">檢視到您網站 (需要永久性 Cookie) 的訪客的相關資料。在區段定義中，容器是瀏覽。規則是 <p>永久性 Cookie 等於 1。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範例：促銷活動訪客區段 {#concept_61AC6115097B4EB3AEFE8CE98F38315D}

顯示此常用區段的範例。

許多客戶想要查看從回應了特定促銷活動的訪客得到的量度。建立促銷活動訪客區段是取得這些資料的簡易方式。

在「區段產生器」建立此區段，表示您要拖曳促銷活動維度 (在此例中為「促銷活動名稱」) 到頂層的「瀏覽」容器中：

![](assets/seg_campaign_visitor.png)

(選用) 如果您希望能夠輕鬆篩選所有促銷活動相關區段，也可以套用「促銷活動」標記至這個區段。
