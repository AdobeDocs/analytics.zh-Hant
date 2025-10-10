---
description: 設定雲端匯入帳戶以及可上傳分類資料的位置
keywords: Analysis Workspace
title: 地點管理員
feature: Classifications
exl-id: ace70568-220a-44e8-8e5f-f73002b9e2a2
source-git-commit: 5c02b46a7757e07a23505dc8e3dc21b6353aa9e2
workflow-type: tm+mt
source-wordcount: '1490'
ht-degree: 1%

---

# 地點管理員

「位置」管理員可讓您檢視、建立、編輯或刪除帳號與位置。 這些檔案可用於下列任一用途：

* 使用[資料摘要](/help/export/analytics-data-feed/create-feed.md)匯出檔案
* 使用[Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)匯出報告
* 使用[Report Builder](/help/analyze/report-builder/report-builder-export.md)時匯出檔案
* 使用[分類集](/help/components/classifications/sets/overview.md)匯入結構描述

## 檢視、篩選和搜尋位置

「位置管理員」可讓您檢視您建立的任何位置或與組織共用的任何位置。 系統管理員可以檢視所有使用者建立的位置，無論這些使用者是否共用。

1. 若要存取Adobe Analytics中的位置管理員，請選取&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 位置]**。

1. （視條件而定）如果您是系統管理員，可以啟用&#x200B;[!UICONTROL **檢視所有使用者的位置**]&#x200B;選項，以檢視組織中的所有使用者建立的位置。<!-- Maybe add a screenshot? This is new functionality -->

1. 篩選或搜尋位置清單：

   * **篩選器：**&#x200B;選取「篩選器」圖示以篩選位置清單。

     您可以依&#x200B;**[!UICONTROL 位置型別]**、**[!UICONTROL 帳戶]**&#x200B;或由&#x200B;**[!UICONTROL 建立的]**&#x200B;來篩選位置。

     ![位置篩選器](assets/locations-filters.png)

   * **搜尋：**&#x200B;在搜尋欄位中，開始輸入您要檢視的位置名稱。 輸入時會篩選結果。 搜尋下列資料行： **位置名稱**、**位置型別**、**帳戶**&#x200B;以及&#x200B;**建立者**。

1. （選擇性）如果您有超過1,000個位置，只會顯示前1,000個。 選取&#x200B;[!UICONTROL **載入更多**]&#x200B;以載入其他1,000個位置。

## 在位置管理員中設定欄

「位置」管理員中有以下欄。 若要自訂表格中顯示的欄，請選取&#x200B;**自訂表格**&#x200B;圖示![自訂表格圖示](assets/customize-table-icon.png)。

* **[!UICONTROL 位置名稱]**：位置名稱。 選取位置名稱旁的3點功能表，以[編輯位置](/help/components/locations/configure-import-locations.md)或將其刪除。
* **[!UICONTROL 位置型別]**：與位置關聯的帳戶型別。
* **[!UICONTROL 帳戶]**：與位置關聯的特定帳戶。
* **應用程式**：位置可以搭配使用的應用程式型別(例如資料摘要、Data Warehouse或分類設定)。
* **[!UICONTROL 上次使用]**：上次使用位置的日期。
* **[!UICONTROL 建立者]**：建立位置的使用者。
* **[!UICONTROL 建立日期]**：建立位置的日期。

## 建立和管理位置

您可以建立、編輯和刪除位置。

### 建立位置

如需有關如何建立位置的資訊，請參閱[設定雲端匯入和匯出位置](/help/components/locations/configure-import-locations.md)。

<!-- Do I need to add some steps here about how to create a location and then assign that location to be used with DF, DW, or Classifications sets? Need to hear back from Ron and team whether we are including this functionality -->

### 編輯位置

位置只能由建立該位置的使用者或系統管理員編輯。

如需有關如何編輯位置的資訊，請參閱[設定雲端匯入和匯出位置](/help/components/locations/configure-import-locations.md)。

### 刪除位置

>[!IMPORTANT]
>
>如果刪除位置，任何與已刪除位置關聯的資料摘要檔案、Data Warehouse報表或分類設定結構描述將在下次使用時失敗。
>
>如果您刪除位置，您應該[編輯您的資料摘要](/help/export/analytics-data-feed/create-feed.md)、[Data Warehouse報告](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)和[分類設定結構描述](/help/components/classifications/sets/manage/schema.md)，以使用正常的位置。

位置只能由建立該位置的使用者或系統管理員刪除。

若要在Adobe Analytics的「位置」管理員中刪除位置：

1. 選取&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 位置]**，然後選取&#x200B;[!UICONTROL **位置**]&#x200B;索引標籤。

1. 選取您要刪除之位置的&#x200B;[!UICONTROL **位置名稱**]&#x200B;欄中的3點功能表。

1. 選取「[!UICONTROL **刪除**]」。

## 建立和管理帳戶

您可以建立、編輯和刪除帳戶。

### 建立帳戶

如需有關如何建立帳戶的資訊，請參閱[設定雲端匯入和匯出帳戶](/help/components/locations/configure-import-accounts.md)。

### 編輯帳戶

只有建立帳號的使用者或系統管理員才能編輯帳號。

如需有關如何編輯帳戶的資訊，請參閱[設定雲端匯入和匯出帳戶](/help/components/locations/configure-import-accounts.md)。

### 檢視帳戶金鑰

建立帳戶之後，您可以檢視該帳戶的任何關聯帳戶金鑰。 如果您在您[最初設定帳戶](/help/components/locations/configure-import-accounts.md)時，尚未與雲端提供者完成帳戶的設定，您可能需要檢視此資訊。

若要檢視與匯出帳戶相關聯的金鑰，請執行下列動作：

1. 在Adobe Analytics中，選取&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 位置]**，然後選取&#x200B;[!UICONTROL **位置帳戶**]&#x200B;索引標籤。

1. （視條件而定）如果您是系統管理員，可以啟用&#x200B;[!UICONTROL **檢視所有使用者的位置**]&#x200B;選項，以檢視組織中的所有使用者建立的位置。<!-- Maybe add a screenshot? This is new functionality -->

1. 在您要編輯的帳戶上選取3點圖示，然後選取&#x200B;[!UICONTROL **帳戶金鑰**]。

### 刪除帳戶

>[!IMPORTANT]
>
>如果沒有位置使用帳號，才能刪除帳號。 刪除帳戶之前，必須先刪除帳戶上的任何位置，如[刪除位置](#delete-a-location)中所述。

只有建立帳號的使用者或系統管理員才能刪除帳號。

若要刪除帳戶，請執行下列動作：

1. 在Adobe Analytics中，選取&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 位置]**，然後選取&#x200B;[!UICONTROL **位置帳戶**]&#x200B;索引標籤。

1. （視條件而定）如果您是系統管理員，可以啟用&#x200B;[!UICONTROL **檢視所有使用者的帳戶**]&#x200B;選項，以檢視貴組織中所有使用者建立的位置。

1. 在您要編輯的帳戶上選取3點圖示，然後選取&#x200B;[!UICONTROL **刪除帳戶**]

## 設定全公司設定（僅限管理員）

系統管理員可以限制使用者建立帳戶和位置，也可以限制使用者可以建立和使用的帳戶型別。

![管理員設定標籤](assets/locations-admin-settings.png)

### 設定使用者是否可以建立和編輯帳戶

依預設，組織中的所有使用者都可以建立帳戶，並編輯他們在Adobe Analytics環境中建立的帳戶，如[設定雲端匯入和匯出帳戶](/help/components/locations/configure-import-accounts.md)中所述。

您可以限制使用者建立帳戶。 當您這樣做時，使用者仍然可以使用他們已建立的任何帳戶，但他們無法再編輯這些帳戶。 您可以刪除使用者已建立的帳戶，如[刪除帳戶](#delete-an-account)中所述。

若要限制所有使用者建立和編輯帳戶：

1. 在Adobe Analytics中，選取&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 位置]**，然後選取&#x200B;[!UICONTROL **管理員設定**]&#x200B;索引標籤。

1. 在&#x200B;[!UICONTROL **位置帳戶**]&#x200B;區段中，取消選取&#x200B;[!UICONTROL **允許使用者建立和管理位置帳戶**]&#x200B;選項。

1. 選取「[!UICONTROL **儲存**]」。

1. （選擇性）刪除使用者已建立而您不再想要他們使用的任何帳戶，如[刪除帳戶](#delete-an-account)中所述。

### 設定使用者是否可以建立和編輯位置

根據預設，組織中的所有使用者都可以在Adobe Analytics環境中建立位置並編輯他們建立的位置，如[設定雲端匯入和匯出位置](/help/components/locations/configure-import-locations.md)中所述。

您可以限制使用者建立位置。 當您這樣做，使用者仍然可以使用他們已建立的任何位置，但他們無法再編輯這些位置。 您可以刪除使用者已建立的位置，如[刪除位置](#delete-a-location)中所述。

若要限制所有使用者建立和編輯位置：

1. 在Adobe Analytics中，選取&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 位置]**，然後選取&#x200B;[!UICONTROL **管理員設定**]&#x200B;索引標籤。

1. 在&#x200B;[!UICONTROL **位置**]&#x200B;區段中，取消選取&#x200B;[!UICONTROL **允許使用者建立和管理位置**]&#x200B;選項。

1. 選取「[!UICONTROL **儲存**]」。

1. （選擇性）刪除使用者已建立而您不再希望他們使用的任何位置，如[刪除位置](#delete-a-location)中所述。

### 限制使用者可以建立和使用的帳戶型別

您可以在下列情況下限制使用者看到的帳戶型別：

* 當[建立新帳戶](/help/components/locations/configure-import-accounts.md)時。

* 使用[資料摘要](/help/export/analytics-data-feed/create-feed.md)匯出檔案時、使用[Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)匯出報表時，或使用[分類集](/help/components/classifications/sets/overview.md)匯入結構描述時，選擇要使用哪些帳戶。

當您依照本節所述限制帳戶型別時，使用者將無法再看見您所限制型別的任何帳戶。 這表示無法建立該型別的新帳戶，且在建立資料摘要、Data Warehouse或「分類設定」時，無法使用該型別的現有帳戶。

但是，如果您想要限制使用為排程匯出設定的現有帳戶，則必須刪除這些帳戶。

#### 確保帳戶不會用於排程的匯出

當您限制帳戶型別時，會隱藏現有的帳戶，而不會將其刪除。

如果排程已設定為傳送資料至您所限制型別的帳戶，則排程仍會繼續執行，即使您限制帳戶型別後，資料也會繼續傳送至帳戶。  例如，如果資料摘要的排程是將資料傳送至您限制的帳戶型別，則排程將繼續執行。

如果您需要確保排程的匯出不會使用特定型別的帳戶，您可以在[限制帳戶型別](#limit-the-account-types-that-are-available-to-users)之前刪除帳戶。

若要刪除帳號：

1. 找出您計畫限制的帳戶型別帳戶，這些帳戶用於排程匯出。

1. 刪除帳戶，如[刪除帳戶](#delete-an-account)中所述。

1. 繼續下列章節，[限制使用者可用的帳戶型別](#limit-the-account-types-that-are-available-to-users)。

#### 限制使用者可用的帳戶型別

若要限制使用者建立和使用帳戶時可用的帳戶型別：

1. 在Adobe Analytics中，選取&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 位置]**，然後選取&#x200B;[!UICONTROL **管理員設定**]&#x200B;索引標籤。

1. 找到&#x200B;[!UICONTROL **允許的帳戶型別**]&#x200B;區段。

   使用者預設可使用下列帳戶型別。 取消選取您要限制使用者使用的任一帳戶型別。

   至少必須選取一種帳戶型別。

   * [!UICONTROL **Amazon S3 Role ARN**]

   * [!UICONTROL **Google Cloud Platform**]

   * [!UICONTROL **Azure SAS**]

   * [!UICONTROL **Azure RBAC**]

   * [!UICONTROL **電子郵件**]

   * 舊版帳戶型別，包括&#x200B;[!UICONTROL **Amazon S3**]、[!UICONTROL **Azure**]、[!UICONTROL **FTP**]&#x200B;和&#x200B;[!UICONTROL **SFTP**]

1. 選取「[!UICONTROL **儲存**]」。


