---
title: 管理「分類設定」合併
description: 瞭解如何將一個或多個分類設定合併為單一分類設定。
exl-id: 0be97ca4-56c3-4642-9347-924812e88e8c
feature: Classifications
source-git-commit: cfa8335008548254786e46dfe634229edad5bd54
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 3%

---

# 管理分類合併

如果您有多個包含類似分類資料的分類集，您可以將它們合併成單一分類集。 合併兩個或多個分類集時，Adobe會產生新的分類集，其中包含來自每個個別分類集的所有分類資料。 當您將資料上傳到許多報表套裝時，合併會很有用。 或者，當您有包含相同分類資料的維度，且想要將其合併為單一工作流程時。

您必須擁有Adobe Analytics的產品管理員存取權，才能檢視分類集合併管理員。



若要管理分類合併：

1. 從Adobe Analytics頂端功能表列選取&#x200B;**[!UICONTROL 元件]**，然後選取&#x200B;**[!UICONTROL 分類設定]**。
1. 在&#x200B;**[!UICONTROL 分類設定]**&#x200B;中，選取&#x200B;**[!UICONTROL 合併]**&#x200B;索引標籤。


## 分類整合管理員

**[!UICONTROL 分類設定 — 合併]**&#x200B;管理員有下列介面元素：

![分類集 — 合併管理員](assets/classifications-sets-consolidations.png)



### 分類彙總清單

清單➊顯示已建立並驗證且可能合併的分類合併。 清單有以下欄位：

| 欄 | 說明 |
|---|---|
| **[!UICONTROL 合併名稱]** | 分類集合併的名稱。 |
| **[!UICONTROL 目前的工作]** | 與分類集合併相關聯的工作。 |
| **[!UICONTROL 狀態]** | 分類集合併的狀態。 可能的值包括： **[!UICONTROL 已建立]**、**[!UICONTROL 已取消]**、**[!UICONTROL 正在取消]**、**[!UICONTROL 正在驗證]**、**[!UICONTROL 已失敗的驗證]**、**[!UICONTROL 已驗證]**、**[!UICONTROL 比較]**、**[!UICONTROL 比較失敗]**、**[!UICONTROL 合併]**、**[!UICONTROL 已提交]**、**[!UICONTROL 合併]**、**[!UICONTROL 合併失敗]**、**[!UICONTROL 合併失敗已成功]**、**[!UICONTROL 正在等待審批]**、**[!UICONTROL 正在完成]**、**[!UICONTROL 失敗]**&#x200B;或&#x200B;**[!UICONTROL 已完成]**。 |
| **[!UICONTROL 建立時間]** | 分類集合併的建立時間。 |
| **[!UICONTROL 完成時間]** | 分類合併的完成時間。 |


若要調整分類合併清單中欄的大小，您可以：

* 暫留在欄分隔符號上，並將欄分隔符號拖曳到所需的欄寬。
* 選取![V形向下](/help/assets/icons/ChevronDown.svg)並選取&#x200B;**[!UICONTROL 調整資料行大小]**。 帶有調整大小按鈕的垂直線允許您使用將欄大小調整到所需的大小。

排序分類合併清單中的欄

* 選取![V形向下](/help/assets/icons/ChevronDown.svg)並選取&#x200B;**[!UICONTROL 遞增排序]**&#x200B;或&#x200B;**[!UICONTROL 遞減排序]**。 箭頭(↑↓)表示哪一欄以及該欄的排序方式。

### 搜尋和按鈕

在分類彙總清單頂端的區域➋中，您可以：

* 搜尋![搜尋](/help/assets/icons/Search.svg)以取得分類合併。 結果會顯示在分類彙總清單中。 選取![CrossSize200](/help/assets/icons/CrossSize200.svg)以清除搜尋。
* 移除套用至分類集合併清單的任何篩選器。 選取![CrossSize100](/help/assets/icons/CrossSize100.svg)以移除篩選器。
* 建立新的分類集合併。 選取![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL New]**&#x200B;以開啟[分類集合併]對話方塊，並定義新的分類集合併。
* 定義分類彙總清單的欄。 選取![ColumnSetting](/help/assets/icons/ColumnSetting.svg)，並在&#x200B;**[!UICONTROL 自訂表格]**&#x200B;對話方塊中選取要顯示在&#x200B;**[!UICONTROL 下方的欄，並選取要顯示的欄]**。 選取&#x200B;**[!UICONTROL 套用]**&#x200B;以套用資料行設定。


### 動作列

當您在「分類設定」清單中選取一或多個分類設定時，會顯示藍色動作列➌。 動作列中可提供下列動作：

| 圖示 | 動作 | 說明 |
|---|---|---|
| ![編輯](/help/assets/icons/Edit.svg) | **[!UICONTROL 編輯]** | [編輯分類集合併](process.md#edit-a-consolidation) |
| ![檢視詳細資料](/help/assets/icons/ViewDetail.svg) | **[!UICONTROL 檢視]** | 檢視分類集合併的詳細資訊。 根據狀態，您可以[核准](process.md#approve)或[取消](process.md#cancel)合併。 |


### 篩選面板

選取![篩選器](/help/assets/icons/Filter.svg)以顯示可讓您篩選分類合併清單的篩選器面板➍。 您可以篩選：

* **[!UICONTROL 狀態]**。 選取其中一個可能的值，以篩選狀態上的分類彙總清單。 |
* **[!UICONTROL 完成時間]**。 選取其中一個可能值，以在完成時篩選分類彙總清單。
* **[!UICONTROL 建立時間]**。 選取其中一個可能值，以在完成時篩選分類彙總清單。


選取![篩選器](/help/assets/icons/Filter.svg) **[!UICONTROL 隱藏篩選器]**&#x200B;以隱藏篩選器面板。

請注意，「篩選器」面板中顯示的篩選器會反映預先載入之分類合併的選項。
