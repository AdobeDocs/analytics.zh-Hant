---
description: 資料倉庫是指儲存空間和自訂報表的Analytics資料復本，您可透過篩選資料來執行。 您可以要求報表依據您的特定問題，從原始資料顯示進階資料關係。資料倉庫報表會以電子郵件傳送或透過FTP傳送，處理時間最長可能需要72小時。 處理時間取決於查詢的複雜性和請求的資料量。
title: Data Warehouse 概觀
topic: Data warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Data Warehouse 概觀

「資料倉庫」是指儲存空間和自訂報表的Analytics資料復本，您可透過篩選資料來執行。 您可以要求報表依據您的特定問題，從原始資料顯示進階資料關係。資料倉庫報表會以電子郵件傳送或透過FTP傳送，處理時間最長可能需要72小時。 處理時間取決於查詢的複雜性和請求的資料量。

Adobe僅針對管理員層級的使用者，針對特定報表套裝啟用「資料倉庫」。 （可針對全域和子報表套裝啟用，但不適用於統計報表套裝）。管理員可以建立可存取「資料倉庫」的群組，然後將非管理員層級的使用者關聯至該群組。

資料倉庫會自動壓縮大小超過1 MB的檔案。 電子郵件附件大小上限為10 MB。

「資料倉庫」可針對個別的已排程和已下載報表，在單一請求中處理不限數量的列。

>[!NOTE] Data Warehouse 會報告在報告時段遇到的第一個值。

>[!IMPORTANT]
>
>依據分類的值進行分段時，Analysis Workspace 和 Data Warehouse 會將「未指定」的值視為不同的值處理。Workspace 中的「未指定」是指未分類的值，而 Data Warehouse 中的「未指定」是指您分類為「未指定」的值。

## Data Warehouse 請求說明 {#section_F21C78ED36884C389C852E876AF5CDE8}

此表說明了頁籤上的欄位和 [!UICONTROL Data Warehouse Request] 選項。

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
    </ul> <p>虛擬報表套裝的資料倉庫報表支援虛擬報表套裝上設定的替代時區。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 可用區段</span> </td> 
   <td colname="col2"> <p>可讓您選取您要檢查的部分訪客人口，並產生複雜的區段。 您可以載入預先設定的區段、建立新區段，以及將區段元件儲存在程式庫中，以用於建立其他區段。 </p> <p>您現在可以堆疊區段。 選取多個區段時，預覽區域、「請求管理員」和「請求詳細資料」彈出式選單會顯示逗號分隔的名稱清單（例如Segment1、Segment2）。 </p> <p>請參閱<a href="/help/components/c-segmentation/seg-home.md">分段指南</a>，瞭解更多資訊。 </p> <p>注意：您不能在同一個 Data Warehouse 的同一個區段上，同時包括區段篩選和劃分。這麼做會導致錯誤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 劃分</span> </td> 
   <td colname="col2"> <p>可讓您使用劃分來分類資料。 區段和劃分的不同之處在於，區段會從資料集中篩選資料，而劃分則會將資料分割為所有有效值，以供劃分使用。 </p> 您也可以依一或多個區段來劃分報表。 不過，您不能在同一個「資料倉儲」報表中同時包含相同區段的區段篩選和劃分。 這麼做會導致錯誤。 <p> 例如，使用區段從資料集中移除性別，並使用劃分查看依性別分隔的資料。 </p> <p>當以多個多值維度（例如各種行動報表）提交資料倉庫請求時，單次點擊可產生指數數列。 可從單一點擊輸出的列數上限為100（先前為1,000）。 </p> </td> 
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
   <td colname="col2"> <p>可讓您排程請求，以在選取的間隔自動傳送，或以單次報表的形式傳送。 如果您使用預設格式，報表會以。csv檔案形式以電子郵件形式送達。 </p> <p>若要新增日期範圍，請在檔案名稱中加上 <span class="filepath">%R</span>。此值表示報告中請求的日期值。例如，若您請求從 2013 年 5 月 1 日到 2013 年 5 月 7 日的資料，<span class="filepath">%R</span> 會顯示包含 20130501 - 20130507 日期範圍的檔案名稱。 </p> </td> 
  </tr> 
 </tbody> 
</table>

