---
description: 分類是將 Analytics 變數資料分類，然後在您產生報表時以不同方式顯示資料的方式。
subtopic: Classifications
title: 關於分類
topic: Admin tools
uuid: abc1a1be-8e37-4b7e-81fd-3e99ac27fc6a
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 關於分類

分類是將 Analytics 變數資料分類，然後在您產生報表時以不同方式顯示資料的方式。

「[Analytics 分類](https://video.tv.adobe.com/v/16853/?captions=chi_hant)」的影片概述。

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > *`<Traffic or Conversion>`*

分類時，您會在變數和與該變數相關的中繼資料之間建立關係。 分類最常用於促銷活動。 使用變數（eVar、prop和事件）資訊收集的資料可透過將中繼資料套用至在變數中收集的值來統計。

![步驟資訊](assets/sub_class_create.png)

分類後，您可以使用關鍵變數產生的任何報表，也可以使用相關屬性產生。 例如，您可以使用其 [!UICONTROL Product IDs] 他產品屬性來分類，例如產品名稱、顏色、大小、說明和SKU。 利用其他屬性擴充報告與分析資料，提供更深入、更複雜的報告機會。

>[!IMPORTANT]
>
>匯入數值 2 與日期啟用分類的功能已自基底程式碼移除。此變更將自2019年6月維護髮行生效。 若您的匯入檔案中含有數值或日期啟用欄，系統會自動忽略這些儲存格，至於該檔案中的其他所有資料都將正常匯入。您仍可透過標準分類工作流程匯出現有分類，並繼續在報表中使用。

>[!NOTE] 在 2018 年 5 月 10 日的 Analytics 維護發行中，Adobe 已開始限制日期啟用和數值分類的功能。這些分類類型已從「管理員」和「分類匯入工具」介面中移除。不能新增啟用日期和數值分類。 但仍可透過標準分類工作流程來管理 (上傳和刪除) 現有分類，並可繼續在報告中使用。

建立分類之後，您可以在整個 Adobe Analytics 中運用新的資料屬性。

**追蹤代碼範例**

假設您不想僅依追蹤代碼檢視促銷活動，而想依搜尋引擎、關鍵字和促銷活動渠道查看促銷活動結果。 您可以建立促銷活動變數的三個分類，以代表搜尋引擎、關鍵字和促銷活動渠道，而不是將轉換變數分成每個分類。 此策略可讓您透過所有四個變數來查看網站成功事件，毋需加上標籤。

報告與分析包括追蹤代碼變數的預先定義分類，此類分類提供分類型報表，稱為「創作元素」和「促銷活動」。 您必須手動設定所有其他轉換和流量變數的分類。

請參 [閱流量分](/help/admin/admin/c-traffic-variables/traffic-classifications.md) 類 [和轉換分類](https://marketing.adobe.com/resources/help/zh_TW/reference/conversion_classifications.html)。

下表說明可用的不同分類類型，以及支援這些分類的變數類型。 上傳資料檔案之前，請先檢閱[一般檔案結構](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md)。

<table id="table_279728C28D9C40EE832ACC9F211B5F17"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>類型 </p> </th> 
   <th colname="col2" class="entry"> <p>可用性 </p> </th> 
   <th colname="col3" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 文字</span> </p> </td> 
   <td colname="col2"> <p>轉換和流量變數 </p> </td> 
   <td colname="col3"> <p>文字分類可定義類別，讓您將變數資料分組以用於報告。 </p> <p>例如，如果您銷售襯衫，您可能想要依顏色、大小和樣式來分類襯衫銷售（轉換），以便產生報表，讓您查看這些類別所組織的襯衫銷售。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 啟用日期的文字</span> </p> <p>注意：在 2018 年 5 月 10 日的 Analytics 維護發行中，Adobe 已開始限制日期啟用分類的功能。這些分類類型已從「管理員」和「分類匯入工具」介面中移除。無法新增日期啟用分類。但仍可透過標準分類工作流程來管理 (上傳和刪除) 現有分類，並可繼續在報告中使用。 </p> </td> 
   <td colname="col2"> <p>轉換變數 </p> </td> 
   <td colname="col3"> <p>啟用日期的文字分類可讓您將日期範圍指派給文字分類。 它通常能搭配促銷活動分類，以便讓您在<span class="wintitle">促銷活動</span>報告中善用甘特圖檢視的優點。 </p> <p>您可以在負責填入分類資料的資料檔案中加入實際的促銷活動日期。 </p> <p>即使已過了促銷活動的結束日期，Reports &amp; Analytics 仍會收集促銷活動追蹤程式碼，不過在促銷活動結束日期之後收集而來的促銷活動資料不會與促銷活動相關聯。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 數值</span> <p>注意：在 2018 年 5 月 10 日的 Analytics 維護發行中，Adobe 已開始限制數值分類的功能。這些分類類型已從「管理員」和「分類匯入工具」介面中移除。無法新增數值分類。但仍可透過標準分類工作流程來管理 (上傳和刪除) 現有分類，並可繼續在報告中使用。 </p> </p> </td> 
   <td colname="col2"> <p>轉換變數 </p> </td> 
   <td colname="col3"> <p>數值分類可讓您將固定數值套用至<span class="wintitle">轉換</span>報告。這些分類會顯示為報告中的量度。 </p> <p>在考量是否要新增<span class="wintitle">數值</span>分類時，數值必須固定且不會隨著時間改變。 </p> </td> 
  </tr> 
 </tbody> 
</table>

