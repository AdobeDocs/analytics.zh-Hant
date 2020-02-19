---
description: 使用「表格產生器」，可以用任何度量、維度和區段的設定來建立報表。例如，您可以新增多個度量到「表格產生器」，然後一次將區段套用於所有度量。您可以套用工具窗格中的項目成為列和劃分，或套用成為欄，並且輕鬆地旋轉表格來呈現不同的檢視。建立表格後，您可直接與產生的資料表格互動，以便進一步分析。請記住，從「表格產生器」產生資料表格會執行查詢，並建立新的資料表格。
title: 表格產生器
uuid: d5dbd05e-9ebd-4571-b3a5-3856c28b65f3
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 表格產生器

使用「表格產生器」，可以用任何度量、維度和區段的設定來建立報表。例如，您可以新增多個度量到「表格產生器」，然後一次將區段套用於所有度量。您可以套用工具窗格中的項目成為列和劃分，或套用成為欄，並且輕鬆地旋轉表格來呈現不同的檢視。建立表格後，您可直接與產生的資料表格互動，以便進一步分析。請記住，從「表格產生器」產生資料表格會執行查詢，並建立新的資料表格。

## 表格產生器 {#concept_574FEDC73B244101935D3C86C39DB70F}

使用「表格產生器」，可以用任何度量、維度和區段的設定來建立報表。例如，您可以新增多個度量到「表格產生器」，然後一次將區段套用於所有度量。您可以套用工具窗格中的項目成為列和劃分，或套用成為欄，並且輕鬆地旋轉表格來呈現不同的檢視。建立表格後，您可直接與產生的資料表格互動，以便進一步分析。請記住，從「表格產生器」產生資料表格會執行查詢，並建立新的資料表格。

[!UICONTROL 表格產生器]不適用於某些路徑報表，如[!UICONTROL 站點分析]、[!UICONTROL 流失]、[!UICONTROL 流量]和[!UICONTROL 虛擬重點]。

## 表格產生器描述{#section_4B7B96546B864142AB91DF3996918590}

<table id="table_C11D78E62DEF48A78B50EFB8669817BC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 行 / 劃分</span> </td> 
   <td colname="col2"> <p>從加入的項目建立行和劃分。您拖曳至<span class="wintitle">行/劃分</span>的第一個項目會成為資料表格中的最左欄，或是劃分中的父項目。繼續加入其他項目，即可建立劃分。 </p> <p>例如，如果您先後加入「頁面」和「城市」維度，則報表會依城市劃分頁面。您可以使用下列功能表，設定每個項目要顯示多少行和劃分： </p> 
    <ul id="ul_702F215DFB814398B8F1879EDFEC103F"> 
     <li id="li_95C4DF2B33524C94BBD2E07397393300"> <span class="uicontrol"> 顯示</span>和<span class="uicontrol">劃分</span>：可讓您指定要顯示的項目及劃分數量。 </li> 
     <li id="li_D594C7F31A094D1EA1A070B80794E006"> <span class="uicontrol">預設</span>：使用<span class="wintitle">劃分屬性</span>中的設定值。 </li> 
    </ul> <p>例如，您也可以設定固定值清單，以多個度量劃分一個度量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 劃分屬性</span> </td> 
   <td colname="col2"> <p><img placement="inline"  src="assets/Settings_Illustrative.png" id="image_C46860621CF94E88AF592B8660F28E57"> </img> </p> <p>可讓您指定要顯示多少行與劃分 (依加入項目的順序而顯示) 的預設設定。您可以指定每頁顯示多少總計結果，以及要劃分多少行。 </p> <p>您在<span class="wintitle">表格產生器</span>中進行的設定會覆寫<span class="wintitle">劃分屬性</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 編輯項目</span> </td> 
   <td colname="col2"> <p><img  src="assets/Edit_Buttcon.png" id="image_E44BCC4B0BFF453D8564047E3DA2501A"> </img> </p> <p>選擇維度項目清單以建立劃分所需的固定清單。當您將項目新增至此清單時，這些項目將永久保留在儲存的報表中，而且當您開啟儲存或計劃的報表時，這些項目不會收合。 </p> <p>請參閱<a href="/help/analyze/ad-hoc-analysis/c-reports-configure.md#task_29BEE0AF09DA4625B9B44BAB77D7C841"  >劃分表格資料</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">「欄」</span> </td> 
   <td colname="col2"> <p>可讓您建立欄，內含維度、區段及度量等項目。您也可以使用旋轉 X 軸和 Y 軸的箭頭圖示來旋轉欄。 </p> <p> <span class="uicontrol">顯示</span>：可讓您限制資料表格中產生的欄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 摘要</span> </td> 
   <td colname="col2"> <p>可顯示報表的結構配置，讓您知道將會建立多少行和欄。摘要會反映<span class="uicontrol">行/劃分</span>和<span class="uicontrol">欄</span>群組中所指定的設定值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 取代表格</span> </td> 
   <td colname="col2"> <p>根據您的<span class="wintitle">表格產生器</span>設定，建立 (並覆寫) 現有表格。 </p> <p>注意：按下<span class="uicontrol">取代表格</span>會重新執行報表，並覆寫表格格線中的資料。如果您在表格格線中加入項目，則表格和<span class="wintitle">表格產生器</span>之間的關聯不再有效。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 警告 </td> 
   <td colname="col2"> <p><img id="image_619E1068C6084D41853DA3DD6B85DFC9"  src="assets/AlertRed_Illustrative.png" placement="inline" /> </p> <p>指出<span class="wintitle">表格產生器</span>的設定不會傳回資料，或未選取度量。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 從表格產生器產生報表 {#task_B04801AC9848485C93DF02E96C9A9902}

說明如何使用[!UICONTROL 表格產生器]的步驟。

<!-- 

t_table_builder.xml

 -->

1.  若要存取[!UICONTROL 表格產生器]，請執行支援的報表，並按一下&#x200B;**[!UICONTROL 表格產生器]**。
1. 從工具窗格拖曳元素 (維度、度量、區段) 至[!UICONTROL 表格產生器]。
1. 將項目設定為行、劃分和欄。
1. 按一下&#x200B;**[!UICONTROL 取代表格]**，執行報表。

   按下&#x200B;**[!UICONTROL 取代表格]**&#x200B;會執行新查詢，並建立新的資料表格。手動編輯詳情表格並不會反映在「表格產生器」中。

