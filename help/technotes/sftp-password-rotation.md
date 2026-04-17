---
title: FTP和SFTP伺服器的安全性需求
description: 瞭解FTP和SFTP伺服器的安全性需求。
feature: Data Configuration and Collection
role: Admin
source-git-commit: 26ae4edacbc3591d4d3358afe009bf7831d45efb
workflow-type: tm+mt
source-wordcount: '1899'
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

### 清查您的FTP帳戶

升級FTP伺服器以使用SFTP時，本頁所述的程式必須對用於資料摘要和Data Warehouse的每個FTP站台完成。

因此，您必須識別所有接收資料摘要或Data Warehouse資料的FTP帳戶。 此資訊會顯示在您的FTP組態設定中，如文章[設定雲端匯入和匯出帳戶](/help/components/locations/configure-import-accounts.md#configure-a-location-account)中的[舊版帳戶型別](/help/components/locations/configure-import-accounts.md)區段所述。

針對每個帳戶，收集下列資訊：

* **主機**：您的帳戶所連線之FTP伺服器的主機名稱（例如，`ftp.omniture.com`、`ftp2.omniture.com`等）。

* **連線埠**：使用Adobe代管的SFTP伺服器時，SFTP使用者端會連線到連線埠22。 不安全的FTP連線使用連線埠21。

* **使用者名稱**：用來登入FTP伺服器的使用者名稱。

* **位置帳戶密碼**：帳戶的目前帳戶密碼。 這是您目前下載傳送至FTP位置之資料的帳戶機密（密碼）。 Adobe Analytics介面不提供此資訊。

### 確認您可以在工具中更新認證

請務必在您用來連線至SFTP站台的工具或指令碼（例如SFTP使用者端、自動指令碼或協力廠商平台）中更新SFTP密碼。

所有使用者端都應透過SFTP連線，並以密碼作為遞補密碼。

## 升級FTP伺服器以使用SFTP

>[!IMPORTANT]
>
>如果您的FTP資料已傳送給協力廠商合作夥伴（例如諮詢公司或分析供應商），請在遵循本文步驟之前先與其協調。

### 步驟1：產生您組織的SSH金鑰以下載資料

本節說明如何產生您組織的SSH金鑰（公開/私密金鑰組），這些金鑰用於從SFTP伺服器&#x200B;**下載資料**。

>[!NOTE]
>
>在未來的步驟中，您將下載Adobe提供的另一個公開金鑰。 這是第二個公開/私用金鑰組的一部分，Adobe會使用該金鑰組，將資料&#x200B;**上傳**&#x200B;至SFTP伺服器。

若要設定安全傳輸，以便從FTP伺服器下載資料：

1. 登入可從FTP伺服器下載資料的工作站。

1. 產生公開/私用金鑰組以用於安全傳輸。

   使用Adobe代管的FTP伺服器時，Adobe支援RSA和ed25519金鑰。

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
>在未來的步驟中，您將設定此新位置帳戶，以作為資料摘要和Data Warehouse傳遞的目的地。

#### 建立SFTP帳戶

1. 在Adobe Analytics中，前往&#x200B;[!UICONTROL **元件**] > [!UICONTROL **位置**]。

1. 選取&#x200B;[!UICONTROL **位置帳戶**]&#x200B;索引標籤。

1. 選取&#x200B;[!UICONTROL **新增帳戶**]。

1. 在&#x200B;[!UICONTROL **帳戶型別**]&#x200B;下拉式欄位中，選取&#x200B;[!UICONTROL **SFTP （舊版）**]。

1. 填入下列欄位：

   | 欄位名稱 | 函數 |
   |---------|----------|
   | [!UICONTROL **主機名稱**] | 您的SFTP主機名稱（例如，`ftp.omniture.com`）。 |
   | [!UICONTROL **連線埠**] | 資料將透過防火牆連線埠傳送。 這是Adobe代管SFTP連線的連線埠22。 |
   | [!UICONTROL **使用者名稱**] | 您的SFTP使用者名稱。 使用您FTP帳戶所用的相同使用者名稱。 |

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

1. 在&#x200B;[!UICONTROL **已建立的帳戶**]&#x200B;對話方塊中，下載RSA或ed25519公開金鑰，然後選取&#x200B;**[!UICONTROL 確定]**。 這是Adobe用來將資料上傳至SFTP伺服器的SSH公開金鑰。 （您將在下一節[將Adobe的SSH公開金鑰新增至SFTP伺服器](#add-adobes-ssh-public-key-to-the-sftp-server)中使用此金鑰。）

1. 對您要建立的每個SFTP帳戶重複此程式。

1. 繼續下列章節，[將公開金鑰上傳至SFTP伺服器](#upload-the-public-key-to-the-sftp-server)。

#### 將Adobe的SSH公開金鑰新增至`authorized_keys`檔案，並將其上傳至您的FTP伺服器

您在上一節的步驟7中下載的公開金鑰屬於公開/私用金鑰組，Adobe會使用該金鑰組&#x200B;**將資料**&#x200B;上傳至SFTP伺服器。

您必須將此公開金鑰新增至您先前新增組織下載金鑰的`authorized_keys`檔案（您在[步驟1：產生您組織的下載金鑰，並將其新增至您的FTP伺服器](#step-1-generate-your-organizations-download-key-and-add-it-to-your-ftp-server)）。

若要將Adobe的SSH公開金鑰新增至`authorized_keys`檔案並上傳至您的FTP伺服器：

1. 登入可從FTP伺服器下載資料的工作站。

1. 開啟[!DNL `authorized_keys`]檔案並新增Adobe的上傳金鑰至其中。 此檔案應已包含您組織的下載金鑰（從[步驟1：產生您組織的下載金鑰，並將其新增至您的FTP伺服器](#step-1-generate-your-organizations-download-key-and-add-it-to-your-ftp-server)）。

1. 將[!DNL `authorized_keys`]檔案上傳至您的FTP伺服器：

   1. 連線至FTP伺服器，並使用您的使用者名稱和密碼登入。\
      這可以是Adobe託管的FTP伺服器或您自己的FTP伺服器。
   1. 建立 [!DNL .ssh] 目錄 (如果尚未存在)。
   1. 上傳 [!DNL `authorized_keys`] 檔案至 [!DNL .ssh] 目錄。

1. 更新您的防火牆設定，以允許來自SFTP伺服器的輸入連線。 使用Adobe代管的SFTP伺服器時，請允許來自連線埠22上Adobe IP範圍的輸入連線。

1. 使用您的SFTP使用者端登入伺服器以測試連線。

1. 對您在上一節中建立的每個SFTP帳戶[建立SFTP帳戶](#create-the-sftp-account)重複此程式。

1. 繼續下列區段，[在帳戶](#add-a-location-within-the-account)內新增位置。

#### 在帳戶內新增位置

1. 在&#x200B;**位置**&#x200B;索引標籤上，選取&#x200B;**新增位置**。

1. 指定名稱、說明，以及此位置是否會與資料摘要或Data Warehouse搭配使用。

1. 在&#x200B;[!UICONTROL **位置帳戶**]&#x200B;欄位中，選取您剛建立的帳戶。

1. 在&#x200B;[!UICONTROL **目錄路徑**]&#x200B;欄位中，指定SFTP伺服器上目錄的路徑。 路徑中的資料夾必須已存在；否則，會發生錯誤。 例如，`/folder_name/folder_name`。

1. 選取&#x200B;**「儲存」**。

1. 對您建立的每個SFTP帳戶重複此程式。

如需詳細指示，請參閱[設定雲端匯入和匯出位置](https://experienceleague.adobe.com/zh-hant/docs/analytics/components/locations/configure-import-locations)。

### 步驟3：編輯資料摘要和Data Warehouse請求，以使用新的SFTP目的地

更新目前傳送資料至FTP目的地的任何現有排程資料摘要和Data Warehouse請求，以使用您建立的新SFTP目的地。

#### 編輯資料摘要

編輯每個已設定為使用舊FTP目的地的排程資料摘要，以使用新SFTP目的地：

1. 在Adobe Analytics中，選取&#x200B;[!UICONTROL **管理員**] > [!UICONTROL **資料摘要**]。

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

1. 在Data Warehouse頁面上，選取您要編輯的請求。

   ![管理要求](assets/dw-manage-request.png)

1. 選取「[!UICONTROL **編輯**]」。

1. 選取&#x200B;[!UICONTROL **報告目的地**]&#x200B;標籤。

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


<!--
< **_Ignore everything after this_** >

-------

## Set up a new SFTP server or upgrade your existing FTP server

## Upgrade your FTP server to use SFTP where files are delivered or FTP account to use SFTP

Set up an SFTP server where Data Feed and Data Warehouse files can be delivered. This could beYou first need to upgrade your FTP server to use SFTP To upgrade an FTP account to use SFTP, follow the steps in [Connect to an FTP account with SFTP](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md).

## Create an SFTP account

## Rotate the passphrase on SFTP accounts


 
Adobe recommends that you periodically rotate the account secrets (passwords) on your FTP accounts that are associated with Data Feeds and Data Warehouse. 
 
Regular rotation of account secrets is a security best practice that helps protect your data. 
 
To ensure uninterrupted reception of data, follow the steps in [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets) prior to changing any account secrets.  
 
>[!IMPORTANT] 
> 
>If your FTP data is delivered to a third-party partner (for example, a consulting firm or Adobe Analytics vendor), coordinate with them before rotating account secrets. The third-party partner will need to update their own tools and scripts with the new account secrets immediately after the new account secrets are provided by your FTP host provider (either Adobe or another provider).

## When rotating account secrets is not necessary 
 
### Transition from FTP to a cloud destination 
 
FTP and SFTP are legacy destination types. Rather than rotating FTP account secrets, Adobe recommends moving to a modern cloud destination type (such as Amazon S3, Google Cloud Platform, or Azure), which provide a higher level of security. For more information, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts). 
 
### Transition from the Classifications importer to Classification sets 
 
If your FTP account is used exclusively for Classifications, you should migrate from the **Classifications importer** to **Classification sets**, rather than rotating your FTP account secrets. The Classification importer will be deprecated and no longer accessible after **August 31, 2026**. For more information, see [Classification sets overview](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/sets/overview). 

## Prepare to rotate account secrets 
 
Complete the following steps before attempting to rotate FTP account secrets: 
 
### Step 1: Inventory your FTP accounts 
 
Identify all FTP accounts that are receiving data for Data Feeds or Data Warehouse. This information is shown in your FTP configuration settings, as described in the [Legacy account types](/help/components/locations/configure-import-accounts.md#configure-a-location-account) section of the article [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md). 
 
For each account, gather the following information: 
 
* **Host**: The FTP destination of the host your account connects to (for example, `ftp.omniture.com`, `ftp2.omniture.com`, and so forth). 
 
* **Port**: SFTP clients connect on port 22. FTP connections that are non-secure use port 21. 
 
* **Username**: The username used to log in to the FTP site. 
 
* **location account secret**: The current account secret for the account. This is the account secret (password) that you use currently when downloading data delivered to your FTP location. This information is not available from the Adobe Analytics interface. 
 
 
### Step 2: Confirm that you can update credentials in your tools 
 
Make sure you can update the FTP account secret in whatever tool or script you use to connect to the FTP site (for example, an FTP client, automated script, or third-party platform). 
 
### Step 3: Create FTP cloud location accounts with your current credentials 
 
Create new FTP cloud location accounts to replace your existing FTP location accounts. These new accounts will be used as the destination for your Data Feeds and Data Warehouse deliveries.  
 
When creating the new FTP accounts, you must use the same hostname, username, and account secret that are used in your existing FTP accounts. 
 
#### Create each FTP account 
 
1. In Adobe Analytics, go to **Components** > **Locations**. 
 
1. Select the **Location accounts** tab. 
 
1. Select **Add account**. 
 
1. In the **Account type** drop-down field, select **FTP (legacy)**. 
 
1. Complete the following fields: 

   | Field name | Function |
   |---------|----------|
   | **Hostname** |  Your Adobe FTP hostname (for example, `ftp.omniture.com`). | 
   | **Port** | SFTP clients connect on port 22. FTP connections that are non-secure use port 21. | 
   | **Username** | Your current FTP username. |
   | **Location account secret** | Your current FTP account secrets (password).  |
 
1. Select **Save**. 
 
Repeat this process for each FTP account. 
 
For detailed instructions, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts). 
 
#### Add a location within the account 
 
1. On the **Locations** tab, select **Add location**. 
 
1. Specify a name, description, and whether this location will be used with Data Feeds or Data Warehouse. 
 
1. In the [!UICONTROL **Location account**] field, select the account you just created. 
 
1. In the [!UICONTROL **Directory path**] field, specify the path to the directory on the FTP server. Folders must already exist; feeds throw an error if the specified path does not exist. For example, `/folder_name/folder_name`. 
 
1. Select **Save**. 
 
Repeat this process for each location. 
 
For detailed instructions, see [Configure cloud import and export locations](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-locations). 
 
### Step 4: Reference the new FTP cloud accounts from any scheduled Data Feeds and Data Warehouse requests 
 
Update any existing scheduled Data Feeds and Data Warehouse requests to use the FTP cloud accounts you created.  
 
* **Data Feeds**: Go to **Admin** > **Data Feeds**, edit each scheduled  Data Feed that uses an FTP account, then change the destination to the newly created FTP cloud account. 
 
  For detailed instructions, see [Edit a data feed](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md). 
 
* **Data Warehouse**: Go to **Tools** > **Data Warehouse**, edit each scheduled Data Warehouse request that uses an FTP account, then change the report destination to the newly created FTP cloud account. 
 
  For detailed instructions, see [Edit requests](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests) in [Manage Data Warehouse requests](/help/export/data-warehouse/data-warehouse-requests-manage.md). 
 
### Step 5: Ensure that scheduled Data Feeds and Data Warehouse requests are being delivered correctly. 
 
After updating each existing Data Feed and Data Warehouse request to use the new FTP account and location, wait for the next scheduled delivery. Verify that data arrives at the new destination as expected. 

## Request a new account secret 
 
>[!IMPORTANT] 
>
>Before requesting a new account secret, consider the following:
>
>* The steps in this section apply only if you are using an Adobe-provided FTP account. For example, the FTP hostname is `ftp.omniture.com`, `ftp2.omniture.com` or similar.   If your FTP hostname is not provided by Adobe, please contact your FTP host provider for details on changing the account secret.
> 
>* Request a new account secret only after you complete all the preparation steps described in [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets). 
>
>* After Adobe Customer Care or your third-party FTP host provider provides a new account secret, the old account secret is immediately invalidated. There is no way to revert to the previous account secret. 
>
 
To request a new account secret from Adobe: 
 
1. Contact Adobe Customer Care. 
 
1. For each FTP account, provide the **Hostname** and **Username** for each account that needs a new account secret. 
 
   Customer Care will generate a new account secret for each FTP account. 

1. Continue immediately with the following section, [After you receive the new account secret](#after-you-receive-the-new-account-secret).
 
## After you receive the new account secret 
 
Act immediately after receiving the new credentials. Any delay results in failed deliveries for active Data Feeds and Data Warehouse requests. 
 
### Step 1: Update your tools and scripts 
 
Update the FTP account secret in any tool, script, or automated process that connects to the FTP account. Make sure all team members and third-party partners who access the account are notified. 
 
### Step 2: Update your cloud location accounts 
 
1. In Adobe Analytics, go to **Components** > **Locations**. 

1. Select the **Location accounts** tab. 

1. Find the FTP account that you created in Step 3 of section, [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets).

1. Select **Edit details**. 

1. Enter the new account secret and confirm it. 

1. Select **Save**. 
 
Repeat this process for each account that was reset. 

For more detailed information about this process, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts).
 
### Step 3: Test your connections 
 
Verify that your Data Feeds or Data Warehouse requests that use the FTP account are working correctly with the new account secret. 
 
>[!TIP] 
> 
>If your current tools use SFTP with SSH keys that haven't been recently rotated, consider rotating those keys as well.

 
## Troubleshooting 
 
If something goes wrong after the account secret is rotated and you cannot restore connectivity, you can create a new FTP account. After the new account is set up, point your Data Feed or Data Warehouse request to the new account and update your cloud location accordingly. 

For information about how to create an FTP account, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts).

To set up secure transfer with your FTP server: 

1. Generate a public/private key pair to use for secure transfer.

   This process differs depending on whether your FTP server is Adobe-hosted or self-hosted:

   +++ For an Adobe-hosted FTP server:

   Generate a public/private key pair: 
   
      * **In a Linux environment**: Run the following command to generate the ed25519 key pair: 

        ```
        ssh-keygen -t ed25519 -C "your-comment-or-email"
        ```

        If your policy does not allow you to use ed25519 keys, run the following command to generate the RSA key pair (**Note:** The RSA key typically applies to customers who operate under FIPS 186-4, as ed25519 is first supported in the newer FIPS 186-5):

        ```
        ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
        ```

      * **In a Windows environment**: Use PuTTYgen.

   +++

   +++ For a self-hosted FTP server: 
   
   If you want to set up secure transfer with your own FTP server, you must have an SFTP hostname, username, and SFTP account within Adobe Analytics that contains a valid RSA or ed25519 public key from Adobe. This key must be installed on your SFTP server. You download this public key as part of the process of [creating the SFTP account](#create-the-sftp-account).

   +++

1. Create a file named [!DNL `authorized_keys`] (no extension).



3 basic steps: Set up SFTP on customer side, then on Adobe side, then change passphrase. 

1. FTP site: ftp.omniture.com - Using username/password to connect. Adobe uses the same username/password to connect to the site.

2. user can then upload their public key to that server, then start connecting to that server with their private key using SFTP. (They also need to open Port 22 in the firewall and they would close the other ports they don't need.)

3. In Locations, create a new location, use the same username. 

4. After they create that location, we give them our public key, and they have to install it on their SFTP server.

5. Then they switch all their data feeds to use the new Location. And then we'll use SFTP to send the data. 

6. Then they call Customer Care to get new passphrase (rotate passphrase), and then they change the passphrase on their side. Passphrase is only used if SSH fails (they have the wrong keys--a bad actor could use bad keys and then use the password. But they don't have to coordinate the switching of the passphrase with installation of SFTP. )


If they're using a third-party to do this, the third-party would need to set up SFTP - This is the same as we have documented right now. It doesn't have to be immediate, though, like we were assuming before. 


If it's they're own FTP site, it would be the same. They would need to start using SFTP with their FTP server, then get our public key and install it on their server. Shouldn't matter if the FTP site is hosted by Adobe or not. 

-->

