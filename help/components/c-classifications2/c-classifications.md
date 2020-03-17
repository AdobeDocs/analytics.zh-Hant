---
description: 分類是將 Analytics 變數資料分類，然後在您產生報表時以不同方式顯示資料的方式。
subtopic: Classifications
title: 關於分類
topic: Admin tools
uuid: abc1a1be-8e37-4b7e-81fd-3e99ac27fc6a
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 關於分類

分類是將 Analytics 變數資料分類，然後在您產生報表時以不同方式顯示資料的方式。

「[Analytics 分類](https://video.tv.adobe.com/v/16853/?captions=chi_hant)」的影片概述。

**[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]** > **[!UICONTROL 編輯設定]** > *`<Traffic or Conversion>`*

您在分類時，建立變數和與該變數相關之中繼資料間的關係。分類最常在促銷活動中使用。可以將中繼資料套用到變數中收集的值，以彙總使用變數 (eVar、prop 和事件) 資訊收集的資料。

![步驟資訊](assets/sub_class_create.png)

分類後，透過代碼資料產生的任何報告，亦可透過相關聯的屬性產生。例如，您可以使用其他的產品屬性將「[!UICONTROL 產品 ID]」分類，例如產品名稱、顏色、大小、說明和 SKU。利用其他屬性加強 Reports &amp; Analytics 資料可提供更深和更複雜的報告機會。

>[!IMPORTANT]
>
>匯入數值 2 與日期啟用分類的功能已自基底程式碼移除。此變更預計於 2019 年 6 月維護版本中生效。若您的匯入檔案中含有數值或日期啟用欄，系統會自動忽略這些儲存格，至於該檔案中的其他所有資料都將正常匯入。您仍可透過標準分類工作流程匯出現有分類，並繼續在報表中使用。

> [!NOTE] 在 2018 年 5 月 10 日的 Analytics 維護發行中，Adobe 已開始限制日期啟用和數值分類的功能。這些分類類型已從「管理員」和「分類匯入工具」介面中移除。無法新增日期啟用和數值分類。但仍可透過標準分類工作流程來管理 (上傳和刪除) 現有分類，並可繼續在報告中使用。

建立分類之後，您可以在整個 Adobe Analytics 中運用新的資料屬性。

**追蹤程式碼範例**

假設您不是只要使用追蹤程式碼檢視促銷活動，而是要依「搜尋引擎」、「關鍵字」和「促銷活動管道」查看促銷活動結果。您不必為每一項提供一個專用的轉換變數，而是可以為促銷活動建立三個變數分類，來代表「搜尋引擎」、「關鍵字」和「促銷活動管道」。這個策略可以讓您使用全部的四個變數查看網站成功事件，不需使用額外的標記。

Reports &amp; Analytics 包含追蹤程式碼變數預先定義分類，提供以分類為基礎的報告，名為「創作元素與促銷活動」。您必須以手動方式為其他所有轉換和流量變數設定分類。

請參閱「[流量分類](/help/admin/admin/c-traffic-variables/traffic-classifications.md)」和「[轉換分類](https://marketing.adobe.com/resources/help/zh_TW/reference/conversion_classifications.html)」。

下表描述多種可用的分類，以及各種支援類別的變數。上傳資料檔案之前，請先檢閱[一般檔案結構](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md)。

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
   <td colname="col3"> <p>文字分類定義的類別可讓您根據不同的報告用途將變數資料分組。 </p> <p>例如，如果您販賣襯衫，也許會想要根據顏色、大小及樣式來歸類襯衫的銷售 (轉換) 情形，這樣一來，您便可以產生報告以查閱依這些類別組織的襯衫銷售情形。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 啟用日期的文字</span> </p> <p>注意：在 2018 年 5 月 10 日的 Analytics 維護發行中，Adobe 已開始限制日期啟用分類的功能。這些分類類型已從「管理員」和「分類匯入工具」介面中移除。無法新增日期啟用分類。但仍可透過標準分類工作流程來管理 (上傳和刪除) 現有分類，並可繼續在報告中使用。 </p> </td> 
   <td colname="col2"> <p>轉換變數 </p> </td> 
   <td colname="col3"> <p>啟用日期的文字分類可讓您將日期範圍指定給文字分類。它通常能搭配促銷活動分類，以便讓您在<span class="wintitle">促銷活動</span>報告中善用甘特圖檢視的優點。 </p> <p>您可以在負責填入分類資料的資料檔案中加入實際的促銷活動日期。 </p> <p>即使已過了促銷活動的結束日期，Reports &amp; Analytics 仍會收集促銷活動追蹤程式碼，不過在促銷活動結束日期之後收集而來的促銷活動資料不會與促銷活動相關聯。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 數值</span> <p>注意：在 2018 年 5 月 10 日的 Analytics 維護發行中，Adobe 已開始限制數值分類的功能。這些分類類型已從「管理員」和「分類匯入工具」介面中移除。無法新增數值分類。但仍可透過標準分類工作流程來管理 (上傳和刪除) 現有分類，並可繼續在報告中使用。 </p> </p> </td> 
   <td colname="col2"> <p>轉換變數 </p> </td> 
   <td colname="col3"> <p>數值分類可讓您將固定數值套用至<span class="wintitle">轉換</span>報告。這些分類會顯示為報告中的量度。 </p> <p>在考量是否要新增<span class="wintitle">數值</span>分類時，數值必須固定且不會隨著時間改變。 </p> </td> 
  </tr> 
 </tbody> 
</table>

