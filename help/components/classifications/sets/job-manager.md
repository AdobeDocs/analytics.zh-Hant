---
title: 分類作業管理員
description: 瞭解如何檢視從分類設定產生的最新和已完成的分類作業。
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
feature: Classifications
source-git-commit: cfa8335008548254786e46dfe634229edad5bd54
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 2%

---

# 檢視分類工作並據以執行

分類作業管理員會顯示針對分類設定產生的最新和已完成的分類作業。 您也可以使用管理員來下載特定作業的分類資料或範本。

若要檢視分類工作並據以執行，請執行下列動作：


1. 從Adobe Analytics頂端功能表列選取&#x200B;**[!UICONTROL 元件]**，然後選取&#x200B;**[!UICONTROL 分類設定]**。
1. 在&#x200B;**[!UICONTROL 分類設定]**&#x200B;中，選取&#x200B;**[!UICONTROL 工作]**&#x200B;索引標籤。

## 分類工作管理員

**[!UICONTROL 分類設定 — 作業]**&#x200B;管理員有下列介面元素：

![分類集 — 工作管理員](manage/assets/classifications-sets-jobs.png)



### 分類工作清單

**[!UICONTROL 分類工作]**&#x200B;清單➊會顯示分類工作。 清單有以下欄位：

| 欄 | 說明 |
|---|---|
| **[!UICONTROL 工作識別碼]** | 分類工作的識別碼。 |
| **[!UICONTROL 分類設定]** | 與分類工作相關聯的分類設定。 |
| **[!UICONTROL 大小]** | 作為分類作業的一部分匯出或匯入的檔案大小。 |
| **[!UICONTROL 狀態]** | 分類工作的狀態。 可能的值包括： **[!UICONTROL 已建立]**、**[!UICONTROL 已排入佇列]**、**[!UICONTROL 已驗證]**、**[!UICONTROL 已失敗的驗證]**、**[!UICONTROL 正在處理]**、**[!UICONTROL 已完成處理]**、**[!UICONTROL 已失敗的處理]**、**[!UICONTROL 已完成]**&#x200B;或&#x200B;**[!UICONTROL 進度]**。 如果顯示，將滑鼠游標停留在警示![警示](/help/assets/icons/Alert.svg)上以顯示其他資訊。 |
| **[!UICONTROL 檔案名稱]** | 識別用來匯入或匯出檔案做為分類作業一部分的名稱或功能。 可能的值包括： <ul><li>*沒有值*</li><li>分類作業中處理的檔案名稱。</li><li>**[!UICONTROL SAINT匯出]**：作業是從[舊版分類介面](/help/components/classifications/importer/c-working-with-saint.md)匯出。</li><li>在&#x200B;**[!UICONTROL timestamp _匯出_分類集&#x200B;_的_]**&#x200B;匯出：作業是從[結構描述](manage/schema.md#download)介面下載。</li></ul> |
| **[!UICONTROL 工作型別]** | 分類工作的型別。 可能的值為： **[!UICONTROL 匯入]**&#x200B;或&#x200B;**[!UICONTROL 匯出]**。 |
| **[!UICONTROL 來源]** | 分類工作的來源。 可能的值為： **[!UICONTROL 網頁API]**、**[!UICONTROL 直接API上傳]**、**[!UICONTROL Adobe]**、**[!UICONTROL SAINT]**&#x200B;或&#x200B;**[!UICONTROL 未知]**。 |
| **[!UICONTROL 修改行]** | 分類作業修改的修改行數。 |
| **[!UICONTROL 總行]** | 分類工作已處理的行總數。 |
| **[!UICONTROL 完成時間]** | 分類工作的完成時間。 |
| **[!UICONTROL 檔案下載]** | 使用![下載](/help/assets/icons/Download.svg)來下載與分類工作相關聯的檔案（範本或資料）。 |

若要調整分類工作清單中欄的大小，您可以：

* 暫留在欄分隔符號上，並將欄分隔符號拖曳到所需的欄寬。
* 選取![V形向下](/help/assets/icons/ChevronDown.svg)並選取&#x200B;**[!UICONTROL 調整資料行大小]**。 帶有調整大小按鈕的垂直線允許您使用將欄大小調整到所需的大小。

排序分類工作清單中的欄

* 選取![V形向下](/help/assets/icons/ChevronDown.svg)並選取&#x200B;**[!UICONTROL 遞增排序]**&#x200B;或&#x200B;**[!UICONTROL 遞減排序]**。 箭頭(↑↓)表示哪一欄以及該欄的排序方式。


### 搜尋和按鈕

在分類工作清單頂端的區域➋中，您可以：

* 搜尋![搜尋](/help/assets/icons/Search.svg)以尋找分類工作。 結果會顯示在分類作業清單中。 選取![CrossSize200](/help/assets/icons/CrossSize200.svg)以清除搜尋。
* 移除套用至分類作業清單的任何篩選器。 選取![CrossSize100](/help/assets/icons/CrossSize100.svg)以移除篩選器。
* 選取![MoreCircle](/help/assets/icons/MoreCircle.svg)以載入額外的1000個分類工作。 最初，分類設定清單會顯示最多1000個分類工作。
* 定義分類集作業清單的欄。 選取![ColumnSetting](/help/assets/icons/ColumnSetting.svg)，並在&#x200B;**[!UICONTROL 自訂表格]**&#x200B;對話方塊中選取要顯示在&#x200B;**[!UICONTROL 下方的欄，並選取要顯示的欄]**。 選取&#x200B;**[!UICONTROL 套用]**&#x200B;以套用資料行設定。



### 篩選面板

選取![篩選器](/help/assets/icons/Filter.svg)以顯示可讓您篩選分類工作清單的篩選器面板➌。 您可以篩選：

* **[!UICONTROL 分類設定]**。 選取一或多個分類集以篩選分類作業清單。
* **[!UICONTROL 完成時間]**。 選取其中一個可能值，以在完成時間篩選分類作業清單。
* **[!UICONTROL 狀態]**。 選取其中一個可能值，以篩選狀態上的分類作業清單。
* **[!UICONTROL 工作型別]**。 選取其中一個可能值，以篩選工作型別上的分類工作清單。
* **[!UICONTROL Source]**。 選取其中一個可能值，以篩選來源上的分類作業清單。


選取![篩選器](/help/assets/icons/Filter.svg) **[!UICONTROL 隱藏篩選器]**&#x200B;以隱藏篩選器面板。

請注意，「篩選器」面板中顯示的篩選器會反映預先載入之分類作業的選項。
