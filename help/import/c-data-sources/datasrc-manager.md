---
description: 在報表套裝中建立、管理、檢視資料來源的使用。
subtopic: Data sources
title: 資料來源管理員
topic: Developer and implementation
uuid: ccfa4a1c-7c56-421b-8ee6-a42b334659b1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 資料來源管理員

在報表套裝中建立、管理、檢視資料來源的使用。

**[!UICONTROL Analytics]** &gt;管 **[!UICONTROL 理]** &gt;資 **[!UICONTROL 料來源]**。

## 建立標籤 {#section_74603FDA3D8842E49F1A51624A06DE20}

「[!UICONTROL 建立]」標籤讓您可以為目前選取的報表套裝設定新的資料來源。啟用資料來源後，「[!UICONTROL 資料來源精靈]」將引導您完成建立資料來源範本的整個過程，並將建立一個上傳資料的 FTP 地址。

您在「建立」標籤中的選取，將決定建立的範本一開始有什麼欄位。如需詳細資訊，請參閱[產生匯入檔案範本](/help/import/c-data-sources/datasrc-template/t-datasrc-creating-data-sources-file.md)。

## 管理標籤 {#section_DD559A6701CA45F1A85E56F840F48DBE}

<table id="table_F74696EC855441328CFE0BF49C20D9B0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>選項 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>重新開始處理 </p> </td> 
   <td colname="col2"> <p>重新開始之前因錯誤或警告而停止的資料來源處理。處理將繼續進行，直到發生下一個錯誤。只有當您選取「<span class="uicontrol">出現錯誤時停止處理</span>」時，資料來源才會停止處理資料來源檔案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>完成處理 </p> </td> 
   <td colname="col2"> <p>指示資料來源關閉檔案中所有已開啟的造訪，並完成資料來源檔案的處理。當您有跨越多個資料來源檔案的造訪時，這功能相當實用。這僅適用於 <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md"   > 完全處理</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>停用 </p> </td> 
   <td colname="col2"> <p> 如果停用資料來源，則會將其刪除。如果已開始處理伺服器上的任何檔案，則將繼續處理直到完成。尚未開始處理的檔案將不會加以處理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>出現錯誤/警告時停止處理 </p> </td> 
   <td colname="col2"> <p> 指示資料來源處理引擎在遇到錯誤時停止處理。要等到您選取「重新開始處理」後，才會繼續處理資料來源。「出現警告時停止處理」選項僅適用於 <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md"   > 完全處理</a>. </p> <p>當資料來源遇到檔案錯誤，會通知您發生錯誤。系統會將有錯誤的資料來源檔案移到 FTP 伺服器上名為 <span class="filepath">files_with_errors</span> 的資料夾。在您解決問題後，將資料來源檔案重新提交處理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>設定 </p> </td> 
   <td colname="col2"> <p>可讓您修改資料來源範本或其他與此資料來源相關的設定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FTP 資訊 </p> </td> 
   <td colname="col2"> <p>顯示此資料來源的 FTP 資訊。使用此資訊存取「資料來源」範本以及傳送「資料來源」資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>檔案名稱 </p> </td> 
   <td colname="col2"> <p>上傳檔案的名稱 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>狀態 </p> </td> 
   <td colname="col2"> <p> 檔案的目前狀態。可能的狀態值有: </p> 
    <ul id="ul_56A0BF8C1BE249F6BB39B0D11DA3997F"> 
     <li id="li_BAB359E08EDE4E0298C0362258789603">在佇列中 (3 個步驟中的步驟 1): 檔案存在，但尚未開始處理。If the file doesn't appear within 30 minutes, check that the associated <span class="filepath"> .fin</span> file is present </li> 
     <li id="li_A09A14F42CB74F01B694799740B3DA17">準備中 (3 個步驟中的步驟 2): 正在檢查檔案有無錯誤或警告 </li> 
     <li id="li_793FDCDB64CF434D82CAF5B6E9BDE557">處理中 (3 個步驟中的步驟 3): 正在處理檔案 </li> 
     <li id="li_1D8C4B241FF0453EAF7DDFD8354C5573">失敗: 因出現錯誤，檔案未被處理 </li> 
     <li id="li_A52507602FB4492B83A70AF6449A539A">成功: 檔案已完成處理 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 檔案記錄標籤 {#section_B7AC7EE8CAD740A59DD53CF1919373F0}

檔案記錄有搜尋功能，可讓您依資料來源名稱、資料來源類型、檔案名稱、接收日期或狀態搜尋資訊。
