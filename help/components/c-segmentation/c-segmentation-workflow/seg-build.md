---
description: 「區段產生器」提供畫布來拖放「量度維度」、「區段」和「事件」，以根據容器階層邏輯、規則和運算子來分段訪客。此一整合式開發工具可讓您建立並儲存簡單或複雜區段，用以識別跨瀏覽及頁面點擊的訪客屬性和動作。
title: 建立區段
topic: Segments
uuid: c01393df-ccdd-431c-83a6-3c2700bd4999
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 區段產生器

[!UICONTROL 區段產生器]提供畫布來拖放量度、維度、區段和事件，以便根據容器階層邏輯、規則和運算子來區分訪客。此一整合式開發工具可讓您建立並儲存簡單或複雜區段，用以識別跨瀏覽及頁面點擊的訪客屬性和動作。

>[!IMPORTANT]
>
>我們在 2019 年 6 月的版本中引入了維度歸因模型。請參閱下方「Web UI 功能」底下的第 6 項。

要存取「區段產生器」有數種方式：

* **Analytics 頂端導覽**：按一下&#x200B;**[!UICONTROL 「Analytics]** > **[!UICONTROL 元件]** > **[!UICONTROL 區段」]**。
* **[!UICONTROL Analysis Workspace]**：按一下&#x200B;**[!UICONTROL 「Analytics]** > **[!UICONTROL Workspace」]**，開啟專案並按一下&#x200B;**[!UICONTROL 「+ 新增]** > **[!UICONTROL 建立區段」]**。
* **[!UICONTROL Reports &amp; Analytics]**：按一下&#x200B;**[!UICONTROL 「Analytics]** > **[!UICONTROL 報表」]**，開啟現有報表並按一下左側導覽中的「區段」圖示 ![](assets/segment_icon.png)，然後按一下&#x200B;**[!UICONTROL 「新增」]**。
* **[!UICONTROL Ad Hoc Analysis]**：[在 Ad Hoc Analysis 中建立區段](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md#build-segments)。
* **[!UICONTROL Report Builder]**：[在 Report Builder 中新增或編輯區段](https://marketing.adobe.com/resources/help/zh_TW/arb/segmentation.html)。

## 區段產生器使用者介面 {#concept_643F2DF74C544796B58F4656ABC5F726}

[!UICONTROL 區段產生器]可讓您建立簡單或複雜區段，用以識別各瀏覽及頁面點擊中的訪客屬性和動作。它提供畫布來拖放量度維度、事件或其他區段，以根據容器階層邏輯、規則和運算子來劃分訪客。

## Web UI 功能{#section_F61C4268A5974C788629399ADE1E6E7C}

[!UICONTROL 「區段產生器」]可讓您在 Web UI (或在 [Ad Hoc Analysis 的 Java UI](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md)) 中建立和編輯區段。您可以新增規則定義和容器來微調您的區段、堆疊區段和巢狀內嵌區段。您也可以驗證有多少個頁面檢視、造訪和獨特訪客是從您目前的區段定義得出。然後儲存區段，以供未來使用。

存取「區段產生器」的方法有：：

* 顯示現有報表並按一下左側導覽中的區段圖示 ![](assets/segment_icon.png)。在顯示的區段欄中，按一下&#x200B;**[!UICONTROL 「新增」]**。

* 在「區段管理器」內按一下&#x200B;**[!UICONTROL 「+ 新增」]**。
* 按一下「區段管理器」中的現有區段標題，以編輯「區段產生器」中的區段。

![](assets/segment_builder_ui.png)

1. **[!UICONTROL 標題]**：為區段命名或重新命名。
1. **[!UICONTROL 說明]**：提供區段的說明。如果您要共用區段，則必須提供說明。
1. **[!UICONTROL 標記]**：選擇現有標記清單中的標記或建立新標記，[標記您正在建立的區段](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md)。
1. **[!UICONTROL 定義]**：可在此[建立和設定區段](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md)、新增規則、巢狀內嵌及排序容器。可讓您透過選取容器並拖放維度、區段或量度至定義，來提供新區段的說明。
1. **[!UICONTROL 顯示]**：(頂端容器選擇器)可讓您選取頂層[容器](/help/components/c-segmentation/seg-overview.md)層級 ([!UICONTROL 訪客]、[!UICONTROL 造訪]、[!UICONTROL 點擊])。預設的頂層容器為「點擊」容器。
1. **[!UICONTROL 選項]**：(齒輪) 圖示

   * **[!UICONTROL + 新增容器]**：可讓您新增新的容器 (在頂層容器下) 至區段定義。
   * **[!UICONTROL + 從選項新增容器]**：可讓您使用在「定義」欄位中選取的一個以上元素建立新容器。
   * **[!UICONTROL 排除]**：可讓您透過排除一或多個維度、區段或量度來定義區段。

1. **[!UICONTROL 歸因模型]**：用於維度劃分。維度模型在循序區段中特別有用，例如支援「流量」視覺化的區段：

   * **[!UICONTROL 重複]** ((預設值))：包含維度的例項和持續值。
   * **[!UICONTROL 例項]**：包含維度的例項。
   * **[!UICONTROL 非重複例項]**：包含維度的唯一例項 (非重複)。
   ![](assets/attribution-models.jpg)

1. **[!UICONTROL 維度]**：從「維度」清單拖放過來的維度 (橘色側欄)。
1. **[!UICONTROL 比較]**：您可以使用選取的運算子來比較和限制值。
1. **[!UICONTROL 值]**：您針對維度、區段或量度所輸入或選取的值。
1. **[!UICONTROL And/Or/Then]**：在容器或規則之間指派 [!UICONTROL AND/OR/THEN] 運算子。THEN 運算子可用來[定義循序區段](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md)。
1. **[!UICONTROL 量度]**：(綠色側欄) 從「量度」清單拖放過來的量度。
1. **[!UICONTROL 比較]**&#x200B;運算子：可使用選取的運算子來比較和限制值。
1. **[!UICONTROL 值]**：您針對維度、區段或量度所輸入或選取的值。
1. **[!UICONTROL X]**：(刪除) 可用來刪除這個部分的區段定義。
1. **[!UICONTROL 儲存]**&#x200B;或&#x200B;**[!UICONTROL 取消]**：儲存或取消區段。按一下&#x200B;**[!UICONTROL 「儲存」]**&#x200B;之後會進入「區段管理器」，您可在此管理區段。
1. **[!UICONTROL 搜尋]**：搜尋維度、區段或量度清單。
1. **[!UICONTROL 維度]**：(清單) 按一下標題可展開。
1. **[!UICONTROL 量度]**：按一下標題可展開。
1. **[!UICONTROL 區段]**：按一下標題可展開。
1. **[!UICONTROL 報表套裝選取器]**：可讓您選取要將此區段儲存於其下的報表套裝。您仍可以使用所有報表套裝中的區段。
1. **[!UICONTROL 區段預覽]**：可讓您預覽關鍵量度，以查看您是否具備有效的區段及區段的廣度。代表如果您套用此區段，可以預期看到的資料集劃分。顯示 3 個同心圓以及一個清單，以顯示對資料集執行之區段的[!UICONTROL 點擊]、[!UICONTROL 瀏覽]和[!UICONTROL 訪客]符合項目的數目和百分比。在您建立或對區段定義進行變更之後，此圖表會立即更新。
1. **[!UICONTROL 產品相容性]**：提供與您所建立區段相容的 Adobe Analytics 產品 (Analysis Workspace、[!UICONTROL Reports &amp; Analytics]、Ad Hoc Analysis、Data Warehouse) 清單。大多數區段與所有產品都相容。不過，並非所有運算子和維度均與所有 Analytics 產品相容，特別是 [Data Warehouse](/help/components/c-segmentation/seg-reference/seg-compatibility.md)。在您對區段定義進行變更之後，此圖表會立即更新。

含有內嵌日期範圍的區段在 Analysis Workspace 和 [!UICONTROL Reports &amp; Analytics] 中持續以不同方式運作。在 Workspace 中，包含內嵌日期範圍的區段會覆寫面板日期範圍。相較之下，[!UICONTROL Reports &amp; Analytics] 則提供報表日期範圍及區段內嵌日期範圍的交集。

**[!UICONTROL 發佈至 Experience Cloud (適用於`<report suite name>`)]**：(畫面上不會顯示) 只有當您要儲存此區段的目標報表套裝[已啟用 Experience Cloud 功能](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md)時，才會出現此選項。將區段發佈至 Experience Cloud 後，您便可以在[!UICONTROL 對象庫]、[!DNL Target] 和 [!DNL Audience Manager] 中，使用該區段進行促銷活動。需要區段標題和說明。

> [!NOTE]您可以在 Analytics 中編輯或刪除發佈的區隔。如果該區隔正在使用中，系統會在您編輯該區隔時發出警告訊息。您無法刪除 Adobe [!DNL Target] 正在使用的已發佈區段。

![](assets/segment_publish_to_mac_copy.png)

>[!IMPORTANT]
>
>您必須將透過 Analytics 共用的對象數量限制為 20，以避免額外的程序延誤。透過 Analytics 與 Experience Cloud 共用的受眾不能超過 2,000 萬個不重複的成員。另外，由於快取關係，Experience Cloud 會在 12 小時之後才顯示 Analytics 中刪除的報表套裝資訊。

>[!IMPORTANT]
>
>訪客符合從 Analytics 共用的對象資格後，此資訊會延遲 24 至 48 小時才能在 [!DNL Target]、[!DNL Advertising Cloud] 和 [!DNL Campaign] 中操作。

## 建立區段 {#build-segments}

1. 只需從左側窗格將「維度」、「區段」或「量度事件」拖放至「[!UICONTROL 定義]」欄位即可。

   ![](assets/drag_n_drop_dimension.png)

   將元素拖曳到「[!UICONTROL 定義]」之後，預設的最上層「[!UICONTROL 點擊]」容器隨即顯示。您可以透過「**[!UICONTROL 顯示]**」下拉式功能表，將容器類型變更為「瀏覽」或「訪客」。

1. 從下拉式功能表中設定[運算子](/help/components/c-segmentation/seg-reference/seg-operators.md)。
1. 針對選取的項目輸入或選取值。
1. 必要時使用 **[!UICONTROL And]**、**[!UICONTROL Or]** 或 **[!UICONTROL Then]** 規則新增額外的限制。
1. 放置好容器且設定規則後，請在右上方的驗證圖表中查看區段的結果。驗證器會指出與您所建立區段相符之頁面檢視、造訪次數和獨特訪客的百分比與絕對數量。
1. 在&#x200B;**[!UICONTROL 「標記」]**&#x200B;底下，選取現有標記或建立新標記即可[標記](/help/components/c-segmentation/c-segmentation-workflow/seg-tag.md)容器。
1. 按一下「**[!UICONTROL 儲存]**」來儲存區段。

此時會進入[區段管理器](/help/components/c-segmentation/c-segmentation-workflow/seg-manage.md)，您可在此透過多種方式標記、共用及管理區段。

## 建立與巢狀內嵌容器 {#section_1C38F15703B44474B0718CEF06639EFD}

您可以[建立容器的架構](/help/components/c-segmentation/seg-overview.md)，然後在當中放置邏輯規則和運算子。

1. 按一下&#x200B;**[!UICONTROL 「選項 > 新增容器」]**。

   ![](assets/add_container.png)

   隨即開啟一個新的「[!UICONTROL 點擊]」容器，其中未識別「[!UICONTROL 點擊]」(頁面檢視)。

   ![](assets/new_container.png)

1. 視需要變更容器類型。
1. 從左側窗格拖曳「維度」、「區段」或「事件」至容器。
1. 繼續從定義上方的頂層「**[!UICONTROL 選項]**」>「**[!UICONTROL 新增容器]**」按鈕新增容器，或從容器內新增容器以巢狀內嵌邏輯。

   **或**

   選取一或多個規則，然後按一下「**[!UICONTROL 選項]**」>「**[!UICONTROL 從選項新增容器]**」。這會將您的選項轉變成個別容器。

## 在區段中使用日期範圍 {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

您可以建立包含滾動日期範圍的區段，以回答與持續性促銷活動或事件有關的問題。

舉例來說，您可以輕鬆建立包括「過去 60 天內購買過一次的人」的區段。

您可以建立「造訪」容器，在裡面添加時間範圍[!UICONTROL 「Last 60 days (過去 60 天)」]及量度[!UICONTROL 「Orders is greater than or equal to 1 (訂單數量大於或等於 1)」]，用「AND」作運算符：

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

> [!NOTE] 將兩個區段堆疊在一起時，預設會使用 AND 陳述式加以連結。無法變更為 OR 陳述式。

1. 前往「區段產生器」。
1. 提供區段的標題和說明。

   步驟結果 1。按一下「**[!UICONTROL 顯示區段]**」以在左側導覽中開啟區段清單。

   步驟結果 1。拖放您要堆疊到區段定義畫布的區段。以下是將現有區段「來自平板電腦的瀏覽」與「美國地區」堆疊在一起的區段範例：

   ![](assets/seg_stack2.png)

1. 儲存區段。

   步驟結果

## 使用區段範本 {#concept_5098446CC78D441E93B8E4D1D1EA6558}

範本代表舊有預先設定的套裝區段。

在區段管理器中按一下&#x200B;**[!UICONTROL 「新增」]**，接著便會前往區段產生器。現在按一下「區段」圖示 ![](assets/segment_icon.png) 

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
