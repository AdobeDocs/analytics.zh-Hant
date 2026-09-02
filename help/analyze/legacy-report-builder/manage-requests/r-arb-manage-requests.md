---
description: 瞭解Report Builder中「管理請求」的欄位說明。
title: 如何在Report Builder中管理請求
uuid: 01b21d0e-c870-4df8-95b9-f4aef1f4d16b
feature: Report Builder
role: User, Admin
exl-id: fd8c0145-4c7e-4f07-aa63-656a8a20724c
TQID: https://experienceleague.adobe.com/ZAVAW4NN9WCHCdj-ZPXDOflV4oC0-WPbClzkdlrf3JM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 563
ht-degree: 26%

---

# 管理請求 - 定義

{{legacy-arb}}

檢視請求狀態的詳細資料，並使用欄位說明在Report Builder中管理請求。

## 概觀 {#section_75C288C945FA4781A4EDF806711A5660}

[!UICONTROL 請求管理員]提供您為所有工作表或僅一個作用中活頁簿建立的所有請求狀態的詳細檢視。 您也可以新增、編輯、重新整理和刪除請求。 當您以滑鼠右鍵按一下包含先前請求的Excel試算表中的可用儲存格時，這些函式通常會與[!UICONTROL 請求精靈]和[!UICONTROL 請求管理員]相關聯。

按一下Report Builder工具列中的&#x200B;**[!UICONTROL 管理]** ![](assets/edit_request.gif)，會顯示[!UICONTROL 請求管理員]。

>[!NOTE]
>
>Adobe Report Builder只會在同一個工作表中執行請求相依性，不會跨工作表執行。 將相依性限制在單一工作表中，可確保執行的時效性。

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
   <td colname="col2"> <p>顯示使用中活頁簿中所有工作表的請求。 若要檢視特定工作表的請求，請關閉此選項。 當此選項關閉時，您必須按一下 Excel 報表底部的「工作表」索引標籤，才能在「<span class="wintitle">請求管理員</span>」中顯示與該工作表相關的請求。 核取方塊旁的標籤會指出目前焦點在活頁簿中的哪個工作表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>工作表 </p> </td> 
   <td colname="col2"> <p>顯示活頁簿中工作表的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>報告套裝 </p> </td> 
   <td colname="col2"> <p>顯示報表套裝的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日期範圍 </p> </td> 
   <td colname="col2"> <p>顯示報表的指定日期範圍。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>顆粒度 </p> </td> 
   <td colname="col2"> <p>指定要求的粒度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 上次執行 </p> </td> 
   <td colname="col2"> <p>指定Report Builder上次處理請求的日期。 在適當的情況下，另有診斷訊息會出現在此表格的<span class="wintitle">「上一次執行」</span>欄中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>新增 </p> </td> 
   <td colname="col2"> <p>顯示[請求精靈]對話方塊。 請參閱<a href="/help/analyze/legacy-report-builder/data-requests/t-create-a-data-request.md"   >建立資料要求</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>編輯 </p> </td> 
   <td colname="col2"> <p> （或編輯多個）編輯選取的請求。 系統會顯示<span class="wintitle">「請求精靈」</span>對話方塊。 請參閱<a href="/help/analyze/legacy-report-builder/manage-requests/t-edit-multiple-requests.md"   >編輯多項請求</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>刪除 </p> </td> 
   <td colname="col2"> <p>刪除請求。 您可以刪除多個選取的請求。 您也可以選取請求，然後按鍵盤上的「刪除」來刪除清單中的請求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 全選 </p> </td> 
   <td colname="col2"> <p>選取所有請求。 <span class="wintitle">「請求管理員」</span>會在請求清單的底部顯示您選擇的請求數量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>從儲存格 </p> </td> 
   <td colname="col2"> <p>從工作表取得請求的資料。 如果請求與作用中工作表中目前選取的儲存格相關聯，則會選取清單中的關聯請求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 重新整理 </p> </td> 
   <td colname="col2"> <p>重新整理單一請求或選擇的請求 （請參閱<a href="/help/analyze/legacy-report-builder/manage-requests/t-refresh-a-request.md"   >重新整理請求</a>。） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>重新整理清單 </p> </td> 
   <td colname="col2"> <p>重新整理所有顯示的請求。 當您重新整理所有請求時，從伺服器更新資訊至報表的時間會與報表中請求的複雜性成正比。 對於非常大的報表，重新整理所有請求可能需要幾分鐘的時間。 有鑑於此，您可以先個別更新最迫切的請求，然後等到其他較閒逸的時間再選擇<span class="wintitle">重新整理所有請求</span>。 </p> <p> <p>附註：在重新整理含有多個請求的工作表時，我們建議您經常到<span class="wintitle">「請求管理員」</span>檢查結果。 如果發生請求失敗，診斷欄中的錯誤訊息可協助您找出錯誤的來源。 雖然在大多數情況下，當請求失敗時會顯示錯誤訊息，但請注意，偶爾不會產生錯誤訊息。 您可能會注意到，重新整理不會更新包含參照的儲存格中的資料，或者更新會移除儲存格中的資料。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>
