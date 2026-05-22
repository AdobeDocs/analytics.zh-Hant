---
title: FTP 和 SFTP 伺服器的安全性需求
description: 了解 FTP 和 SFTP 伺服器的安全性需求。
feature: Data Configuration and Collection
role: Admin
source-git-commit: 94059a3b7d667fafe1900a4a9c82ed931d769df1
workflow-type: ht
source-wordcount: '1933'
ht-degree: 100%

---

# FTP 和 SFTP 伺服器的安全性需求

此頁面說明接收 Adobe Analytics 資料摘要或 Data Warehouse 所傳遞資料之既有 FTP 和 SFTP 伺服器的安全性需求。

* **既有的 FTP 伺服器**：必須升級使用 SFTP，如下方[升級 FTP 伺服器以使用 SFTP](#upgrade-ftp-servers-to-use-sftp) 區段所述。

  從 FTP 升級至 SFTP 為必要操作，因為 SFTP 可提升安全性。

  或者，如需更高級別的安全性，您可以轉變為現代化雲端目標。(如需詳細資訊，請參閱[設定雲端匯入及匯出帳戶](https://experienceleague.adobe.com/zh-hant/docs/analytics/components/locations/configure-import-accounts)。)

* **既有 SFTP 伺服器 (以及新升級的 SFTP 伺服器)**：必須輪換舊密碼，如下方[輪換您的 SFTP 密碼](#rotate-your-sftp-password)區段所述。

  定期輪換 SFTP 密碼是有助於保護資料的安全性最佳做法。

>[!IMPORTANT]
>
>完成本文中的步驟之前，請先考量下列情況。
>
>* **Adobe 建議盡可能轉變為現代化雲端目標，而非選擇升級至 SFTP。**
>FTP 和 SFTP 屬於舊版目標類型。Adobe 建議您改用現代化雲端目標類型 (例如 Amazon S3、Google Cloud Platform 或 Azure)，而非依照本文所述將 FTP 帳戶升級為 SFTP 以及輪換 SFTP 密碼。這些雲端目標能提供更高層級的安全性。如需詳細資訊，請參閱[設定雲端匯入及匯出帳戶](https://experienceleague.adobe.com/zh-hant/docs/analytics/components/locations/configure-import-accounts)。
>
>* **如果 FTP 和 SFTP 帳戶僅用於「分類」，請移轉至「分類設定」。**
>如果您的 FTP 或 SFTP 帳戶僅用於「分類」，您應該從「**分類匯入工具**」移轉至「**分類設定**」，而非依照本文所述將 FTP 帳戶升級為 SFTP 以及輪換 SFTP 密碼。分類匯入工具將棄用，於 **2026 年 8 月 31 日**&#x200B;後無法再存取。如需詳細資訊，請參閱[分類集概觀](https://experienceleague.adobe.com/zh-hant/docs/analytics/components/classifications/sets/overview)。

## 先決條件

### 盤點您的 FTP 帳戶

您必須針對與資料摘要或 Data Warehouse 搭配使用的每個 FTP 網站，完成本頁面上的 SFTP 升級步驟。

因此，您必須找出接收資料摘要或 Data Warehouse 資料的所有 FTP 帳戶。此資訊會顯示在您的 FTP 設定內，如文章[設定雲端匯入及匯出帳戶](/help/components/locations/configure-import-accounts.md)中的[舊帳戶類型](/help/components/locations/configure-import-accounts.md#configure-a-location-account)區段所述。

針對每個帳戶，收集下列資訊：

* **主機**：您帳戶所連線之 FTP 伺服器的主機名稱 (例如，`ftp.omniture.com`、`ftp2.omniture.com`等)。

* **連接埠**：使用 Adobe 託管的 SFTP 伺服器時，SFTP 用戶端會連線至連接埠 22。不安全的 FTP 連線會使用連接埠 21。

* **使用者名稱**：用於登入 FTP 伺服器的使用者名稱。

* **位置帳戶密碼**：帳戶目前的帳戶密碼。這是您目前在下載傳遞至 FTP 位置之資料時所使用的帳戶密碼。此資訊無法從 Adobe Analytics 介面取得。

### 確認您可以在您的工具中更新認證

請確保您能夠在用於連線至 SFTP 網站的任何工具或腳本中更新 SFTP 密碼 (例如 SFTP 用戶端、自動指令碼或第三方平台)。

所有用戶端皆應透過 SFTP 連線，並使用密碼做為後備。

## 升級 FTP 伺服器以使用 SFTP

>[!IMPORTANT]
>
>如果您的 FTP 資料已傳遞給第三方合作夥伴 (例如諮詢公司或分析供應商)，請在遵循本文步驟之前先與其協調。

### 步驟 1：產生您組織的 SSH 金鑰，用於下載資料

本區段說明如何產生您組織的 SSH 金鑰 (公開/私密金鑰組)，這些金鑰用於從 SFTP 伺服器&#x200B;**下載資料**。

>[!NOTE]
>
>在後續的步驟中，您將下載 Adobe 提供的另一個公開金鑰。這是第二個公開/私用金鑰組的一部分，Adobe 會使用此金鑰組，將資料&#x200B;**上傳**&#x200B;至 SFTP 伺服器。

若要設定安全轉移，以便從 FTP 伺服器下載資料，請依循下列步驟：

1. 登入可從 FTP 伺服器下載資料的工作站。

1. 產生公開/私用金鑰組，用於安全轉移。

   使用 Adobe 託管的 SFTP 伺服器時，Adobe 支援 RSA 和 ed25519 金鑰。

   * **在 Linux 環境中**：執行下列命令來產生 ed25519 金鑰組：

     ```
     ssh-keygen -t ed25519 -C "your-comment-or-email"
     ```

     如果您的原則不允許您使用 ed25519 金鑰，請執行以下命令產生 RSA 金鑰組：

     ```
     ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
     ```

   * **在 Windows 環境中**：使用 PuTTYgen。

1. 建立名為 [!DNL `authorized_keys`] 的檔案 (無副檔名)。

1. 將公開金鑰的內容複製至 [!DNL `authorized_keys`] 檔案。

1. 在後續的步驟中，您將回到此 [!DNL `authorized_keys`] 檔案以新增 Adobe 的公開金鑰，Adobe 會使用該金鑰將資料上傳至 SFTP 伺服器。然後您會將 [!DNL `authorized_keys`] 檔案新增至 SFTP 伺服器。

### 步驟 2：在 Adobe Analytics 中建立新的 SFTP 位置帳戶

建立新的 SFTP 位置帳戶，取代各既有的 FTP 帳戶。

建立新的 SFTP 位置帳戶時，必須使用與其取代之既有 FTP 帳戶中相同的主機名稱和使用者名稱。

>[!NOTE]
>
>在後續的步驟中，您將設定此新位置帳戶，做為資料摘要和 Data Warehouse 傳遞的目標。

#### 建立 SFTP 帳戶

1. 在 Adobe Analytics 中，前往「[!UICONTROL **元件**] > [!UICONTROL **位置**]」。

1. 選取「[!UICONTROL **位置帳戶**]」索引標籤。

1. 選取「[!UICONTROL **新增帳戶**]」。

1. 在「[!UICONTROL **帳戶類型**]」下拉式選單中，選取「[!UICONTROL **SFTP (舊版)**]」。

1. 填入下列欄位：

   | 欄位名稱 | 函數 |
   |---------|----------|
   | [!UICONTROL **主機名稱**] | 您的 SFTP 主機名稱 (例如，`ftp.omniture.com`)。 |
   | [!UICONTROL **連接埠**] | 資料將透過防火牆連接埠傳送。對於 Adobe 託管之 SFTP 連線，此為連接埠 22。 |
   | [!UICONTROL **使用者名稱**] | 您的 SFTP 使用者名稱。使用您 FTP 帳戶所用的相同使用者名稱。 |

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

1. 在「[!UICONTROL **已建立帳戶**]」對話框中，下載 RSA 或 ed25519 公開金鑰，然後選取「[!UICONTROL **確定**]」。此為 Adobe 用於將資料上傳至 SFTP 伺服器的 SSH 公開金鑰。(您將在下一區段之[將 Adobe 的 SSH 公開金鑰新增至 SFTP 伺服器](#add-adobes-ssh-public-key-to-the-sftp-server)中使用此金鑰。)

1. 針對您要建立的每個 SFTP 帳戶重複此程序。

1. 繼續進行下列區段，[將公開金鑰上傳至 SFTP 伺服器](#upload-the-public-key-to-the-sftp-server)。

#### 將 Adobe 的 SSH 公開金鑰新增至 [!DNL `authorized_keys`] 檔案，並將其上傳至您的 FTP 伺服器

您在上一區段步驟 7 中下載的公開金鑰屬於公開/私用金鑰組，Adobe 會使用該金鑰組&#x200B;**將資料上傳**&#x200B;至 SFTP 伺服器。

您必須將此公開金鑰新增至您先前新增過組織下載金鑰的 [!DNL `authorized_keys`] 檔案 (您在[步驟 1：產生您組織的 SSH 金鑰，用於下載資料](#step-1-generate-your-organizations-ssh-keys-for-downloading-data)) 中。

若要將 Adobe 的 SSH 公開金鑰新增至 [!DNL `authorized_keys`] 檔案，並將其上傳至您的 FTP 伺服器：

1. 登入可從 FTP 伺服器下載資料的工作站。

1. 開啟 [!DNL `authorized_keys`] 檔案並將 Adobe 的上傳金鑰新增至其中。此檔案應已包含您組織的下載金鑰 (源自[步驟 1：產生您組織的 SSH 金鑰，用於下載資料](#step-1-generate-your-organizations-ssh-keys-for-downloading-data))。

1. 將 [!DNL `authorized_keys`] 檔案上傳至您的 FTP 伺服器：

   1. 連線至 FTP 伺服器，並使用您的使用者名稱和密碼登入。
可以是 Adobe 託管的 FTP 伺服器或您自己的 FTP 伺服器。
   1. 建立 [!DNL .ssh] 目錄 (如果尚未存在)。
   1. 上傳 [!DNL `authorized_keys`] 檔案至 [!DNL .ssh] 目錄。

1. 更新您的防火牆設定，允許來自 SFTP 伺服器的輸入連線。使用 Adobe 託管的 SFTP 伺服器時，請允許來自連接埠 22 上 Adobe IP 範圍的輸入連線。

1. 使用 SFTP 用戶端登入伺服器，測試連線是否正常。

1. 對您在上一區段 ([建立 SFTP 帳戶](#create-the-sftp-account)) 中建立的各 SFTP 帳戶重複此程序。

1. 繼續進行下列區段，[在帳戶內新增位置](#add-a-location-within-the-account)。

#### 在帳戶內新增位置

1. 在「[!UICONTROL **位置**]」索引標籤上，選取「[!UICONTROL **新增位置**]」。

1. 指定名稱、說明，以及此位置是否會與資料摘要或 Data Warehouse 搭配使用。

1. 在「[!UICONTROL **位置帳戶**]」欄位中，選取您剛建立的帳戶。

1. 在「[!UICONTROL **目錄路徑**]」欄位中，指定 SFTP 伺服器上目錄的路徑。路徑中的資料夾必須已存在，否則會發生錯誤。例如，`/folder_name/folder_name`。

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

1. 對您建立的每個 SFTP 帳戶重複此程序。

如需詳細說明，請參閱[設定雲端匯入及匯出位置](https://experienceleague.adobe.com/zh-hant/docs/analytics/components/locations/configure-import-locations)。

### 步驟 3：編輯資料摘要和 Data Warehouse 請求，使用新的 SFTP 目標

更新目前傳送資料至 FTP 目標之任何現有的排程資料摘要和 Data Warehouse 請求，採用您建立的新 SFTP 目標。

#### 編輯資料摘要

編輯每個已設定為使用舊 FTP 目標的排程資料摘要，採用新 SFTP 目標：

1. 在 Adobe Analytics 中，選取「[!UICONTROL **管理員**] > [!UICONTROL **資料摘要**]」。

1. 找到您要編輯的資料摘要。若要尋找資料摘要，您可以[篩選及搜尋資料摘要清單](#filter-and-search-the-list-of-data-feeds)。

1. 在「[!UICONTROL **摘要名稱**]」欄中選取資料摘要。

   「[!UICONTROL **編輯&#x200B;_摘要名稱_**]」頁面會顯示。

1. 在「[!UICONTROL **目標**]」區段的「[!UICONTROL **帳戶**]」欄位中，使用下拉式選單選取您建立的新 SFTP 目標。

1. 在「[!UICONTROL **位置**]」欄位中，使用下拉式選單選取 SFTP 帳戶中的位置。

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

如需詳細資訊，請參閱[管理資料摘要](/help/export/analytics-data-feed/df-manage-feeds.md)中的[編輯資料摘要](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed)。

#### 編輯 Data Warehouse 請求

編輯每個已設定為使用舊 FTP 目標的排程 Data Warehouse 請求，採用新 SFTP 目標：

1. 在 Adobe Analytics 中，選取「[!UICONTROL **工具**] > [!UICONTROL **Data Warehouse**]」。

1. 在 Data Warehouse 頁面上，選取您要編輯的請求。

   ![管理請求](assets/dw-manage-request.png)

1. 選取「[!UICONTROL **編輯**]」。

1. 選取「[!UICONTROL **報告目標**]」索引標籤。

1. 在「[!UICONTROL **帳戶**]」欄位中，使用下拉式選單選取您建立的新 SFTP 目標。

1. 在「[!UICONTROL **位置**]」欄位中，使用下拉式選單選取 SFTP 帳戶中的位置。

1. 選取「[!UICONTROL **儲存變更**]」。

如需詳細資訊，請參閱[管理 Data Warehouse 請求](/help/export/data-warehouse/data-warehouse-requests-manage.md)中的[編輯請求](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests)。

### 步驟 4：更新防火牆設定

如果您尚未更新，則需要更新防火牆設定，如下所示：

* **使用 Adobe 的 FTP 伺服器時**：您必須更新防火牆設定，允許連接埠 22 上的&#x200B;**輸出**&#x200B;連線。

* **使用您自己的 FTP 伺服器時**：您需要更新防火牆設定，在您託管服務的任何連接埠 (通常為連接埠 22) 上允許&#x200B;**輸入**&#x200B;連線。

您也應該移除舊的 FTP 特定規則，例如允許連接埠 21 上的輸入連線。(FTP 使用連接埠 21，外加一系列額外的連接埠進行資料轉移。根據安全性最佳做法，您最終應該透過防火牆移除這項不必要的存取。)

### 步驟 5：確保已排程的資料摘要和 Data Warehouse 請求能正確傳遞

更新各現有的資料摘要和 Data Warehouse 請求，以使用新的 SFTP 帳戶和位置後，請等待下一次排程傳遞。確認資料如預期地抵達新目標。

### 步驟 6：在升級的 SFTP 伺服器上輪換密碼

將 FTP 伺服器升級為 SFTP 之後，您也必須輪換 SFTP 密碼，如下方[輪換 SFTP 密碼](#rotate-your-sftp-password)區段所述。

## 輪換 SFTP 密碼

如果金鑰式驗證失敗，SFTP 密碼會做為遞補驗證方法。

從 FTP 升級為 SFTP 後，立即輪換 SFTP 密碼。應根據您建立的原則，繼續定期輪換。

1. 聯絡 Adobe 客戶服務申請新密碼。

1. 針對各 SFTP 帳戶，提供&#x200B;**主機名稱**&#x200B;和&#x200B;**使用者名稱**。

   客戶服務將為每個 FTP 帳戶產生新密碼。

1. 更新您用於連線至 SFTP 伺服器之任何用戶端中的密碼。


