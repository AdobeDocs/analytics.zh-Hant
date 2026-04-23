---
title: FTP和SFTP伺服器的安全性需求
description: 瞭解FTP和SFTP伺服器的安全性需求。
feature: Data Configuration and Collection
role: Admin
source-git-commit: 9067b57a7436656b6776de08e8411ee0a87f2b20
workflow-type: tm+mt
source-wordcount: '1881'
ht-degree: 2%

---

# FTP和SFTP伺服器的安全性需求

此頁面說明接收Adobe Analytics資料摘要或Data Warehouse所提供資料的現有FTP和SFTP伺服器的安全性需求。

* **現有的FTP伺服器**：必須升級為使用SFTP，如下節所述，[升級FTP伺服器以使用SFTP](#upgrade-ftp-servers-to-use-sftp)。

  從FTP升級至SFTP為必要操作，因為SFTP可提升安全性。

  或者，如需更高級別的安全性，您可以轉換至現代化的雲端目的地。 （如需詳細資訊，請參閱[設定雲端匯入和匯出帳戶](https://experienceleague.adobe.com/zh-hant/docs/analytics/components/locations/configure-import-accounts)。）

* **現有SFTP伺服器（以及新升級的SFTP伺服器）**：必須輪換舊密碼，如下節所述，[輪換您的SFTP密碼](#rotate-your-sftp-password)。

  定期輪換SFTP密碼是有助於保護資料的安全性最佳做法。

>[!IMPORTANT]
>
>完成本文中的步驟之前，請先考量下列情況。
>
>* **Adobe建議儘可能轉換至現代化的雲端目的地，而非升級至SFTP。**
>FTP和SFTP是舊有的目的地型別。 Adobe建議您改用新型雲端目的地型別（例如Amazon S3、Google Cloud Platform或Azure），而不要依照本文所述將FTP帳戶升級為SFTP和輪換SFTP密碼。 這些雲端目的地提供更高層級的安全性。 如需詳細資訊，請參閱[設定雲端匯入和匯出帳戶](https://experienceleague.adobe.com/zh-hant/docs/analytics/components/locations/configure-import-accounts)。
>
>* **如果FTP和SFTP帳戶僅用於「分類」，請移轉至「分類設定」。**
>如果您的FTP或SFTP帳戶僅用於分類，您應該從&#x200B;**分類匯入工具**&#x200B;移轉至&#x200B;**分類設定**，而非依照本文所述將FTP帳戶升級為SFTP和旋轉SFTP密碼。 分類匯入工具將遭取代，且在&#x200B;**2026年8月31日**&#x200B;後無法再存取。 如需詳細資訊，請參閱[分類集總覽](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/sets/overview)。

## 先決條件

### Inventory your FTP accounts

You must complete the SFTP upgrade steps on this page for every FTP site used with Data Feeds or Data Warehouse.

As such, you must identify all FTP accounts that are receiving data for Data Feeds or Data Warehouse. This information is shown in your FTP configuration settings, as described in the [Legacy account types](/help/components/locations/configure-import-accounts.md#configure-a-location-account) section of the article [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md).

For each account, gather the following information:

* **主機**：您的帳戶所連線之FTP伺服器的主機名稱（例如，`ftp.omniture.com`、`ftp2.omniture.com`等）。

* **連線埠**：使用Adobe代管的SFTP伺服器時，SFTP使用者端會連線到連線埠22。 不安全的FTP連線使用連線埠21。

* **使用者名稱**：用來登入FTP伺服器的使用者名稱。

* **位置帳戶密碼**：帳戶的目前帳戶密碼。 這是您目前下載傳送至FTP位置之資料的帳戶機密（密碼）。 Adobe Analytics介面不提供此資訊。

### 確認您可以在工具中更新認證

請務必在您用來連線至SFTP站台的工具或指令碼（例如SFTP使用者端、自動指令碼或協力廠商平台）中更新SFTP密碼。

所有使用者端應透過SFTP連線，並使用密碼作為遞補密碼。

## 升級FTP伺服器以使用SFTP

>[!IMPORTANT]
>
>如果您的FTP資料已傳送給協力廠商合作夥伴（例如諮詢公司或分析供應商），請在遵循本文步驟之前先與其協調。

### 步驟1：產生您組織的SSH金鑰以下載資料

This section describes how to generate your organization&#39;s SSH keys (a public/private key pair) that are used to **download data** from the SFTP server.

>[!NOTE]
>
>In a future step, you will download another public key provided by Adobe. This is part of a second public/private key pair, which is used by Adobe to **upload data** to the SFTP server.

To set up secure transfer for downloading data from your FTP server:

1. 登入可從FTP伺服器下載資料的工作站。

1. 產生公開/私用金鑰組以用於安全傳輸。

   使用Adobe代管的SFTP伺服器時，Adobe支援RSA和ed25519金鑰。

   * **在Linux環境中**：執行下列命令來產生ed25519金鑰組：

     ```
     ssh-keygen -t ed25519 -C "your-comment-or-email"
     ```

     如果您的原則不允許您使用ed25519金鑰，請執行以下命令來產生RSA金鑰組：

     ```
     ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
     ```

   * **在Windows環境中**：使用PuTTYgen。

1. 建立名為 [!DNL `authorized_keys`] 的檔案 (無副檔名)。

1. 將公開金鑰的內容複製到[!DNL `authorized_keys`]檔案中。

1. 在未來的步驟中，您將回到此[!DNL `authorized_keys`]檔案來新增Adobe的公開金鑰，Adobe會使用該金鑰將資料上傳至SFTP伺服器。 然後您會將[!DNL `authorized_keys`]檔案新增至SFTP伺服器。

### 步驟2：在Adobe Analytics中建立新的SFTP位置帳戶

建立新的SFTP位置帳戶以取代每個現有的FTP帳戶。

建立新的SFTP位置帳戶時，您必須使用與其取代的現有FTP帳戶中所使用的相同主機名稱和使用者名稱。

>[!NOTE]
>
>In a future step, you will configure this new location account to be used as the destination for your Data Feeds and Data Warehouse deliveries.

#### Create the SFTP account

1. In Adobe Analytics, go to [!UICONTROL **Components**] > [!UICONTROL **Locations**].

1. Select the [!UICONTROL **Location accounts**] tab.

1. Select [!UICONTROL **Add account**].

1. 在&#x200B;[!UICONTROL **帳戶型別**]&#x200B;下拉式功能表中，選取&#x200B;[!UICONTROL **SFTP （舊版）**]。

1. 填入下列欄位：

   | 欄位名稱 | 函數 |
   |---------|----------|
   | [!UICONTROL **主機名稱**] | 您的SFTP主機名稱（例如，`ftp.omniture.com`）。 |
   | [!UICONTROL **連線埠**] | 資料將透過防火牆連線埠傳送。 這是Adobe代管SFTP連線的連線埠22。 |
   | [!UICONTROL **使用者名稱**] | 您的SFTP使用者名稱。 使用您FTP帳戶所用的相同使用者名稱。 |

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

1. 在&#x200B;[!UICONTROL **已建立的帳戶**]&#x200B;對話方塊中，下載RSA或ed25519公開金鑰，然後選取&#x200B;[!UICONTROL **確定**]。 這是Adobe用來將資料上傳至SFTP伺服器的SSH公開金鑰。 （您將在下一節[將Adobe的SSH公開金鑰新增至SFTP伺服器](#add-adobes-ssh-public-key-to-the-sftp-server)中使用此金鑰。）

1. 對您要建立的每個SFTP帳戶重複此程式。

1. 繼續下列章節，[將公開金鑰上傳至SFTP伺服器](#upload-the-public-key-to-the-sftp-server)。

#### 將Adobe的SSH公開金鑰新增至[!DNL `authorized_keys`]檔案，並將其上傳至您的FTP伺服器

您在上一節的步驟7中下載的公開金鑰屬於公開/私用金鑰組，Adobe會使用該金鑰組&#x200B;**將資料**&#x200B;上傳至SFTP伺服器。

您必須將此公開金鑰新增至您先前新增過組織下載金鑰的[!DNL `authorized_keys`]檔案（您在[步驟1：產生您組織的SSH金鑰以下載資料](#step-1-generate-your-organizations-ssh-keys-for-downloading-data)）中。

若要將Adobe的SSH公開金鑰新增至[!DNL `authorized_keys`]檔案並上傳至您的FTP伺服器：

1. 登入可從FTP伺服器下載資料的工作站。

1. 開啟[!DNL `authorized_keys`]檔案並新增Adobe的上傳金鑰至其中。 此檔案應已包含您組織的下載金鑰（從[步驟1：產生您組織的SSH金鑰以下載資料](#step-1-generate-your-organizations-ssh-keys-for-downloading-data)）。

1. 將[!DNL `authorized_keys`]檔案上傳至您的FTP伺服器：

   1. Connect to the FTP server and log in with your username and password.
這可以是Adobe託管的FTP伺服器或您自己的FTP伺服器。
   1. 建立 [!DNL .ssh] 目錄 (如果尚未存在)。
   1. 上傳 [!DNL `authorized_keys`] 檔案至 [!DNL .ssh] 目錄。

1. Update your firewall settings to allow inbound connections from the SFTP server. When using an Adobe-hosted SFTP server, allow inbound connections from Adobe&#39;s IP ranges on port 22.

1. 使用您的SFTP使用者端登入伺服器以測試連線。

1. 對您在上一節中建立的每個SFTP帳戶[建立SFTP帳戶](#create-the-sftp-account)重複此程式。

1. 繼續下列區段，[在帳戶](#add-a-location-within-the-account)內新增位置。

#### 在帳戶內新增位置

1. 在&#x200B;[!UICONTROL **位置**]&#x200B;索引標籤上，選取&#x200B;[!UICONTROL **新增位置**]。

1. 指定名稱、說明，以及此位置是否會與資料摘要或Data Warehouse搭配使用。

1. 在&#x200B;[!UICONTROL **位置帳戶**]&#x200B;欄位中，選取您剛建立的帳戶。

1. 在&#x200B;[!UICONTROL **目錄路徑**]&#x200B;欄位中，指定SFTP伺服器上目錄的路徑。 路徑中的資料夾必須已存在；否則，會發生錯誤。 例如，`/folder_name/folder_name`。

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

1. 對您建立的每個SFTP帳戶重複此程式。

For detailed instructions, see [Configure cloud import and export locations](https://experienceleague.adobe.com/zh-hant/docs/analytics/components/locations/configure-import-locations).

### 步驟3：編輯資料摘要和Data Warehouse請求，以使用新的SFTP目的地

Update any existing scheduled Data Feeds and Data Warehouse requests that currently send data to FTP destinations to use the new SFTP destinations you created.

#### Edit Data Feeds

Edit each scheduled data feed that is configured with the old FTP destination to use the new SFTP destination:

1. In Adobe Analytics, select [!UICONTROL **Admin**] > [!UICONTROL **Data feeds**].

1. 找到您要編輯的資料摘要。 若要尋找資料摘要，您可以[篩選及搜尋資料摘要清單](#filter-and-search-the-list-of-data-feeds)。

1. 在&#x200B;[!UICONTROL **摘要名稱**]&#x200B;欄中選取資料摘要。

   顯示&#x200B;[!UICONTROL **編輯&#x200B;_摘要名稱_**]頁面。

1. 在&#x200B;[!UICONTROL **目的地**]&#x200B;區段的&#x200B;[!UICONTROL **帳戶**]&#x200B;欄位中，使用下拉式功能表選取您建立的新SFTP目的地。

1. 在&#x200B;[!UICONTROL **位置**]&#x200B;欄位中，使用下拉式功能表選取SFTP帳戶中的位置。

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

如需詳細資訊，請參閱[管理資料摘要](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed)中的[編輯資料摘要](/help/export/analytics-data-feed/df-manage-feeds.md)。

#### 編輯Data Warehouse請求

編輯每個已排程Data Warehouse請求（這些請求已設定為使用舊版FTP目的地），以使用新的SFTP目的地：

1. 在Adobe Analytics中，選取&#x200B;[!UICONTROL **工具**] > [!UICONTROL **Data Warehouse**]。

1. On the Data Warehouse page, select the request that you want to edit.

   ![Manage a request](assets/dw-manage-request.png)

1. 選取「[!UICONTROL **編輯**]」。

1. Select the [!UICONTROL **Report destination**] tab.

1. 在&#x200B;[!UICONTROL **帳戶**]&#x200B;欄位中，使用下拉式功能表選取您建立的新SFTP目的地。

1. 在&#x200B;[!UICONTROL **位置**]&#x200B;欄位中，使用下拉式功能表選取SFTP帳戶中的位置。

1. 選取&#x200B;[!UICONTROL **儲存變更**]。

如需詳細資訊，請參閱[管理Data Warehouse請求](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests)中的[編輯請求](/help/export/data-warehouse/data-warehouse-requests-manage.md)。

### 步驟4：更新防火牆設定

如果您尚未更新，則需要更新防火牆設定，如下所示：

* **使用Adobe的FTP伺服器時**：您必須更新防火牆設定，以允許連線埠22上的&#x200B;**輸出**&#x200B;連線。

* **使用您自己的FTP伺服器時**：您需要更新防火牆設定，以便在您託管服務的任何連線埠（通常為連線埠22）上允許&#x200B;**輸入**&#x200B;連線。

您也應該移除舊的FTP特定規則，例如允許連線埠21上的輸入連線。 (FTP使用連線埠21，外加一系列額外的連線埠以進行資料傳輸。 根據安全性最佳實務，您最終應該透過防火牆移除這項不必要的存取。)

### 步驟5：確保已排程的資料摘要和Data Warehouse請求能正確傳送

更新每個現有的資料摘要和Data Warehouse請求，以使用新的SFTP帳戶和位置後，請等待下一個排程傳送。 確認資料如預期抵達新目的地。

### 步驟6：在升級的SFTP伺服器上輪換密碼

將FTP伺服器升級為SFTP之後，您也必須輪換SFTP密碼，如下節[輪換SFTP密碼](#rotate-your-sftp-password)所述。

## 輪換您的SFTP密碼

如果金鑰式驗證失敗，SFTP密碼會作為遞補驗證方法。

從FTP升級為SFTP後立即輪換SFTP密碼。 應根據您建立的原則，繼續定期輪換。

1. 聯絡Adobe客戶服務並申請新密碼。

1. 針對每個SFTP帳戶，提供&#x200B;**主機名稱**&#x200B;和&#x200B;**使用者名稱**。

   客戶服務將為每個FTP帳戶產生新密碼。

1. 更新您用來連線至SFTP伺服器的任何使用者端中的密碼。


