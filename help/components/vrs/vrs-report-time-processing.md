---
description: 報告時間處理是虛擬報表套裝設定，可讓資料以非破壞性、可回溯性的方式處理。
seo-description: 報告時間處理是虛擬報表套裝設定，可讓資料以非破壞性、可回溯性的方式處理。
seo-title: 報表時間處理功能
title: 報表時間處理功能
uuid: a1d82ea-8c93-43cc-8689-cdf59 c309 b1
translation-type: tm+mt
source-git-commit: 1e8d5af54ab22311e1c3967979c8bdc982a66d5b

---


# 報表時間處理功能

報告時間處理是虛擬報表套裝設定，可讓資料以非破壞性、可回溯性的方式處理。

>[!NOTE]
>
>報表時間處理僅適用於分析工作區。

「報表時間處理功能」僅會影響虛擬報表套裝中的資料，不會影響基本報表套裝中的任何資料或資料集合。您可透過下列圖表，詳細瞭解「報表時間處理功能」與傳統 Analytics 處理功能的差異:

![](assets/google1.jpg)

在 Analytics 處理資料期間，資料會透過資料收集管道流動，而進入前置處理步驟，以準備資料進行報告。此前置處理步驟會在收集資料時，將造訪過期時間邏輯與 eVar 持續性邏輯 (與其他項目) 套用至資料。此前置處理模式的主要缺點，在於需要在資料收集前完成所有設定。這表示任何前置處理設定變更僅會套用至該時間之後的新資料。如果發生資料接收順序錯亂或設定失誤，將會造成問題。

「報表時間處理功能」在處理 Analytics 用於報告的資料時，所採用的方法是截然不同的。Analytics 不會在資料收集前預先定義處理邏輯，而是會在前置處理步驟進行期間忽略資料集，並在每次執行報表時套用此邏輯。

![](assets/google2.jpg)

此處理架構可提供更具彈性的報告選項。例如，您可採用非破壞性的方式，將造訪逾時期間變更為您想要的任何時間長度，而這些變更將會以回溯方式反映在 eVar 持續性和區段容器，如同您已在資料收集前所套用的這些設定。此外，您可以建立任意數量的虛擬報表套裝，並根據相同的基本報表套裝，讓每個套裝使用不同的「報表時間處理功能」選項，而不變更基本報表套裝中的任何資料。

「報表時間處理功能」還能使 Analytics 防止背景點擊開始新的造訪，並可讓[行動 SDK](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) 在每次應用程式啟動事件觸發時，指示報告開始一個新的造訪。

下列為啟用「報表時間處理功能」時，目前可供虛擬報表套裝使用的設定選項:

<table id="table_C086C5FD10A84A1ABC081F5DE28F802D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 造訪逾時 </p> </td> 
   <td colname="col2"> <p> 造訪逾時設定會在自動開始新造訪前，定義不重複訪客必須達到的閒置時間。已預設為 30 分鐘。例如，若您將造訪逾時設為 15 分鐘，系統便會針對收集到的各點擊順序建立新的造訪分組，並按照 15 分鐘閒置時間加以區隔。此設定不僅會影響您的造訪計數，也會影響評估造訪區段容器的方式，以及造訪時過期之任何 eVar 的造訪過期時間邏輯。降低造訪逾時可能會增加報告中的造訪總數，但是增加造訪逾時可能會減少報告中的造訪總數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 行動應用程式造訪設定 </p> </td> 
   <td colname="col2"> <p> 若報表套裝包含透過 <a href="https://www.adobe.io/apis/cloudplatform/mobile.html" format="html" scope="external">Adobe Mobile SDK</a> 的行動應用程式產生的資料，則可使用其他造訪設定。這些非破壞性設定僅會影響已透過 Mobile SDK 收集的點擊數。該設定不會影響非透過 Mobile SDK 收集的資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 避免背景點擊數開始一次新造訪 </p> </td> 
   <td colname="col2"> <p> 當應用程式處於背景狀態時，Mobile SDK 會收集背景點擊數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 每次應用程式啟動後開始新的造訪 </p> </td> 
   <td colname="col2"> <p> 除造訪逾時設定外，您也可以在 Mobile SDK 記錄應用程式啟動事件時強制開始造訪，而不考量閒置視窗。此設定會影響造訪量度與造訪區段容器，以及 eVar 的造訪過期時間邏輯。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>開始事件的新造訪 </p> </td> 
   <td colname="col2"> <p>不論作業階段是否已逾期，事件觸發時就會開始新的工作階段。新建立的工作階段將會包含啟動的事件。此外，您可以使用多個事件來啟動工作階段，如果資料中觀察到其中一個事件，就會觸發新的工作階段。此設定將會影響您的造訪計數、造訪區段容器以及 eVar 的造訪過期時間邏輯。 </p> </td> 
  </tr> 
 </tbody> 
</table>

「報表時間處理功能」不支援傳統 Analytics 報告中提供的所有量度與維度。Virtual report suites utilizing Report Time Processing are only accessible in Analysis Workspace and will not be accessible in [!UICONTROL Reports &amp; Analytics], Ad Hoc Analysis, Data Warehouse, Report Builder, Data Feeds, or the reporting API.

此外，「報表時間處理功能」僅會處理來自報告日期範圍內 (以下稱為「日期時段」) 的資料。這表示在報告日期範圍前，針對訪客設定為「永不過期」的 eVar 值不會保存至報告視窗，也不會出現在報表中。另外，這也表示客戶忠誠度測量均僅以顯示於報告日期範圍內的資料為根據，而非報告日期範圍前的完整記錄。

以下為目前未支援使用「報表時間處理功能」的量度與維度清單:

<table id="table_127AFE8FA1BE4F2BAB3975CA12A2FA47"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度/維度名稱 </th> 
   <th colname="col2" class="entry"> 報表時間處理功能附註 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 目標分析 </p> </td> 
   <td colname="col2"> <p> 目前尚未支援。已規劃於未來支援。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Advertising Cloud保留量度/維度的Analytics </p> </td> 
   <td colname="col2"> <p> 目前尚未支援。已規劃於未來支援。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 單次存取量度 </p> </td> 
   <td colname="col2"> <p> 目前及未來均不支援。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 清單 Var </p> </td> 
   <td colname="col2"> <p> 目前尚未支援。已規劃於未來支援。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 計數器 eVar </p> </td> 
   <td colname="col2"> <p> 目前及未來均不支援。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 行銷管道變數 </p> </td> 
   <td colname="col2"> <p> 目前尚未支援。已規劃於未來支援。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 上次購買間隔天數維度 </p> </td> 
   <td colname="col2"> <p> 由於「報表時間處理」日期範圍性質的緣故，不支援此維度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 首次購買間隔天數維度 </p> </td> 
   <td colname="col2"> <p> 由於「報表時間處理」日期範圍性質的緣故，不支援此維度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 回訪頻率維度 </p> </td> 
   <td colname="col2"> <p> 由於「報表時間處理」日期範圍性質的緣故，不支援此維度。 </p> <p> 您可以使用區段中的造訪次數量度，或使用色階分佈圖報表中的造訪量度做為替代方法。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 上次造訪間隔天數維度 </p> </td> 
   <td colname="col2"> <p> 由於「報表時間處理」日期範圍性質的緣故，不支援此維度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 登入頁面原始維度 </p> </td> 
   <td colname="col2"> <p> 由於「報表時間處理」日期範圍性質的緣故，不支援此維度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 線性配置 eVar </p> </td> 
   <td colname="col2"> <p> 目前尚未支援。已規劃於未來支援。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 原始反向連結網域維度 </p> </td> 
   <td colname="col2"> <p> 目前尚未支援。已規劃於未來支援。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 訪問次數 </p> </td> 
   <td colname="col2"> <p> 由於「報表時間處理」日期範圍性質的緣故，不支援此量度。 </p> <p> 若要報告行動應用程式中的新訪客與重複訪客，您可以搭配使用計算量度 (包括訪客數/造訪次數) 與應用程式安裝量度，以識別新訪客或新造訪。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 交易 ID 資料來源 </p> </td> 
   <td colname="col2"> <p> 目前尚未支援。已規劃於未來支援。 </p> </td> 
  </tr> 
 </tbody> 
</table>

以下為根據選取之「報表時間處理功能」設定，而受影響的維度與量度清單:

<table id="table_491E48C55BC84917B4A8EACBF04C939F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度/維度名稱 </th> 
   <th colname="col2" class="entry"> 報表時間處理功能附註 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 不重複訪客量度 </p> </td> 
   <td colname="col2"> <p> 如果啟用「避免背景點擊數開始一次新造訪」，則不重複訪客項目不會將報告日期範圍中僅執行背景點擊的訪客納入。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 瀏覽 </p> </td> 
   <td colname="col2"> <p> 造訪項目會反映虛擬報表套裝的任何設定，而這些設定可能會與基本報表套裝有所差異。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 具有事件 ID 的序列化事件 </p> </td> 
   <td colname="col2"> <p> 使用具有事件 ID 之事件序列化的事件，僅會因為「報表時間處理」日期範圍的緣故，就報告日期範圍內所發生的事件刪除重複的事件，而非就所有日期或所有訪客全面刪除重複的事件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 購買/收入/訂購/單位 </p> </td> 
   <td colname="col2"> <p> 當您使用購買 ID 時，這些量度僅會因為「報表時間處理」日期範圍的緣故，就報告日期範圍內訪客所發生的重複購買 ID 刪除重複的部分，而非就所有日期或所有訪客全面刪除重複的部分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 彈回數/彈回率 </p> </td> 
   <td colname="col2"> <p> 如果啟用「避免背景點擊數開始一次新造訪」，則系統不會將未跟隨著前景點擊數之背景點擊數視為彈回，也不會將其列入彈回率貢獻。如需詳細資訊，請參閱 <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> 內容感應整合功能。</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 每次造訪逗留時間秒數 </p> </td> 
   <td colname="col2"> <p> 如果啟用「避免背景點擊數開始一次新造訪」，則系統僅會將包括前景點擊數的造訪列入此量度貢獻。如需詳細資訊，請參閱 <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> 內容感應整合功能。</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 每次造訪逗留時間 </p> </td> 
   <td colname="col2"> <p> 如果啟用「避免背景點擊數開始一次新造訪」，則系統僅會將包括前景點擊數的造訪列入此量度貢獻。如需詳細資訊，請參閱 <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> 內容感應整合功能。</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 登入點 </p> </td> 
   <td colname="col2"> <p> 如果啟用「避免背景點擊數開始一次新造訪」，則系統僅會將包含前景點擊之造訪的登入點列入考量。如需詳細資訊，請參閱 <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> 內容感應整合功能。</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 非銷售 eVar/保留 eVar </p> </td> 
   <td colname="col2"> <p> 在 eVar 中設定的值，只有在因為「報表時間處理」日期範圍，而於報告日期範圍內設定時才會加以保存。 </p> <p> 此外，如果保存涵蓋日光節約時間變更，則過期時間可能會提前或延後一小時到期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 銷售 eVar/保留 eVar </p> </td> 
   <td colname="col2"> <p> 請參閱以上內容。 </p> <p> 此外，針對轉換語法方面，其中設定為「any event」(任何事件) 的繫結項目，將會改用「any hit」(任何點擊)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 登入與退出維度 </p> </td> 
   <td colname="col2"> <p> 如果啟用「避免背景點擊數開始一次新造訪」，則此維度中僅會出現含有前景點擊數之造訪的登入與退出。如需詳細資訊，請參閱 <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> 內容感應整合功能。</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 點擊類型 </p> </td> 
   <td colname="col2"> <p> 此維度會將點擊類型指定為前景或背景。 </p> </td> 
  </tr> 
 </tbody> 
</table>

