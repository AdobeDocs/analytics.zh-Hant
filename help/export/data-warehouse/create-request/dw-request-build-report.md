---
description: 說明如何建立 Data Warehouse 請求的步驟。
title: 為Data Warehouse請求建立報告
feature: Data Warehouse
exl-id: 34e84e39-e3b1-4184-898a-3fd222ff4d38
source-git-commit: 6a7bbf5103eb6e7f8a3738d27d1fbb189d951a99
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 42%

---

# 為Data Warehouse請求建立報告

建立 Data Warehouse 請求時有多種可用的設定選項。以下資訊說明如何建立請求的報告。

有關如何開始建立請求的資訊，以及其他重要設定選項的連結，請參閱「[建立 Data Warehouse 請求](/help/export/data-warehouse/create-request/t-dw-create-request.md)」。

若要建立Data Warehouse請求的報表：

1. 如果還沒有，可選取「**[!UICONTROL 工具]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **新增**]」，開始在 Adobe Analytics 中建立請求。

   有關其他詳細資訊，請參閱「[建立 Data Warehouse 請求](/help/export/data-warehouse/create-request/t-dw-create-request.md)」。

1. 在「新Data Warehouse請求」頁面上，選取「[!UICONTROL **建置您的報表**]」標籤。

   ![建置報告標籤](assets/build-report.png)

1. 在左上角，選擇建置Data Warehouse報表時要使用的報表套裝。

   並非所有在「區段產生器」中建立的區段都與 Data Warehouse 相容。如果您選擇的虛擬報表套裝包含不相容的區段，則會顯示錯誤。

   如需區段內支援的函式清單，請參閱[Data Warehouse區段相容性](/help/components/segmentation/seg-reference/seg-compatibility.md)。

1. 將任何區段、量度和維度拖曳至產生器。 您建置的報表會決定Data Warehouse請求中包含哪些資料。

1. 繼續在&#x200B;[!UICONTROL **報告目的地**]&#x200B;標籤上設定您的Data Warehouse要求。 有關詳細資訊，請參閱[為 Data Warehouse 請求設定報告目的地](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)。

<!--

Keep any of this? It was in the Overview article:

The following table describes the fields and options on the [!UICONTROL Data Warehouse Request] tab.

<table id="table_7325A2466866460E8B0AF7D696152713"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Request Name</span> </td> 
   <td colname="col2"> Identifies the request. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Reporting Date</span> </td> 
   <td colname="col2"> <p>The date and granularity of the request. </p> 
    <ul id="ul_C00F4529BD9E4113B517A61751B1DD5C"> 
     <li id="li_4D7C26812DF94ED7B64F985309541F46"> <span class="wintitle"> Custom</span>: A date range you configure in the calendar. </li> 
     <li id="li_2B272087006847148A936350D1B2D523"> <span class="wintitle"> Preset</span>: A preset range. The preset range is relative to the report date. </li> 
     <li id="li_745989965BB94D489FF7046587E13C42"> <span class="wintitle"> Granularity</span>: The time granularity. Valid values are None, Hour, Day, Week, Month, Quarter, and Year. </li> 
    </ul> <p>Data Warehouse reporting on virtual report suites supports the alternative time zone configured on the virtual report suite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Available Segments</span> </td> 
   <td colname="col2"> <p>Lets you select the part of the visitor population you want to examine and generate complex segments. You can load pre-configured segments, create new segments, and store segment components in a library to use in building additional segments. </p> <p>You can now stack segments. When selecting multiple segments, the preview area, the Request Manager, and the Request Detail popup show a comma-separated list of names (e.g., Segment1, Segment2). </p> <p>See the <a href="/help/components/segmentation/seg-home.md"> Segmentation Guide</a> for more information. </p> <p>Note:  You cannot include both a segment filter and a breakdown on the same segment, in the same Data Warehouse report. Doing so will result in an error. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Breakdowns</span> </td> 
   <td colname="col2"> <p>Lets you categorize data using breakdowns. Segments and breakdowns differ in that a segment filters data out of a data set, while a breakdown compartmentalizes data across all valid values for the breakdown. </p> You can also break down a report by one or more segments. However, you cannot include both a segment filter and a breakdown on the same segment, in the same Data Warehouse report. Doing so will result in an error. <p> For example, use segments to remove a gender from the data set, and use a breakdown to see data separated by gender. </p> <p>When a Data Warehouse request is submitted with multiple multi-value dimensions (e.g., various Mobile Reports), an exponential number of rows can be generated from a single hit. The number of rows that can be output from a single hit is capped at 100 (previously 1,000). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Metrics</span> </td> 
   <td colname="col2">Lets you add metrics that you want to report on. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Metrics Sort</span> </td> 
   <td colname="col2">Provides ranked breakdown reports, sorted by descending metric value, similar to what is displayed in the Reports &amp; Analytics user interface, Data Workbench, etc. <a href="/help/export/data-warehouse/sorting-by-metric.md"  > More...</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Schedule Delivery</span> </td> 
   <td colname="col2"> <p>Lets you schedule requests for automatic delivery at selected intervals, or as a one-time report. If you use the default format, the report arrives in an email as a .csv file. </p> <p>To add the date range, include <span class="filepath"> %R</span> in the filename. This value represents the date values requested in the report. For example, if you request data from May 1, 2013 through May 7, 2013, the <span class="filepath"> %R</span> shows a filename including the date range of 20130501 - 20130507. </p> </td> 
  </tr> 
 </tbody> 
</table>

-->
