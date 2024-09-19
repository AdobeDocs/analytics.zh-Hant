---
description: 說明如何建立 Data Warehouse 請求的步驟。
title: 為 Data Warehouse 請求設定報告目標
feature: Data Warehouse
exl-id: 3c7faea3-4d90-4274-88f3-e9337c94155f
source-git-commit: d213befd0fd8d530d95b8d3ac3c4f3b808558244
workflow-type: tm+mt
source-wordcount: '1970'
ht-degree: 83%

---

# 為 Data Warehouse 請求設定報告目標

建立 Data Warehouse 請求時有多種可用的設定選項。以下資訊說明如何設定請求的報告目標。

有關如何開始建立請求的資訊，以及其他重要設定選項的連結，請參閱「[建立 Data Warehouse 請求](/help/export/data-warehouse/create-request/t-dw-create-request.md)」。

>[!NOTE]
>
>設定報告目標時，請考慮以下事項：
>
>* 我們建議您使用雲端帳戶或電子郵件作為您的報告目標。舊版[ FTP 和 SFTP 帳戶](#legacy-destinations)可供使用，但不建議使用。
>
>* 您先前設定的任何雲端帳戶都適合供 Data Warehouse 使用。您可以透過以下任一方式設定雲端帳戶：
>
>   * 設定[資料摘要](/help/export/analytics-data-feed/create-feed.md)
>   
>   * 當[匯入 Adob&#x200B;&#x200B;e Analytics 分類資料](/help/components/locations/locations-manager.md)時 (可以使用帳戶，但不能使用在這些帳戶上設定的任何位置。)
>   
>   * 從「位置」管理員，在「[元件 > 位置](/help/components/locations/configure-import-accounts.md)」中。
>
>* 雲端帳戶與您的 Adob&#x200B;&#x200B;e Analytics 使用者帳戶有關聯。其他使用者無法使用或查看您設定的雲端帳戶。
>
>* 您可以在「[元件 > 位置](/help/components/locations/configure-import-accounts.md)」中，編輯從「位置」管理員建立的任何位置

若要設定傳送 Data Warehouse 報告目標：

1. 如果還沒有，可選取「**[!UICONTROL 工具]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **新增**]」，開始在 Adobe Analytics 中建立請求。

   有關其他詳細資訊，請參閱「[建立 Data Warehouse 請求](/help/export/data-warehouse/create-request/t-dw-create-request.md)」。

1. 在「全新 Data Warehouse」請求頁面上，選取「[!UICONTROL **報告目標**]」標籤。

   ![報告目標標籤](assets/dw-report-destination.png)

1. (視情況而定) 如果已在 Adobe Analytics 設定雲端帳戶 (以及該帳戶目標)，您可以將其用作報告目標：

   >[!NOTE]
   >
   >只有在您已設定帳戶或您已與所屬組織共用帳戶時，您才可以使用這些帳戶。
   >
   >如果您是系統管理員，則可以使用「[!UICONTROL **顯示所有目標**]」選項。如果您有權存取組織中任何使用者建立的所有帳戶和位置，請啟用此選項。

   1. 從&#x200B;[!UICONTROL **帳戶**]&#x200B;下拉式功能表中選取帳戶。

      您在 Adob&#x200B;&#x200B;e Analytics 的以下任何區域中設定的任何雲端帳戶都可供使用：

      * 匯入 Adob&#x200B;&#x200B;e Analytics 分類資料時，如[結構描述](/help/components/classifications/sets/manage/schema.md)中所述。

        但是，為匯入分類資料所設定的任何位置無法供使用。相反地，請依照下面說明新增目標。

      * 在「位置」區域中設定帳戶和位置時，請參閱「[設定雲端匯入和匯出帳戶](/help/components/locations/configure-import-accounts.md)」和「[設定雲端匯入和匯出位置](/help/components/locations/configure-import-locations.md)」。

   1. 從「[!UICONTROL **選取目標**]」下拉式選單中選取與帳戶有關聯的目標。 <!-- Is this correct? -->

1. (視情況而定) 如果您無法存取已在 Adob&#x200B;&#x200B;e Analytics 中設定的雲端帳戶，您可以設定一個：

   1. 選取&#x200B;[!UICONTROL **帳戶**]&#x200B;下拉式功能表，然後選取&#x200B;[!UICONTROL **新增帳戶**]。

   1. 在新增帳戶對話方塊中，指定下列資訊：

      | 欄位 | 函數 |
      |---------|----------|
      | [!UICONTROL **位置帳戶名稱**] | 位置帳戶的名稱。 建立位置時會顯示此名稱 |
      | [!UICONTROL **位置帳戶描述**] | 提供帳戶的簡短說明，有助區分該帳戶與相同帳戶類型的其他帳戶。 |
      | [!UICONTROL **讓您的組織中的所有使用者都可以使用帳戶**] | 啟用此選項可允許組織中的其他使用者使用該帳戶。<p>共用帳戶時，請考量下列事項：</p><ul><li>您無法取消共用您共用的帳戶。</li><li>共用帳戶只能由帳戶擁有者編輯。</li><li>任何人都可以建立共用帳戶的位置。</li></ul> |
      | [!UICONTROL **帳戶類型**] | 選取您的雲端帳戶類型。我們建議為每種帳戶類型設定一個帳戶，並根據需要在該帳戶內設定多個位置。<p>系統管理員可以限制使用者可以建立的帳戶型別，如[設定使用者是否可以建立帳戶](/help/components/locations/locations-manager.md#configure-whether-users-can-create-accounts)中所述。 如果您無法依照本節所述建立帳戶，請連絡您的系統管理員。</p> |

   1. 在&#x200B;[!UICONTROL **帳戶屬性**]&#x200B;區段中，指定您所選取帳戶型別的特定資訊。

      如需設定指示，請展開下列對應至您選取之&#x200B;[!UICONTROL **帳戶型別**]&#x200B;的區段。 （也可使用其他舊帳戶型別，但不建議使用。）

      **帳戶型別**

      +++Amazon S3角色ARN

      若要設定 Amazon S3 角色 ARN 帳戶，請註明以下資訊：

      | 欄位 | 函數 |
      |---------|----------|
      | [!UICONTROL **角色 ARN**] | 您必須提供角色 ARN (Amazon 資源名稱)，以便 Adobe 可以使用該角色來取得 Amazon S3 帳戶的存取權。為此，您需要為來源帳戶建立 IAM 權限原則，將該原則附加給使用者，然後為目標帳戶建立角色。有關特定資訊，請參閱「[此 AWS 文件](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/)」。 |

      {style="table-layout:auto"}

+++

      +++Google Cloud Platform

      若要設定 Google Cloud Platform 帳戶，請註明以下資訊：

      | 欄位 | 函數 |
      |---------|----------|
      | [!UICONTROL **專案 ID**] | 您的 Google Cloud 專案 ID。請參閱「[Google Cloud 文件關於如何取得專案 ID](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects)」。 |

      {style="table-layout:auto"}

+++

      +++Azure SAS

      若要設定 Azure SAS 帳戶，請註明以下資訊：

      | 欄位 | 函數 |
      |---------|----------|
      | [!UICONTROL **應用程式 ID**] | 從您建立的 Azure 應用程式複製此 ID。在 Microsoft Azure 中，此資訊位於您應用程式中的「**概述**」標籤。若要了解更多資訊，請參閱「[Microsoft Azure 文件關於如何使用 Microsoft 身份識別平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)」。 |
      | [!UICONTROL **租用戶 ID**] | 從您建立的 Azure 應用程式複製此 ID。在 Microsoft Azure 中，此資訊位於您應用程式中的「**概述**」標籤。若要了解更多資訊，請參閱「[Microsoft Azure 文件關於如何使用 Microsoft 身份識別平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)」。 |
      | [!UICONTROL **金鑰保存庫 URI**] | <p>Azure Key Vault 中得到 SAS 權杖的路徑。若要設定Azure SAS，您必須使用Azure金鑰儲存庫將SAS權杖儲存為秘密。 若要了解更多資訊，請參閱「[Microsoft Azure 文件有關如何從 Azure Key Vault 設定和擷取密碼](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations)」。</p><p>建立金鑰儲存庫URI後，在金鑰儲存庫上新增存取原則，以授予您建立的Azure應用程式許可權。 若要了解更多資訊，請參閱「[Microsoft Azure 文件有關如何指定 Key Vault 存取權原則](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal)」。</p><p>或</p><p>如果您要直接授與存取角色而不建立存取原則，請參閱[Microsoft Azure檔案，瞭解如何使用Azure入口網站](https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal)指派Azure角色。 這會新增應用程式ID的角色指派，以存取金鑰儲存庫URI。 </p> |
      | [!UICONTROL **金鑰保存庫祕密名稱**] | 將密碼新增至Azure金鑰儲存庫時建立的密碼名稱。 在Microsoft Azure中，此資訊位於您建立的金鑰儲存庫中（位於&#x200B;**金鑰儲存庫**&#x200B;設定頁面上）。 若要了解更多資訊，請參閱「[Microsoft Azure 文件有關如何從 Azure Key Vault 設定和擷取密碼](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations)」。 |
      | [!UICONTROL **位置帳戶密碼**] | 從您建立的 Azure 應用程式複製密碼。在 Microsoft Azure 中，此資訊位於您的應用程式中的「**憑證和密碼**」標籤。若要了解更多資訊，請參閱「[Microsoft Azure 文件關於如何使用 Microsoft 身份識別平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)」。 |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      若要設定 Azure RBAC 帳戶，請註明以下資訊：

      | 欄位 | 函數 |
      |---------|----------|
      | [!UICONTROL **應用程式 ID**] | 從您建立的 Azure 應用程式複製此 ID。在 Microsoft Azure 中，此資訊位於您應用程式中的「**概述**」標籤。若要了解更多資訊，請參閱「[Microsoft Azure 文件關於如何使用 Microsoft 身份識別平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)」。 |
      | [!UICONTROL **租用戶 ID**] | 從您建立的 Azure 應用程式複製此 ID。在 Microsoft Azure 中，此資訊位於您應用程式中的「**概述**」標籤。若要了解更多資訊，請參閱「[Microsoft Azure 文件關於如何使用 Microsoft 身份識別平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)」。 |
      | [!UICONTROL **位置帳戶密碼**] | 從您建立的 Azure 應用程式複製密碼。在 Microsoft Azure 中，此資訊位於您的應用程式中的「**憑證和密碼**」標籤。若要了解更多資訊，請參閱「[Microsoft Azure 文件關於如何使用 Microsoft 身份識別平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)」。 |

      {style="table-layout:auto"}

+++

      +++電子郵件

      >[!NOTE]
      >
      >電子郵件帳戶只能與[資料摘要](/help/export/analytics-data-feed/create-feed.md)搭配使用。 ([Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)或[分類集](/help/components/classifications/sets/overview.md)不支援電子郵件帳戶)。

      若要設定 Azure RBAC 帳戶，請註明以下資訊：

      | 欄位 | 函數 |
      |---------|----------|
      | [!UICONTROL **收件者**] | 傳送報告時可以向特定使用者傳送電子郵件通知。指定單一電子郵件地址或逗號分隔的電子郵件地址清單。 |

      {style="table-layout:auto"}

+++

1. 在「[!UICONTROL **報告選項**]」標籤中，繼續設定您的 Data Warehouse 請求。有關詳細資訊，請參閱「[為 Data Warehouse 請求設定報告選項](/help/export/data-warehouse/create-request/dw-request-report-options.md)」。

## 舊版帳戶型別

>[!IMPORTANT]
>
>本節所述的目標是舊版目標，不建議使用。相反地，在建立 Data Warehouse 目標時，請使用下列目標之一：Amazon S3、Google Cloud Platform、Azure RBAC、Azure SAS 或電子郵件。有關每個建議使用的目標詳細資訊，請參閱上面資訊。

以下提供每個舊版目標的設定資訊：

### FTP

Data Warehouse 資料可以傳送至 Adobe 或客戶託管的 FTP 位置。FTP 主機、使用者名稱和密碼為必填。請使用路徑欄位將摘要檔案置入檔案夾。資料夾必須已存在；如果指定的路徑不存在，摘要會傳回錯誤。

填寫可用欄位時，請使用以下資訊：

#### 帳戶欄位

* [!UICONTROL **帳戶名稱**]：FTP 帳戶的名稱。

* [!UICONTROL **帳戶說明**]：FTP 帳戶的說明。

* [!UICONTROL **主機名稱**]：輸入所需的 FTP 目標 URL。例如，`ftp.company.com`。

  >[!NOTE]
  >
  >  URL 開頭切勿包含 `ftp://` 。

* [!UICONTROL **使用者名稱**]：輸入要登入 FTP 網站的使用者名稱。

* [!UICONTROL **密碼和確認密碼**]：輸入要登入 FTP 網站的密碼。

#### 位置欄位

* [!UICONTROL **位置名稱**]：在 FTP 帳戶上，您希望檔案傳送的位置名稱。

* [!UICONTROL **位置說明**]：FTP 帳戶上的位置說明。

* [!UICONTROL **目錄路徑**]：FTP 帳戶上位置的路徑。

### SFTP

提供 Data Warehouse 的 SFTP 支援 。必須填入 SFTP 主機、使用者名和目標網站，才能包含有效的 RSA 或 DSA 公開金鑰。建立 Data Warehouse 目標時，您可以下載適當的公開金鑰。

填寫可用欄位時，請使用以下資訊：

#### 帳戶欄位

* [!UICONTROL **帳戶名稱**]：FTP 帳戶的名稱。

* [!UICONTROL **帳戶說明**]：FTP 帳戶的說明。

* [!UICONTROL **主機名稱**]：輸入所需的 SFTP 目標 URL。例如，`sftp.company.com`。

  >[!NOTE]
  >
  >  URL 開頭切勿包含 `sftp://` 。

* [!UICONTROL **使用者名稱**]：輸入要登入 SFTP 網站的使用者名稱。

* [!UICONTROL **上傳期間使用臨時檔案副檔名**]：啟用後，將在上傳過程中使用 `.part` 檔案副檔名稱。維持啟用此選項，除非您的 SFTP 伺服器限制檔案上傳後不可變更檔案名稱。

* [!UICONTROL **公開金鑰**]：建立 Data Warehouse 目標時下載適當的公開金鑰。

#### 位置欄位

* [!UICONTROL **位置名稱**]：在 SFTP 帳戶上，您希望檔案傳送的位置名稱。

* [!UICONTROL **位置說明**]：SFTP 帳戶上的位置說明。

* [!UICONTROL **目錄路徑**]：SFTP 帳戶上位置的路徑。

有關 SFTP 設定的更多資訊，請參閱「[向 SFTP 伺服器發送 Data Warehouse 請求](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md)」。

### S3

您可以直接傳送倉儲資料至 Amazon S3 貯體。此目的地類型需要貯體名稱、存取金鑰 ID 和機密金鑰。 如需詳細資訊，請參閱 Amazon S3 文件中的「[Amazon S3 貯體命名規定](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html)」。

您提供來上傳 Data Warehouse 資料的使用者必須具備以下[權限](https://docs.aws.amazon.com/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html)：

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

下列 16 個標準 AWS 區域有受到支援 (必要時會使用適當的簽章演算法)：

* us-east-2
* us-east-1
* us-west-1
* us-west-2
* ap-south-1
* ap-northeast-2
* ap-southeast-1
* ap-southeast-2
* ap-northeast-1
* ca-central-1
* eu-central-1
* eu-west-1
* eu-west-2
* eu-west-3
* eu-north-1
* sa-east-1

>[!NOTE]
>
>不支援 cn-north-1 區域。

### Azure Blob

Data Warehouse 支援 Azure Blob 目標。容器、帳戶和金鑰為必填。Amazon 會自動加密閒置的資料。下載資料時，則會自動解密。如需詳細資訊，請參閱 Microsoft Azure 文件中的[建立儲存帳戶](https://docs.microsoft.com/zh-tw/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys)。

>[!NOTE]
>
>您必須實作自己的處理程序，才能管理 Data Warehouse 目標的磁碟空間。Adobe 不會從伺服器刪除任何資料。
