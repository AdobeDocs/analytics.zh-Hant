---
description: 了解在 Analysis Workspace 中如何處理專案。使用專案管理程式來管理 (建立、刪除、移動、共用、核准、固定、複製和標記) 專案。
keywords: Analysis Workspace
title: 專案概觀
feature: Workspace Basics
role: User, Admin
exl-id: 75c551de-297e-4c45-95e6-77472be6628a
source-git-commit: f02b660b551f5291443b8f7c5c51179a06b22eb9
workflow-type: tm+mt
source-wordcount: '1680'
ht-degree: 91%

---

# 專案概觀

Workspace 專案可讓您合併面板、視覺效果和元件，以進行分析並與貴組織的任何人共用。在開始第一個專案之前，請先了解如何存取、瀏覽及管理您的專案。

若要存取Adobe Analytics中的專案，請選取&#x200B;**[!UICONTROL Workspace]**。  **[!UICONTROL 專案]**&#x200B;管理員會列出您擁有的所有專案或與您共用的專案。具有專案清單的專案管理員也是Adobe Analytics的預設登陸頁面，除非您已在「偏好設定」中另行設定。

![專案登陸頁會顯示專案清單。](assets/projects.png)


## 標題區域

在標題區域 ➊ 內，您可以使用其他圖磚來建立專案、建立資料夾、編輯您的偏好設定，以及顯示或隱藏面板。

* 若要顯示或隱藏左側面板以便您在「**[!UICONTROL 專案]**」和「**[!UICONTROL 了解]**」之間選取，您可選取「![邊欄](/help/assets/icons/Rail.svg)」。
* 標題會顯示專案，還可選擇新增至您已選取資料夾的路徑。例如，[!UICONTROL 專案] > **[!UICONTROL 公司資料夾]**。您可以選取個別子資料夾部分，以直接前往特定資料夾。
* 若要顯示[**[!UICONTROL 空白專案]**](create-projects.md)、[**[!UICONTROL 空白行動計分卡]**](/help/analyze/mobile-app/create-scorecard.md)、**[!UICONTROL 開啟檔案]**&#x200B;和&#x200B;**[!UICONTROL 開啟發行說明]**，請選取![V形向下](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 顯示更多]**。 若要隱藏有圖磚的區域，請選取 ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 「顯示較少」]**。
* 根據您的選取來顯示 (使用[顯示選擇器](#show-selector))，您可以編輯偏好設定並對&#x200B;**[!UICONTROL 專案]**&#x200B;中目前可見到的資料夾執行動作：

  | 動作 | 說明 |
  |---|---|
  | **[!UICONTROL 建立專案]** | 選取以[建立新專案](create-projects.md)。 |
  | **[!UICONTROL 建立資料夾]** | 選取以[建立新專案](workspace-folders/create-folders.md)。 |
  | ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL 編輯偏好設定]** | [編輯偏好設定](/help/analyze/analysis-workspace/user-preferences.md)適用於您所有的專案。當階層連結導致空間有限時，此動作是「![更多](/help/assets/icons/More.svg)」子選單中的一部分。 |
  | **[!UICONTROL 新增專案]** | 選取以[新增專案](workspace-folders/add-projects.md)至目的資料夾。當階層連結導致空間有限時，此動作是「![更多](/help/assets/icons/More.svg)」子選單中的一部分。 |
  | **[!UICONTROL 重新命名資料夾]** | [重新命名](workspace-folders/manage-folders.md#rename-folders)目前資料夾。 |
  | **[!UICONTROL 移動資料夾]** | [移動](workspace-folders/manage-folders.md#move-folders)目前資料夾。 |
  | **[!UICONTROL 刪除資料夾]** | [刪除](workspace-folders/manage-folders.md#delete-folders)目前資料夾。 |




## 專案清單


專案清單 ➋ 會顯示您擁有以及已經與您共用的所有專案。清單有以下欄位：

| 欄 | 說明 |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | 當選取一個或多個專案時，專案介面底部會出現一個藍色操作欄。如需詳細資訊，請參閱「[動作](#actions)」。 |
| ![StarOutline](/help/assets/icons/StarOutline.svg) | 選取以將專案設為我的最愛 ![Star](/help/assets/icons/Star.svg) 或取消我的最愛 ![StarOutline](/help/assets/icons/StarOutline.svg)。 |
| **[!UICONTROL 標題和說明]** | 若要編輯專案，請選取標題連結，即會開啟 [Workspace 專案](/help/analyze/analysis-workspace/home.md)。與您共用的專案會以「![共用](/help/assets/icons/ShareAlt.svg)」來表示。選取 ![InfoOutline](/help/assets/icons/InfoOutline.svg) 以顯示快顯選單，其中含有專案的更多詳細資訊。選取「![更多](/help/assets/icons/More.svg)」以開啟含有動作的內容選單。如需詳細資訊，請參閱「[動作](#actions)」。 |
| **[!UICONTROL 類型]** | Workspace 專案、![FolderUser](/help/assets/icons/FolderUser.svg) 資料夾或[行動計分卡](/help/analyze/mobile-app/home.md)。 |
| **[!UICONTROL 標記]** | 套用至專案的標記。 |
| **[!UICONTROL 已排程]** | 是否為專案排程以透過電子郵件發送給收件者。選項包括 ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL 開啟]**&#x200B;或![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 關閉]**。請參閱「[發送專案資料給其他人](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md)」。 |
| **[!UICONTROL 共用連結 (任何人)]** | 無論是否與任何人共用專案，即使是沒有 Analysis Workspace 存取權的人都可以共用。選項包括 ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL 使用中]**&#x200B;或![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 非使用中]**。如需更多資訊，請參閱[共用專案](/help/analyze/analysis-workspace/curate-share/share-projects.md)中的「[與任何人共用專案 (無需登入)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required)」。 |
| **[!UICONTROL 專案角色]** | 您在專案中的角色。選項包括：編輯、複製、檢視。請參閱「[專案角色](/help/analyze/analysis-workspace/curate-share/curate.md)」，了解更多資訊。 |
| **[!UICONTROL 報告套裝]** | 與專案相關聯的報表套裝。 |
| **[!UICONTROL 所有者]** | 建立此專案的人 (您或與您共用專案的人)。 |
| **[!UICONTROL 共用對象]** | 已與其共用該專案的使用者。 |
| **[!UICONTROL 上次修改日期]** | 上次修改專案的日期和時間。 |
| **[!UICONTROL 上次開啟]** | 上次開啟專案的日期和時間。 |
| **[!UICONTROL 元件 ID]** | 元件的ID。 |
| **[!UICONTROL 最大日期範圍]** | 專案中任何面板或視覺效果的最長日期範圍。 |
| **[!UICONTROL 查詢數]** | 專案中使用的查詢總數。 |
| **[!UICONTROL 位置]** | 專案所在的資料夾。 |

將滑鼠停留在任何資料欄標題上，即可顯示 ![ChevronDown](/help/assets/icons/ChevronDown.svg) 並從內容選單中選取：

* **[!UICONTROL 升序排列]**
* **[!UICONTROL 降序排序]**
* **[!UICONTROL 調整資料欄大小]**&#x200B;會出現一條藍線，可幫助您調整資料欄的大小。

### 動作

您可以使用內容選單 ![更多的](/help/assets/icons/More.svg) 或藍色動作列，對一個或多個專案執行動作。

| 圖示 | 動作 | 說明 |
|:---:| ---|---|
| ![CrossSize75](/help/assets/icons/Close.svg) | **[!UICONTROL *x *已選取]** | 取消選擇您已選的專案和資料夾，並刪除藍色動作列。 |
| ![Delete](/help/assets/icons/Delete.svg) | **[!UICONTROL 刪除]** | 刪除一個或多個專案或資料夾。系統會提示您進行確認。 <p>您刪除的專案：</p><ul><li>無法恢復</li><li>已從專案清單中移除</li><li>無法再透過其 URL 進行存取</li><li>不再包含於已排程傳遞中 (如果先前曾設定已排程傳遞的話)<br/>關於已排程傳遞的資訊，請參閱[已排程的專案](/help/components/scheduled-projects-manager.md)。  </p> |
| ![Share](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL 共用]** | 共用專案。請參閱「[共用專案](/help/analyze/analysis-workspace/curate-share/share-projects.md)」了解更多。 |
| ![Edit](/help/assets/icons/Edit.svg) | **[!UICONTROL 重新命名]** | 重新命名專案。開啟&#x200B;**[!UICONTROL 重新命名：*專案名稱對話框&#x200B;*]**。輸入新名稱並選取「**[!UICONTROL 儲存&#x200B;]**」。 |
| ![Copy](/help/assets/icons/Copy.svg) | **[!UICONTROL 複製]** | 複製一個或多個專案。專案會獲得相同的名稱和字尾 `(Copy)`。 |
| ![PinOnff](/help/assets/icons/PinOff.svg) | **[!UICONTROL 釘選]**&#x200B;或&#x200B;**[!UICONTROL 取消釘選]** | 釘選或取消釘選一個或多個專案或資料夾。已釘選的專案和資料夾會出現在清單上方，並忽略您指定的排序順序。 |
| ![ArrowUp](/help/assets/icons/ArrowUp.svg) | **[!UICONTROL 向上移動]** | 在專案清單中，將已釘選的專案或資料夾向上移動。 |
| ![ArrowDown](/help/assets/icons/ArrowDown.svg) | **[!UICONTROL 向下移動]** | 在專案清單中，將已釘選的專案或資料夾向下移動。 |
| ![Label](/help/assets/icons/Label.svg) | **[!UICONTROL 標記]** | 標記一個或多個專案或資料夾。**[!UICONTROL 標記元件]**&#x200B;對話框會顯示，即可選取一個或多個標記。選取「**[!UICONTROL 儲存]**」，以儲存所選專案或資料夾的標記。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL 核准]**&#x200B;或&#x200B;**[!UICONTROL 取消核准]** | 核准或不核准專案。只有管&#x200B;&#x200B;理員可以核准專案。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL 匯出 CSV]** | 將選取的專案匯出為名為 `Project List.csv` 的 CSV 檔案。 |
| ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) | **[!UICONTROL 新增專案]** | 將一個或多個專案新增至選取的資料夾。在「**[!UICONTROL 新增專案]**」中，您可以選取一個或多個專案。選取「**[!UICONTROL 新增]**」，將專案新增至資料夾。請參閱「[將項目新增至資料夾](workspace-folders/add-projects.md#from-inside-a-folder)」了解更多。 |
| ![FolderAddTo](/help/assets/icons/FolderAddTo.svg) | **[!UICONTROL 移動至]** | 將一個或多個選取的專案移動至資料夾。在「**[!UICONTROL 選取資料夾]**」中，選取要將選取的專案移往的資料夾，然後選取「**[!UICONTROL 移動]**」。請參閱「[將項目新增至資料夾](workspace-folders/add-projects.md#from-the-project-list)」了解更多。 |



## 顯示選擇器

您可以使用&#x200B;**[!UICONTROL 「顯示」]**&#x200B;選擇器 ➌ 來切換專案介面的外觀。**[!UICONTROL 顯示]**&#x200B;選擇器會定義[標題區域](#title-area)中可用的選項，以及[專案清單](#project-list)中顯示的資料欄。

* 若要變更[標題區域](#title-area)中可用的選項，請選取&#x200B;**[!UICONTROL 顯示]** **[!UICONTROL 所有專案]**&#x200B;或&#x200B;**[!UICONTROL 顯示]** **[!UICONTROL 資料夾和專案]**。

* 若要定義在[專案清單](#project-list)中顯示哪些資料欄，請選取![ColumnSetting](/help/assets/icons/ColumnSetting.svg)，然後從「**[!UICONTROL 自訂表格]**」對話框選取或取消選取資料欄。選取「**[!UICONTROL 套用]**」以套用自訂。若要了解資料欄的更多資訊，請參閱「[專案清單](#project-list)」。

## 篩選面板

您可以使用篩選器面板 ➍ 來篩選「[專案清單](#project-list)」中的篩選器和資料夾。若要顯示或隱藏篩選器面板，請使用「![篩選器](/help/assets/icons/Filter.svg)」。

篩選器面板由以下部分組成。

### 標記

| 標記 | 說明 |
|---|---|
| ![標記](assets/projects-filters-tags.png){width="300"} | 「**[!UICONTROL 標記]**」部分可讓您按標記進行篩選。 <ul><li>您可以使用 ![搜尋](/help/assets/icons/Search.svg) *「搜尋標記」*&#x200B;來搜尋您想要用來篩選的標記。</li><li>您可以選取多個標記。適用標記取決於篩在篩選器面板其他部分所做的選擇。</li><li>這些數字是表示：<ul><li>**2︎⃣**：目前篩選器產生的專案適用的標記數量。</li><li>7︎⃣：與特定標記相關聯的專案數量。</li></ul></li></ul> |


### 報表套裝

| 報表套裝 | 說明 |
|---|---|
| ![報告套裝](assets/projects-filters-reportsuites.png){width="300"} | **[!UICONTROL 報表套裝]**&#x200B;區段可讓您篩選報表套裝。 <ul><li>您使用![搜尋](/help/assets/icons/Search.svg) *搜尋報表套裝*&#x200B;來搜尋您要用來篩選的報表套裝。</li><li>您可以選取多個報表套裝。 可用的報表套裝取決於篩選器面板中其他區段所做的選擇。</li><li>這些數字是表示：<ul><li>**3︎⃣**：目前篩選產生的專案可用的報表套裝數目。</li><li>⃣4︎：與特定報表套裝相關聯的專案數目。</li></ul></li></ul> |


### 所有者

| 所有者 | 說明 |
|---|---|
| ![所有者](assets/projects-filters-owners.png){width="300"} | 「**[!UICONTROL 所有者]**」部分可讓您篩選所有者。 <ul><li>您可使用 ![搜尋](/help/assets/icons/Search.svg) *「搜尋所有者」*&#x200B;來搜尋您想要用來篩選的所有者。</li><li>您可以選取多個所有者。適用的所有者取決於在篩選器面板其他部分所做的選擇。</li><li>這些數字是表示：<ul><li>**3︎⃣**：目前篩選器產生的專案適用的所有者數量。</li><li>4︎⃣：與特定所有者相關聯的專案數量。</li></ul></li></ul> |


### 類型

| 類型 | 說明 |
|---|---|
| ![Type](assets/projects-filters-type.png){width="300"} | **[!UICONTROL 類型]**&#x200B;部分可讓您依照專案或資料夾的類型進行篩選。<ul><li>您可以選取下列其中一個或更多選項:<ul><li> **[!UICONTROL 資料夾]**。</li><li>**[!UICONTROL Analysis Workspace 專案]**</li><li>**[!UICONTROL Mobile 計分卡]**</li></ul> <li>您可以選取多個其他篩選器。適用的其他篩選器取決於在篩選器面板其他部分所做的選擇。</li><li>這些數字是表示：<ul><li>**5︎⃣**：目前篩選器產生的專案適用的其他篩選器數量。</li><li>4︎⃣：與特定其他篩選器相關聯的專案數量。</li></ul></li></ul> |


### 其他篩選器

| 其他篩選器 | 說明 |
|---|---|
| ![其他篩選器](assets/projects-filters-others.png){width="300"} |  **[!UICONTROL 其他篩選器]**&#x200B;部分可讓您根據其他預先定義的篩選器進行篩選。<ul><li>您可以選取下列其中一個或更多選項:<ul><li> **[!UICONTROL 全部顯示]**</li><li>**[!UICONTROL 與我共用]**</li><li>**[!UICONTROL 我的]**</li><li>**[!UICONTROL 已核准]**</li><li>**[!UICONTROL 我的最愛]**</li></ul> 您可以選取的內容取決於您的角色和權限。</li><li>您可以選取多個其他篩選器。適用的其他篩選器取決於在篩選器面板其他部分所做的選擇。</li><li>這些數字是表示：<ul><li>**5︎⃣**：目前篩選器產生的專案適用的其他篩選器數量。</li><li>4︎⃣：與特定其他篩選器相關聯的專案數量。</li></ul></li></ul> |

## 搜尋

您可以使用搜尋區域 ➎ 並透過「![搜尋](/help/assets/icons/Search.svg)」欄位搜尋專案和資料夾。開始輸入後，[專案清單](#project-list)會自動篩選您的搜尋輸入。

搜尋區域也會顯示從篩選器面板套用的篩選器。

* 若要移除篩選器，請在篩選器中選取 ![CrossSize75](/help/assets/icons/CrossSize75.svg)。
* 若要刪除所有篩選器，請選取「全部清除」。

如果空間受限而無法顯示個別篩選器，您可以看到&#x200B;**[!UICONTROL 按篩選器 *x* 進行劃分]**。

* 若要移除篩選器：

   1. 使用上方的 **[!UICONTROL *x *篩選器]**![ChevronDown](/help/assets/icons/ChevronDown.svg) 來開啟內容選單，列出篩選器類型和個別篩選器。
   1. 使用 ![CrossSize75](/help/assets/icons/CrossSize75.svg) 來移除篩選器。

