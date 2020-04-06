---
description: Report Builder 中「管理請求」的欄位說明。
title: 管理請求 - 定義
topic: Report builder
uuid: 01b21d0e-c870-4df8-95b9-f4aef1f4d16b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 管理請求 - 定義

Report Builder 中「管理請求」的欄位說明。

## 概述 {#section_75C288C945FA4781A4EDF806711A5660}

提供 [!UICONTROL Request Manager] 您針對所有工作表或作用中活頁簿的單張工作表所建立之所有請求狀態的詳細檢視。 您也可以在包含先前請求的Excel試算表中，以滑鼠右鍵按一下可用的儲存格，新增、編輯、重新整理及刪除請求(通常與 [!UICONTROL Request Wizard][!UICONTROL Request Manager]and相關的函式)。

The [!UICONTROL Request Manager] displays when you click **[!UICONTROL Manage]** ( ![](assets/edit_request.gif) in the Report Builder toolbar.

>[!NOTE] Adobe Report Builder 只會在同一個工作表中執行請求相依性，不會跨工作表執行。將相依性限制在單一工作表中，可確保執行的時效性。

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
   <td colname="col2"> <p>顯示作用中活頁簿中所有工作表的請求。 若要檢視特定工作表的要求，請關閉此選項。 當此選項關閉時，您必須按一下 Excel 報表底部的「工作表」索引標籤，才能在「<span class="wintitle">請求管理員</span>」中顯示與該工作表相關的請求。核取方塊旁的標籤會指出活頁簿中目前有哪些工作表具有焦點。 </p> </td> 
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
   <td colname="col1"> <p> 上次執行 </p> </td> 
   <td colname="col2"> <p>指定報告建立工具上次處理請求的日期。 在適當的情況下，另有診斷訊息會出現在此表格的<span class="wintitle">「上一次執行」</span>欄中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>新增 </p> </td> 
   <td colname="col2"> <p>顯示「請求精靈」對話方塊。 請參閱<a href="/help/analyze/report-builder/data-requests/t-create-a-data-request.md"   >建立資料請求</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>編輯 </p> </td> 
   <td colname="col2"> <p> （或編輯多個）編輯選取的請求。 系統會顯示<span class="wintitle">「請求精靈」</span>對話方塊。請參閱<a href="/help/analyze/report-builder/manage-requests/t-edit-multiple-requests.md"   >編輯多項請求</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>刪除 </p> </td> 
   <td colname="col2"> <p>刪除請求。 您可以刪除多個選取的請求。 您也可以選取請求並按鍵盤上的刪除，以刪除清單中的請求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 選擇全部 </p> </td> 
   <td colname="col2"> <p>選擇所有請求。 <span class="wintitle">「請求管理員」</span>會在請求清單的底部顯示您選擇的請求數量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>從儲存格 </p> </td> 
   <td colname="col2"> <p>從工作表取得請求的資料。 如果請求與作用中工作表中目前選取的儲存格相關聯，則會選取清單中的相關請求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 重新整理 </p> </td> 
   <td colname="col2"> <p>重新整理單一請求或選擇的請求(See <a href="/help/analyze/report-builder/manage-requests/t-refresh-a-request.md"   > Refresh a Request</a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>刷新清單 </p> </td> 
   <td colname="col2"> <p>重新整理所有顯示的請求。 重新整理所有請求時，從伺服器將資訊更新至報表的時間會與報表中請求的複雜度成正比。 若是大型報表，重新整理所有請求可能需要幾分鐘的時間。 有鑑於此，您可以先個別更新最迫切的請求，然後等到其他較閒逸的時間再選擇<span class="wintitle">重新整理所有請求</span>。 </p> <p> <p>附註：在重新整理含有多個請求的工作表時，我們建議您經常到<span class="wintitle">「請求管理員」</span>檢查結果。如果發生請求失敗，診斷欄中的錯誤訊息會協助您找出錯誤的來源。 雖然在大多數情況下，當請求失敗時會顯示錯誤訊息，但請注意，偶爾不會產生錯誤訊息。 您可能會注意到，重新整理不會更新包含參考的儲存格中的資料，或是更新會從儲存格移除資料。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

