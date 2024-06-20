---
description: 設定雲端匯入帳戶以及可上傳分類資料的位置
keywords: Analysis Workspace
title: 設定雲端匯入和匯出帳戶
feature: Classifications
exl-id: 40d3d3f1-1047-4c37-8caf-6b0aabaa590a
source-git-commit: df9470f1870879ac91f00a021ed890bc6fb10cda
workflow-type: tm+mt
source-wordcount: '1470'
ht-degree: 54%

---

# 設定雲端匯入和匯出帳戶

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

>[!NOTE]
>
>建立和編輯帳戶時，請考量下列事項： <ul><li>系統管理員可以限制使用者建立帳戶，如中所述 [設定使用者是否可以建立帳戶](/help/components/locations/locations-manager.md#configure-whether-users-can-create-accounts). 如果您無法依照本節所述建立帳戶，請連絡您的系統管理員。</li><li>只有建立帳號的使用者或系統管理員才能編輯帳號。</li></ul>

您可以設定雲端帳戶，用於下列任何或所有用途：

* 匯出檔案，使用 [資料摘要](/help/export/analytics-data-feed/create-feed.md)
* 匯出報告，使用 [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* 使用匯入結構描述 [分類設定](/help/components/classifications/sets/overview.md)

您需要為Adobe Analytics設定存取雲端帳戶所需的必要資訊。 此程式包含依照本文所述新增及設定帳戶(例如Amazon S3角色ARN、Google Cloud Platform等)，然後依照所述新增及設定該帳戶內的位置（例如帳戶內的資料夾） [設定雲端匯入和匯出位置](/help/components/locations/configure-import-locations.md).

如需有關如何檢視和刪除現有帳戶的資訊，請參閱 [位置管理員](/help/components/locations/locations-manager.md).

若要設定雲端匯入或匯出帳戶：

1. 在Adobe Analytics中，選取 [!UICONTROL **元件**] > [!UICONTROL **位置**].
1. 在 [!UICONTROL 位置] 頁面，選取 [!UICONTROL **位置帳戶**] 標籤。
1. （視條件而定）如果您是系統管理員，則可以啟用 [!UICONTROL **檢視所有使用者的帳戶**] 檢視組織中所有使用者所建立帳號的選項。
   ![檢視所有使用者的帳戶](assets/accounts-all-users.png)
1. 若要建立新帳戶，請選取 [!UICONTROL **新增帳戶**].

   此 [!UICONTROL **位置帳戶詳細資料**] 對話方塊隨即顯示。

   或

   若要編輯現有帳戶，請找到您要編輯的帳戶，然後選取 [!UICONTROL **編輯詳細資料**] 按鈕。

   此 [!UICONTROL **新增帳戶**] 對話方塊隨即顯示。

1. 指定下列資訊： |欄位 | 函式 | ---------|----------| | [!UICONTROL **位置帳戶名稱**] | 位置帳戶的名稱。 建立位置時會顯示此名稱 | | [!UICONTROL **位置帳戶說明**] | 提供帳戶的簡短說明，以協助將其與相同帳戶型別的其他帳戶區分開來。 | | [!UICONTROL **讓您組織中的所有使用者都可以使用帳戶**] | 啟用此選項可允許組織中的其他使用者使用該帳戶。<p>共用帳戶時，請考量下列事項：</p><ul><li>您無法取消共用您共用的帳戶。</li><li>共用帳戶只能由帳戶擁有者編輯。</li><li>任何人都可以建立共用帳戶的位置。</li></ul> | | [!UICONTROL **帳戶型別**] | 選取您的雲端帳戶型別。 我們建議為每種帳戶類型設定一個帳戶，並根據需要在該帳戶內設定多個位置。<p>系統管理員可以限制使用者可以建立的帳戶型別，如中所述 [設定使用者是否可以建立帳戶](/help/components/locations/locations-manager.md#configure-whether-users-can-create-accounts). 如果您無法依照本節所述建立帳戶，請連絡您的系統管理員。</p> |
1. 在 [!UICONTROL **帳戶屬性**] 區段，指定您所選取之帳戶型別的特定資訊。

   如需設定指示，請展開以下對應至 [!UICONTROL **帳戶型別**] 您已選取的專案。 （也可使用其他舊帳戶型別，但不建議使用。）

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
   | [!UICONTROL **金鑰保存庫 URI**] | <p>Azure Key Vault 中得到 SAS 權杖的路徑。若要設定Azure SAS，您必須使用Azure金鑰儲存庫將SAS權杖儲存為秘密。 若要了解更多資訊，請參閱「[Microsoft Azure 文件有關如何從 Azure Key Vault 設定和擷取密碼](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations)」。</p><p>建立金鑰儲存庫URI後，在金鑰儲存庫上新增存取原則，以授予您建立的Azure應用程式許可權。 若要了解更多資訊，請參閱「[Microsoft Azure 文件有關如何指定 Key Vault 存取權原則](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal)」。</p> |
   | [!UICONTROL **金鑰保存庫祕密名稱**] | 將密碼新增至Azure金鑰儲存庫時建立的密碼名稱。 在Microsoft Azure中，此資訊位於您建立的金鑰儲存庫中，位於 **金鑰儲存庫** 設定頁面。 若要了解更多資訊，請參閱「[Microsoft Azure 文件有關如何從 Azure Key Vault 設定和擷取密碼](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations)」。 |
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
   >電子郵件帳戶只能用於 [資料摘要](/help/export/analytics-data-feed/create-feed.md). (電子郵件帳戶不支援 [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) 或 [分類設定](/help/components/classifications/sets/overview.md))。

   若要設定 Azure RBAC 帳戶，請註明以下資訊：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **收件者**] | 傳送報告時可以向特定使用者傳送電子郵件通知。指定單一電子郵件地址或逗號分隔的電子郵件地址清單。 |

   {style="table-layout:auto"}

+++

   **舊版帳戶型別**

   這些舊帳戶型別僅在透過匯出資料時可用 [資料摘要](/help/export/analytics-data-feed/create-feed.md) 和 [Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md). 使用匯入資料時，這些選項無法使用 [分類設定](/help/components/classifications/sets/manage/schema.md).

   +++FTP

   資料摘要資料可以傳送至Adobe或客戶託管的FTP位置。 FTP 主機、使用者名稱和密碼為必填。請使用路徑欄位將摘要檔案置入檔案夾。資料夾必須已存在；如果指定的路徑不存在，摘要會傳回錯誤。

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **Host**] | 輸入所需的FTP目的地URL。 例如，`ftp://ftp.omniture.com`。 |
   | [!UICONTROL **路徑**] | 可留空。 |
   | [!UICONTROL **使用者名稱**] | 輸入要登入FTP網站的使用者名稱。 |
   | [!UICONTROL **密碼和確認密碼**] | 輸入密碼以登入FTP站台。 |

   {style="table-layout:auto"}

+++

   +++SFTP

   SFTP 可支援資料摘要。必須填入 SFTP 主機、使用者名和目的地站點，才能包含有效的 RSA 或 DSA 公開金鑰。建立摘要時，您可以下載相關的公開金鑰。

+++

   +++S3

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

+++

   +++Azure Blob

   Data Warehouse支援Azure Blob目的地。 容器、帳戶和金鑰為必填。Amazon 會自動加密閒置的資料。下載資料時，則會自動解密。如需詳細資訊，請參閱 Microsoft Azure 文件中的[建立儲存帳戶](https://docs.microsoft.com/zh-tw/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys)。

   >[!NOTE]
   >
   >您必須實作自己的處理程序，才能管理 Data Warehouse 目標的磁碟空間。Adobe 不會從伺服器刪除任何資料。

+++

1. 選取「[!UICONTROL **儲存**]」。

1. 繼續使用 [設定雲端匯入和匯出位置](/help/components/locations/configure-import-locations.md).
