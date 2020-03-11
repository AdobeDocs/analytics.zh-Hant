---
description: Data Warehouse 是指用於儲存和自訂報表的 Analytics 資料複本，可供您透過篩選資料的方式來執行。您可以要求報告依據您的特定問題，從原始資料顯示進階資料關係。Data Warehouse 報告會以電子郵件方式或透過 FTP 傳送，處理時間最長需要 72 小時。處理時間依查詢的複雜度以及請求的資料量而定。
title: Data Warehouse 概觀
topic: Data warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Data Warehouse 概觀

Data Warehouse 是指用於儲存和自訂報表的 Analytics 資料複本，可供您透過篩選資料的方式來執行。您可以要求報告依據您的特定問題，從原始資料顯示進階資料關係。Data Warehouse 報告會以電子郵件方式或透過 FTP 傳送，處理時間最長需要 72 小時。處理時間依查詢的複雜度以及請求的資料量而定。

Adobe 僅針對管理員層級使用者，在特定報表套裝上啟用 Data Warehouse(DataWarehouse 可在全域及子報表套裝上啟用，但不可用於統計報表套裝)。管理員可建立存取資料倉儲的群組，然後將非管理員級別的使用者與該群組關聯。

Data Warehouse 會自動壓縮大小超過 1 MB 的檔案。電子郵件附件大小上限是 10 MB。

Data Warehouse 針對個別已排程和已下載報表，可處理單一請求中的無限制列數。

> [!NOTE] Data Warehouse 會報告在報告時段遇到的第一個值。

>[!IMPORTANT]
>
>依據分類的值進行分段時，Analysis Workspace 和 Data Warehouse 會將「未指定」的值視為不同的值處理。Workspace 中的「未指定」是指未分類的值，而 Data Warehouse 中的「未指定」是指您分類為「未指定」的值。

## Data Warehouse 請求說明 {#section_F21C78ED36884C389C852E876AF5CDE8}

本表說明「[!UICONTROL Data Warehouse 請求]」標籤中的欄位和選項。

<table id="table_7325A2466866460E8B0AF7D696152713"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 請求名稱</span> </td> 
   <td colname="col2"> 識別請求。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 報告日期</span> </td> 
   <td colname="col2"> <p>請求的日期和詳細程度。 </p> 
    <ul id="ul_C00F4529BD9E4113B517A61751B1DD5C"> 
     <li id="li_4D7C26812DF94ED7B64F985309541F46"> <span class="wintitle">自訂</span>：您在日曆中設定的日期範圍。 </li> 
     <li id="li_2B272087006847148A936350D1B2D523"> <span class="wintitle">預設</span>：預設範圍。預設範圍是相對於報告日期。 </li> 
     <li id="li_745989965BB94D489FF7046587E13C42"> <span class="wintitle">詳細程度</span>：時間詳細程度。有效值為無、小時、日、週、月份、季度或年。 </li> 
    </ul> <p>報告虛擬報表套裝的 Data Warehouse 支援虛擬報表套裝上設定的替代時區。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 可用區段</span> </td> 
   <td colname="col2"> <p>可讓您選擇要檢查的部分訪客人口並產生複雜區段。您可以載入預先設定的區段、建立新區段以及將區段元件儲存至建立其他區段時要使用的庫中。 </p> <p>您現在可以堆疊區段。選取多個區段時，預覽區域、「請求管理員」和「請求詳細資訊」彈出式功能表會顯示逗號分隔的名稱清單 (例如 Segment1, Segment2)。 </p> <p>請參閱<a href="/help/components/c-segmentation/seg-home.md">分段指南</a>，瞭解更多資訊。 </p> <p>注意：您不能在同一個 Data Warehouse 的同一個區段上，同時包括區段篩選和劃分。這麼做會導致錯誤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 劃分</span> </td> 
   <td colname="col2"> <p>可讓您使用劃分來分類資料。區段與劃分不同，區段是從資料集中篩選資料，而劃分則是從所有有效值中分類資料以進行劃分。 </p> 您也可以依一或多個區段劃分報表。但是，您不能在同一個 Data Warehouse 的同一個區段上，同時包括區段篩選和劃分。這麼做會導致錯誤。 <p> 例如，使用區段可從資料集中移除性別，使用劃分則可查看依照性別分隔開的資料。 </p> <p>若用多個多值維度 (例如，各種行動報表) 提交 Data Warehouse 請求，單次點擊會產生大量的資料列。可從單次點擊輸出的資料列數量上限是 100 (先前為 1,000)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 量度</span> </td> 
   <td colname="col2">可讓您新增要報告的量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> 量度排序</span> </td> 
   <td colname="col2">提供依遞減量度值排序的排名劃分報表，類似於「Reports &amp; Analytics」使用者介面、Data Workbench 等等顯示的項目。<a href="/help/export/data-warehouse/sorting-by-metric.md"  > 更多...</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 排程傳送</span> </td> 
   <td colname="col2"> <p>可讓您排程請求在選定時間間隔自動傳送，或僅傳送一次報告。如果您使用預設格式，報告在電子郵件中為 .csv 格式的檔案。 </p> <p>若要新增日期範圍，請在檔案名稱中加上 <span class="filepath">%R</span>。此值表示報告中請求的日期值。例如，若您請求從 2013 年 5 月 1 日到 2013 年 5 月 7 日的資料，<span class="filepath">%R</span> 會顯示包含 20130501 - 20130507 日期範圍的檔案名稱。 </p> </td> 
  </tr> 
 </tbody> 
</table>

