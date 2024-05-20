---
description: 設定雲端匯入帳戶以及可上傳分類資料的位置
keywords: Analysis Workspace
title: 地點管理員
feature: Classifications
exl-id: ace70568-220a-44e8-8e5f-f73002b9e2a2
source-git-commit: 273fea86cde8880d9c9e03ac9c6a99b75f70f6cd
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 1%

---

# 地點管理員

「位置」管理員可讓您檢視、建立、編輯或刪除帳號與位置。 這些檔案可用於下列任一用途：

* 匯出檔案，使用 [資料摘要](/help/export/analytics-data-feed/create-feed.md)
* 匯出報告，使用 [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* 使用匯入結構描述 [分類設定](/help/components/classifications/sets/overview.md)

## 檢視、篩選和搜尋位置

「位置管理員」可讓您檢視您建立的任何位置。 系統管理員可以檢視所有使用者建立的位置。

1. 若要存取Adobe Analytics中的位置管理器，請選取「 」 **[!UICONTROL 元件]** > **[!UICONTROL 位置]**.

1. （視條件而定）如果您是系統管理員，則可以啟用 [!UICONTROL **檢視所有使用者的位置**] 用來檢視組織中所有使用者建立的位置的選項。 <!-- Maybe add a screenshot? This is new functionality -->

1. 篩選或搜尋位置清單：

   * **篩選：** 選取「篩選」圖示以篩選位置清單。

     您可以依以下方式篩選位置： **[!UICONTROL 位置型別]**， **[!UICONTROL 帳戶]**，或 **[!UICONTROL 建立者]**.

     ![位置篩選器](assets/locations-filters.png)

   * **搜尋：** 在搜尋欄位中，開始輸入您要檢視的位置名稱。 輸入時會篩選結果。 系統會搜尋下列各欄： **位置名稱**， **位置型別**， **帳戶**、和 **建立者**.

1. （選擇性）如果您有超過1,000個位置，只會顯示前1,000個。 選取 [!UICONTROL **載入更多**] 以載入其他1,000個位置。

## 在位置管理員中設定欄

「位置」管理員中有以下欄。 若要自訂表格中顯示的欄，請選取 **自訂表格** 圖示 ![自訂表格圖示](assets/customize-table-icon.png).

* **[!UICONTROL 位置名稱]**：位置名稱。 選取位置名稱旁的3點選單，以 [編輯位置](/help/components/locations/configure-import-locations.md) 或刪除它。
* **[!UICONTROL 位置型別]**：與位置相關聯的帳戶型別。
* **[!UICONTROL 帳戶]**：與位置相關聯的特定帳戶。
* **應用**：位置可搭配使用的應用程式型別(例如資料摘要、Data Warehouse或分類設定)。
* **[!UICONTROL 上次使用日期]**：上次使用位置的日期。
* **[!UICONTROL 建立者]**：建立位置的使用者。
* **[!UICONTROL 建立日期]**：建立位置的日期。

## 建立和管理位置

您可以建立、編輯和刪除位置。

### 建立位置

如需有關如何建立位置的資訊，請參閱 [設定雲端匯入和匯出位置](/help/components/locations/configure-import-locations.md).

<!-- Do I need to add some steps here about how to create a location and then assign that location to be used with DF, DW, or Classifications sets? Need to hear back from Ron and team whether we are including this functionality -->

### 編輯位置

如需有關如何編輯位置的資訊，請參閱 [設定雲端匯入和匯出位置](/help/components/locations/configure-import-locations.md).

### 刪除位置

>[!IMPORTANT]
>
>如果刪除位置，任何與已刪除位置關聯的資料摘要檔案、Data Warehouse報表或分類設定結構描述將在下次使用時失敗。
>
>如果您刪除位置，您應： [編輯您的資料摘要](/help/export/analytics-data-feed/create-feed.md)， [Data Warehouse報表](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)、和 [分類集結構描述](/help/components/classifications/sets/manage/schema.md) 以使用功能位置。

若要在Adobe Analytics的「位置」管理員中刪除位置：

1. 選取 **[!UICONTROL 元件]** > **[!UICONTROL 位置]**，然後選取 [!UICONTROL **位置**] 標籤。

1. 選取「 」中的3點選單 [!UICONTROL **位置名稱**] 要刪除的位置欄。

1. 選取「[!UICONTROL **刪除**]」。

## 編輯帳戶

1. 若要在Adobe Analytics的「位置」管理員中編輯帳戶，請選取「 」 **[!UICONTROL 元件]** > **[!UICONTROL 位置]**，然後選取 [!UICONTROL **位置帳戶**] 標籤。

1. （視條件而定）如果您是系統管理員，則可以啟用 [!UICONTROL **檢視所有使用者的帳戶**] 用來檢視組織中所有使用者建立的位置的選項。 <!-- Maybe add a screenshot? This is new functionality -->


1. 選取 [!UICONTROL **檢視詳細資料**] 在您想要編輯的帳戶上。

1. 進行任何需要的變更，然後選取「 」 [!UICONTROL **儲存**].

## 檢視帳戶金鑰

建立帳戶之後，您可以檢視該帳戶的任何關聯帳戶金鑰。 如果您在設定帳戶時尚未與雲端提供者完成設定，您可能需要檢視此資訊 [原本設定的帳戶](/help/components/locations/configure-import-accounts.md).

若要檢視與匯出帳戶相關聯的金鑰，請執行下列動作：

1. 在Adobe Analytics中，選取 **[!UICONTROL 元件]** > **[!UICONTROL 位置]**，然後選取 [!UICONTROL **位置帳戶**] 標籤。

1. 在您要編輯的帳戶上選取3點圖示，然後選取「 」 [!UICONTROL **帳戶金鑰**].

## 刪除帳戶

1. 在Adobe Analytics中，選取 **[!UICONTROL 元件]** > **[!UICONTROL 位置]**，然後選取 [!UICONTROL **位置帳戶**] 標籤。

1. 在您要編輯的帳戶上選取3點圖示，然後選取「 」 [!UICONTROL **刪除帳戶**]
