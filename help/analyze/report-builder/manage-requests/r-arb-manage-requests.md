---
description: Report Builder 中「管理請求」的欄位說明。
seo-description: Report Builder 中「管理請求」的欄位說明。
seo-title: 管理請求 - 定義
solution: Analytics
title: 管理請求 - 定義
topic: Report Builder
uuid: 01b21d0e-c870-4df8-95b9-f4aef1f4d16b
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# 管理請求 - 定義

Report Builder 中「管理請求」的欄位說明。

## 概述 {#section_75C288C945FA4781A4EDF806711A5660}

「[!UICONTROL 請求管理員]」能針對您為所有工作表建立的所有請求，提供詳細狀態檢視，或只提供使用中活頁簿內一份工作表的詳細狀態檢視。您也可以針對含有舊有請求的 Excel 試算表，在可用的儲存格內按一下滑鼠右鍵來新增、編輯、重新整理及刪除請求 (通常是與「[!UICONTROL 請求精靈]」和「[!UICONTROL 請求管理員]」相關的功能)。

按一 [!UICONTROL 下「管理] 」(在「報告建立工具」工具列 ****![](assets/edit_request.gif) 中)時，會顯示「請求管理員」。

> [!NOTE] Adobe Report builder只會在相同的工作表內實施請求相依性，而不會跨工作表執行。 將相依性限制在單一工作表中，可確保執行的時效性。

## 定義 {#section_FD29D8614DE74F32A0027FA130F40304}

<table id="table_0880204181074BDBBA37E3DF2972A672"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>所有工作表 </p> </td> 
   <td colname="col2"> <p>顯示作用中活頁簿內所有工作表的請求。若要檢視特定工作表的請求，請關閉此選項。當此選項關閉時，您必須按一下 Excel 報表底部的「工作表」索引標籤，才能在「<span class="wintitle">請求管理員</span>」中顯示與該工作表相關的請求。核取方塊旁的標籤表示目前正在活頁簿中使用的工作表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>工作表 </p> </td> 
   <td colname="col2"> <p>顯示活頁簿中工作表的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>報表套裝 </p> </td> 
   <td colname="col2"> <p>顯示報表套裝的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日期範圍 </p> </td> 
   <td colname="col2"> <p>顯示報表的指定日期範圍。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>粒度 </p> </td> 
   <td colname="col2"> <p>指定請求的詳細程度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 上一次執行 </p> </td> 
   <td colname="col2"> <p>指定 Report Builder 上次處理請求的日期。在適當的情況下，另有診斷訊息會出現在此表格的「<span class="wintitle">上一次執行</span>」欄中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>新增 </p> </td> 
   <td colname="col2"> <p>顯示「請求精靈」對話方塊。請參閱 <a href="/help/analyze/report-builder/data-requests/t-create-a-data-request.md"   > 建立資料請求</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>編輯 </p> </td> 
   <td colname="col2"> <p> (或「編輯多項) 編輯選擇的請求。系統會顯示「<span class="wintitle">請求精靈</span>」對話方塊。See <a href="/help/analyze/report-builder/manage-requests/t-edit-multiple-requests.md"   > Edit Multiple Requests</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>刪除 </p> </td> 
   <td colname="col2"> <p>刪除請求。您可以刪除多個選擇的請求。也可以只刪除清單中的一個請求，只要選擇請求，然後再按鍵盤的 Delete 鍵即可。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 選擇全部 </p> </td> 
   <td colname="col2"> <p>選擇所有請求。「<span class="wintitle">請求管理員</span>」會在請求清單的底部顯示您選擇的請求數量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>從儲存格 </p> </td> 
   <td colname="col2"> <p>從工作表取得請求的資料。如果請求與作用中工作表內目前選擇的儲存格關聯，系統會選擇清單中的關聯請求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 重新整理 </p> </td> 
   <td colname="col2"> <p>重新整理單一請求或選擇的請求。(請參閱 <a href="/help/analyze/report-builder/manage-requests/t-refresh-a-request.md"   > 重新整理請求</a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>重新整理清單 </p> </td> 
   <td colname="col2"> <p>重新整理所有顯示的請求。在重新整理所有請求時，將伺服器中的資訊更新到報表的時間與報表中請求的複雜度成正比。對於規模龐大的報表來說，重新整理所有請求可能需要花費幾分鐘的時間。有鑑於此，您可以先個別更新最迫切的請求，然後等到其他較閒逸的時間再選擇<span class="wintitle">重新整理所有請求</span>。 </p> <p> <p>附註: 在重新整理含有多個請求的工作表時，我們建議您經常到「<span class="wintitle">請求管理員</span>」檢查結果。發生請求失敗時，診斷欄中的錯誤訊息能協助您找出錯誤的來源。當請求失敗時，系統大多時候會顯示錯誤訊息；然而請注意，偶而系統不會產生任何錯誤訊息。您會發現重新整理作業並未更新含參考之儲存格內的資料，或是更新作業移除儲存格內的資料。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

