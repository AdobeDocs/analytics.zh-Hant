---
description: 說明如何建立 Data Warehouse 請求的步驟。
title: 設定Data Warehouse請求的報表目的地
feature: Data Warehouse
exl-id: 3c7faea3-4d90-4274-88f3-e9337c94155f
source-git-commit: 7edee01a5a5399762f10037cf920863af35cc4d7
workflow-type: tm+mt
source-wordcount: '2235'
ht-degree: 10%

---

# 設定Data Warehouse請求的報表目的地

建立Data Warehouse請求時，有多種可用的設定選項。 以下資訊說明如何設定請求的報表目的地。

如需有關如何開始建立請求的資訊，以及其他重要組態選項的連結，請參閱 [建立Data Warehouse請求](/help/export/data-warehouse/create-request/t-dw-create-request.md).

>[!NOTE]
>
>設定報表目的地時，請考量下列事項：
>
>* 我們建議您使用雲端帳戶或電子郵件作為報表目的地。 可以使用舊版FTP和SFTP帳戶，但不建議使用。
>
>* Data Warehouse請求與您的Adobe Analytics使用者帳戶相關聯。 依預設，其他使用者無法使用或檢視您設定的請求。 您可以啟用「 」以讓組織中的其他使用者可以使用Data Warehouse請求 **顯示所有目的地** 切換，如所述 [Data Warehouse請求一般設定](/help/export/data-warehouse/create-request/dw-general-settings.md).
>
>* 您之前的任何雲端帳戶 [已為資料摘要設定](/help/export/analytics-data-feed/create-feed.md) 可用於Data Warehouse。
>
>* 為設定的雲端帳戶 [匯入Adobe Analytics分類資料](/help/components/locations/locations-manager.md) 設定報表目的地時，可以使用來自雲端目的地的流量。 不過，任何設定為匯入分類資料的位置都無法使用。

若要設定Data Warehouse報表的傳送目的地：

1. 透過選取「 」，開始在Adobe Analytics中建立請求 **[!UICONTROL 工具]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **新增**].

   如需其他詳細資訊，請參閱 [建立Data Warehouse請求](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. 在新Data Warehouse請求頁面上，選取 [!UICONTROL **報表目的地**] 標籤。

   ![報表目的地索引標籤](assets/dw-report-destination.png)

1. （視條件而定）如果已設定帳戶（以及該帳戶上的目的地），而您想要將其用作報表目的地：

   1. （選擇性）如果您是系統管理員， [!UICONTROL **顯示所有目的地**] 選項可供使用。 如果您想要存取組織中任何使用者建立的所有帳戶和位置，請啟用此選項。

   1. 從中選擇帳戶 [!UICONTROL **選取帳戶**] 下拉式功能表。

      您設定的任何雲端帳戶 [匯入Adobe Analytics分類資料](/help/components/locations/locations-manager.md) 來自雲端目的地的資訊會顯示在這裡，且可供使用。 不過，任何設定為匯入分類資料的位置都無法使用。 請改為新增新的目的地，如下所述。

   1. 從中選擇與帳戶關聯的目的地 [!UICONTROL **選取目的地**] 下拉式功能表。 <!-- Is this correct? -->

1. （視條件而定）如果您先前未設定帳戶：

   1. 選取 [!UICONTROL **新增帳戶**]，然後指定下列資訊：

      | 欄位 | 函數 |
      |---------|----------|
      | [!UICONTROL **帳戶型別**] | 選取您的雲端帳戶型別。 我們建議為每種帳戶型別設定單一帳戶，並視需要在該帳戶內設立多個位置。 <p>選擇帳戶型別後，該帳戶型別的特定欄位會顯示出來。 </p> |
      | [!UICONTROL **帳戶名稱**] | 指定帳戶的名稱。 建立位置時會顯示此名稱。 <!-- true? --> |
      | [!UICONTROL **帳戶說明**] | 提供帳戶的簡短說明，以協助將其與相同帳戶型別的其他帳戶區分開來。 |

      如需設定指示，請展開以下對應至 [!UICONTROL **帳戶型別**] 您已選取的專案。

      設定報表目的地時，請使用下列任一帳戶型別。 如需設定指示，請展開帳戶型別。 (其他 [舊版目的地](#legacy-destinations) 也可使用，但不建議使用。)

      +++Amazon S3

      指定下列資訊以設定Amazon S3角色ARN帳戶：

      | 欄位 | 函數 |
      |---------|----------|
      | [!UICONTROL **角色ARN**] | 您必須提供角色ARN (Amazon資源名稱)，Adobe才能使用該角色來存取Amazon S3帳戶。 若要這麼做，請建立來源帳戶的IAM許可權原則、將原則附加至使用者，然後建立目的地帳戶的角色。 如需特定資訊，請參閱 [此AWS檔案](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/).<p>如需如何設定貯體許可權的相關資訊，請參閱文章 [如何為Amazon S3貯體中的物件提供跨帳戶存取權？](https://repost.aws/knowledge-center/cross-account-access-s3) 在Amazon知識中心。 |
      | [!UICONTROL **使用者ARN**] | 使用者ARN (Amazon資源名稱)由Adobe提供。 您必須將此使用者附加至您建立的原則。 |

      {style="table-layout:auto"}

+++

      +++Google雲端平台

      指定下列資訊以設定Google Cloud Platform帳戶：

      | 欄位 | 函數 |
      |---------|----------|
      | [!UICONTROL **專案 ID**] | 您的Google雲端專案ID。 請參閱 [有關取得專案ID的Google Cloud檔案](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

      {style="table-layout:auto"}

+++

      +++Azure SAS

      指定下列資訊以設定Azure SAS帳戶：

      | 欄位 | 函數 |
      |---------|----------|
      | [!UICONTROL **應用程式ID**] | 從您建立的Azure應用程式複製此ID。 在Microsoft Azure中，此資訊位於 **概觀** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **租使用者ID**] | 從您建立的Azure應用程式複製此ID。 在Microsoft Azure中，此資訊位於 **概觀** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **金鑰儲存庫URI**] | <p>Azure金鑰儲存庫中SAS權杖的路徑。  若要設定Azure SAS，您需要使用Azure金鑰儲存庫將SAS權杖儲存為秘密。 如需詳細資訊，請參閱 [有關如何從Azure金鑰儲存庫設定和擷取密碼的Microsoft Azure檔案](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>建立金鑰儲存庫URI後，在金鑰儲存庫上新增存取原則，以授予您建立的Azure應用程式許可權。 如需詳細資訊，請參閱 [有關如何指派金鑰儲存庫存取原則的Microsoft Azure檔案](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
      | [!UICONTROL **金鑰儲存庫秘密名稱**] | 將密碼新增至Azure金鑰儲存庫時建立的密碼名稱。 在Microsoft Azure中，此資訊位於您建立的金鑰儲存庫中，位於 **金鑰儲存庫** 設定頁面。 如需詳細資訊，請參閱 [有關如何從Azure金鑰儲存庫設定和擷取密碼的Microsoft Azure檔案](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
      | [!UICONTROL **密碼**] | 從您建立的Azure應用程式複製密碼。 在Microsoft Azure中，此資訊位於 **憑證和密碼** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      指定下列資訊以設定Azure RBAC帳戶：

      | 欄位 | 函數 |
      |---------|----------|
      | [!UICONTROL **應用程式ID**] | 從您建立的Azure應用程式複製此ID。 在Microsoft Azure中，此資訊位於 **概觀** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **租使用者ID**] | 從您建立的Azure應用程式複製此ID。 在Microsoft Azure中，此資訊位於 **概觀** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **密碼**] | 從您建立的Azure應用程式複製密碼。 在Microsoft Azure中，此資訊位於 **憑證和密碼** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++電子郵件

      指定下列資訊以設定電子郵件帳戶：

      | 欄位 | 函數 |
      |---------|----------|
      | [!UICONTROL **收件者**] | 可在傳送報告時傳送電子郵件通知給特定使用者。 指定單一電子郵件地址或以逗號分隔的電子郵件地址清單。 <!-- How does this differ from the Notification email tab? --> |

   1. 選取 [!UICONTROL **新增位置**]，然後指定下列資訊： |欄位 | 函式 | ---------|----------| | [!UICONTROL **名稱**] | 位置的名稱。  | | [!UICONTROL **說明**] | 提供帳戶的簡短說明，以協助將其與相同帳戶型別的其他帳戶區分開來。 | | [!UICONTROL **位置帳戶**] | 選取您在中建立的位置帳戶 [新增帳戶](#add-an-account). |

   1. 在 [!UICONTROL **位置屬性**] 區段，指定您位置帳戶之帳戶型別的專屬資訊。

      如需設定指示，請展開以下對應至 [!UICONTROL **帳戶型別**] 您先前選取的專案。

      +++Amazon S3

      指定下列資訊以設定Amazon S3位置：

      | 欄位 | 函數 |
      |---------|----------|
      | [!UICONTROL **貯體名稱**] | 您想要將Adobe Analytics資料傳送至的Amazon S3帳戶中的貯體。 確保Adobe提供的使用者ARN有權將檔案上傳到此貯體。 |
      | [!UICONTROL **金鑰前置詞**] | 要放置資料之儲存貯體中的資料夾。 指定資料夾名稱，然後在名稱后面加上反斜線以建立資料夾。 例如， folder_name/ |

      {style="table-layout:auto"}

+++

      +++Google雲端平台

      指定下列資訊來設定Google Cloud平台位置：

      | 欄位 | 函數 |
      |---------|----------|
      | [!UICONTROL **貯體名稱**] | 您想要將Adobe Analytics資料傳送至的GCP帳戶中的貯體。 確保您已授予Adobe所提供之主體的許可權，可將檔案上傳至此儲存貯體。 如需授與許可權的詳細資訊，請參閱 [將主體新增至貯體層級原則](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) (位於Google Cloud檔案中)。 |
      | [!UICONTROL **金鑰前置詞**] | 要放置資料之儲存貯體中的資料夾。 指定資料夾名稱，然後在名稱后面加上反斜線以建立資料夾。 例如， folder_name/ |

      {style="table-layout:auto"}

+++

      +++Azure SAS

      指定下列資訊以設定Azure SAS位置：

      | 欄位 | 函數 |
      |---------|----------|
      | [!UICONTROL **容器名稱**] | 您指定要將Adobe Analytics資料傳送至何處的帳戶中的容器。 |
      | [!UICONTROL **金鑰前置詞**] | 容器內您要放置資料的資料夾。 指定資料夾名稱，然後在名稱后面加上反斜線以建立資料夾。 例如， `folder_name/` |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      指定下列資訊以設定Azure RBAC位置：

      | 欄位 | 函數 |
      |---------|----------|
      | [!UICONTROL **容器名稱**] | 您指定要將Adobe Analytics資料傳送至何處的帳戶中的容器。 請確定您授與許可權，可以將檔案上傳至您先前建立的Azure應用程式。 |
      | [!UICONTROL **金鑰前置詞**] | 容器內您要放置資料的資料夾。 指定資料夾名稱，然後在名稱后面加上反斜線以建立資料夾。 例如， `folder_name/` |
      | [!UICONTROL **帳戶名稱**] | Azure儲存體帳戶。 |

      {style="table-layout:auto"}

+++

   1. 選取&#x200B;[!UICONTROL **「儲存」**]。

      您現在可以將資料匯入至您設定的帳戶和位置。

1. 繼續在「 」上設定您的Data Warehouse請求 [!UICONTROL **報表選項**] 標籤。 如需詳細資訊，請參閱 [設定Data Warehouse請求的報表選項](/help/export/data-warehouse/create-request/dw-request-report-options.md).

## 舊版目的地

>[!IMPORTANT]
>
>本節所述的目的地為舊版，不建議使用。 建立資料倉儲目的地時，請改用下列其中一種目的地： Amazon S3、Google Cloud Platform、Azure RBAC、Azure SAS或電子郵件。 如需上述各個建議目的地的詳細資訊，請參閱上述資訊。

下列資訊提供每個舊版目的地的設定資訊：

### FTP

Data Warehouse資料可以傳送至Adobe或客戶託管的FTP位置。 FTP 主機、使用者名稱和密碼為必填。請使用路徑欄位將摘要檔案置入檔案夾。資料夾必須已存在；如果指定的路徑不存在，摘要會傳回錯誤。

完成可用欄位時，請使用下列資訊：

#### 帳戶欄位

* [!UICONTROL **帳戶名稱**]：FTP帳戶的名稱。

* [!UICONTROL **帳戶說明**]：FTP帳戶的說明。

* [!UICONTROL **主機名稱**]：輸入所需的FTP目的地URL。 例如，`ftp.company.com`。

  >[!NOTE]
  >
  >  不包括 `ftp://` 在URL開頭。

* [!UICONTROL **使用者名稱**]：輸入使用者名稱以登入FTP站台。

* [!UICONTROL **密碼和確認密碼**]：輸入密碼以登入FTP站台。

#### 位置欄位

* [!UICONTROL **位置名稱**]：您想要傳送檔案的FTP帳戶位置名稱。

* [!UICONTROL **位置說明**]：FTP帳戶上位置的說明。

* [!UICONTROL **目錄路徑**]：FTP帳戶上位置的路徑。

### SFTP

SFTP可支援Data Warehouse。 必須填入 SFTP 主機、使用者名和目的地站點，才能包含有效的 RSA 或 DSA 公開金鑰。建立Data Warehouse目的地時，您可以下載適當的公開金鑰。

完成可用欄位時，請使用下列資訊：

#### 帳戶欄位

* [!UICONTROL **帳戶名稱**]：FTP帳戶的名稱。

* [!UICONTROL **帳戶說明**]：FTP帳戶的說明。

* [!UICONTROL **主機名稱**]：輸入所需的SFTP目的地URL。 例如，`sftp.company.com`。

  >[!NOTE]
  >
  >  不包括 `sftp://` 在URL開頭。

* [!UICONTROL **使用者名稱**]：輸入使用者名稱以登入SFTP網站。

* [!UICONTROL **上傳時使用暫存副檔名**]：啟用時， `.part` 會在上傳程式期間使用副檔名。 此選項請保持啟用，除非您的SFTP伺服器限制在上傳完成之後變更的檔案名稱。

* [!UICONTROL **公開金鑰**]：建立Data Warehouse目的地時，請下載適當的公開金鑰。

#### 位置欄位

* [!UICONTROL **位置名稱**]：您要傳送檔案的SFTP帳戶位置名稱。

* [!UICONTROL **位置說明**]：SFTP帳戶上位置的說明。

* [!UICONTROL **目錄路徑**]：SFTP帳戶上位置的路徑。

如需SFTP設定的詳細資訊，請參閱 [傳送Data Warehouse請求至SFTP伺服器](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md).

### S3

您可以直接將倉儲資料傳送至Amazon S3貯體。 此目的地類型需要貯體名稱、存取金鑰 ID 和機密金鑰。 如需詳細資訊，請參閱 Amazon S3 文件中的 [Amazon S3 貯體命名規定](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html)。

您提供來上傳Data Warehouse資料的使用者必須具備下列條件 [許可權](https://docs.aws.amazon.com/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html)：

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

Data Warehouse支援Azure Blob目的地。 容器、帳戶和金鑰為必填。Amazon 會自動加密閒置的資料。下載資料時，則會自動解密。如需詳細資訊，請參閱 Microsoft Azure 文件中的[建立儲存帳戶](https://docs.microsoft.com/zh-tw/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys)。

>[!NOTE]
>
>您必須實作自己的處理程式，才能管理Data Warehouse目的地的磁碟空間。 Adobe 不會從伺服器刪除任何資料。
