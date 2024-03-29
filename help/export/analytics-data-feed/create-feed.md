---
title: 建立資料摘要
description: 瞭解如何建立資料摘要。
feature: Data Feeds
exl-id: 36c8a40e-6137-4836-9d4b-bebf17b932bc
source-git-commit: 9fbe0f8a7933e5ff047a270523ea53d9489b223c
workflow-type: tm+mt
source-wordcount: '3348'
ht-degree: 16%

---

# 建立資料摘要

建立資料摘要時，您會為Adobe提供：

* 有關您要將原始資料檔案傳送到的目的地的資訊

* 您要包含在每個檔案中的資料

>[!NOTE]
>
>建立資料摘要之前，請務必瞭解資料摘要的基本資訊，並確保您符合所有必要的先決條件。 如需詳細資訊，請參閱 [資料摘要概觀](data-feed-overview.md).

## 建立及設定資料摘要

1. 使用您的 Adobe ID 認證登入 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
1. 選取右上角的9個方塊圖示，然後選取「 」 [!UICONTROL **Analytics**].
1. 在頂端導覽列中，前往 [!UICONTROL **管理員**] > [!UICONTROL **資料摘要**].
1. 選取 [!UICONTROL **新增**].

   ![新增資料摘要](assets/datafeed-add.png)

   此時會顯示一個頁面，其中包含三個主要類別： [!UICONTROL **摘要資訊**]， [!UICONTROL **目的地**]、和 [!UICONTROL **資料欄定義**].
1. 在 [!UICONTROL **摘要資訊**] 區段，填入下列欄位：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **名稱**] | 資料摘要的名稱。 在選取的報表套裝內不可重複，長度上限為 255 個字元。 |
   | [!UICONTROL **報告套裝**] | 資料摘要所在的報告套裝。 如果相同報表套裝中建立了多個資料摘要，它們必須各有不同的欄定義。只有來源報表套裝支援資料摘要，虛擬報表套裝並不受支援。 |
   | [!UICONTROL **完成時收到電子郵件**] | 摘要完成處理時要通知的電子郵件地址。 電子郵件地址的格式必須正確。 |
   | [!UICONTROL **摘要間隔**] | 選取 **每日** 用於回填或歷史資料。 每日摘要則包含一整天的資料，從報表套裝時區的午夜到午夜。  選取 **每小時** 持續性資料（如有需要，也可使用「每日」持續性摘要）。 每小時摘要包含一個小時的資料量， |
   | [!UICONTROL **延遲處理**] | 在處理資料摘要檔案之前，請等候一段特定時間。 延遲的作用在於，在行動裝置實作中讓離線裝置得以上線並傳送資料。在管理舊的已處理檔案時，它也可用於容納組織的伺服器端處理程序。多數情況下延遲並不會發生。摘要最多可延遲 120 分鐘。 |
   | [!UICONTROL **開始和結束日期**] | 開始日期指的是您想要資料摘要開始的日期。 若要立即開始處理歷史資料的資料摘要，請將此日期設為收集資料時的過去任何日期。 開始和結束日期取決於報表套裝的時區。 |
   | [!UICONTROL **連續摘要**] | 此核取方塊會移除結束日期，使摘要無限期進行處理。 當摘要完成處理歷史資料後，就會等待資料完成指定小時或當天的資料收集。一旦當前的小時或當天結束，處理程序就會在指定的延遲後開始。 |

1. 在 [!UICONTROL **目的地**] 區段，在 [!UICONTROL **型別**] 下拉式功能表，選取您要傳送資料的目的地。

   >[!NOTE]
   >
   >設定報表目的地時，請考量下列事項：
   >
   >* 我們建議將雲端帳戶用於您的報表目的地。 [舊版FTP和SFTP帳戶](#legacy-destinations) 可使用，但不建議使用。
   >
   >* 雲端帳戶與您的Adobe Analytics使用者帳戶相關聯。 其他使用者無法使用或檢視您設定的雲端帳戶。
   >

   ![資料摘要目的地下拉式功能表](assets/datafeed-destinations-dropdown.png)

   建立資料摘要時，請使用下列任一目的地型別。 如需設定指示，請展開目的地型別。 (其他 [舊版目的地](#legacy-destinations) 也可使用，但不建議使用。)

   +++Amazon S3

   您可以直接傳送摘要至 Amazon S3 貯體。此目的地型別只需要您的Amazon S3帳戶和位置（貯體）。

   Adobe Analytics使用跨帳戶驗證，將檔案從Adobe Analytics上傳至Amazon S3執行個體中的指定位置。

   若要設定Amazon S3貯體作為資料摘要的目的地：

   1. 在Adobe Analytics Admin Console的 [!UICONTROL **目的地**] 區段，選取 [!UICONTROL **Amazon S3**].

      ![Amazon S3目的地](assets/datafeed-destination-amazons3.png)

   1. 選取 [!UICONTROL **選取位置**].

      此時會顯示「Amazon S3匯出位置」頁面。

   1. （視條件而定）如果您先前已新增Amazon S3帳戶和位置：

      1. 從中選擇帳戶 [!UICONTROL **選取帳戶**] 下拉式功能表。

      1. 從中選擇位置 [!UICONTROL **選取位置**] 下拉式功能表。

      1. 選取 [!UICONTROL **儲存**] > [!UICONTROL **儲存**].

         目的地現在已設定為傳送資料至您指定的Amazon S3位置。

   1. （視條件而定）如果您先前未新增Amazon S3帳戶：

      1. 選取 [!UICONTROL **新增帳戶**]，然後指定下列資訊：

         | 欄位 | 函數 |
         |---------|----------|
         | [!UICONTROL **帳戶名稱**] | 帳戶的名稱。 這可以是您選擇的任何名稱。 |
         | [!UICONTROL **帳戶說明**] | 帳戶說明。 |
         | [!UICONTROL **角色ARN**] | 您必須提供角色ARN (Amazon資源名稱)，Adobe才能使用該角色來存取Amazon S3帳戶。 若要這麼做，請建立來源帳戶的IAM許可權原則、將原則附加至使用者，然後建立目的地帳戶的角色。 如需特定資訊，請參閱 [此AWS檔案](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
         | [!UICONTROL **使用者ARN**] | 使用者ARN (Amazon資源名稱)由Adobe提供。 您必須將此使用者附加至您建立的原則。 |

         {style="table-layout:auto"}

      1. 選取 [!UICONTROL **新增位置**]，然後指定下列資訊：

         | 欄位 | 函數 |
         |---------|----------|
         | [!UICONTROL **名稱**] | 帳戶的名稱。 |
         | [!UICONTROL **說明**] | 帳戶說明。 |
         | [!UICONTROL **貯體**] | 您想要將Adobe Analytics資料傳送至的Amazon S3帳戶中的貯體。 <p>請確定Adobe提供的使用者ARN具有 `S3:PutObject` 許可權可將檔案上傳至此貯體。 此許可權可讓使用者ARN上傳初始檔案並覆寫後續上傳的檔案。</p> |
         | [!UICONTROL **前置詞**] | 要放置資料之儲存貯體中的資料夾。 指定資料夾名稱，然後在名稱后面加上反斜線以建立資料夾。 例如， `folder_name/` |

         {style="table-layout:auto"}

      1. 選取 [!UICONTROL **建立**] > [!UICONTROL **儲存**].

         目的地現在已設定為傳送資料至您指定的Amazon S3位置。

+++

   +++Azure RBAC

   您可以使用RBAC驗證直接傳送摘要至Azure容器。 此目的地型別需要應用程式ID、租使用者ID和密碼。

   若要設定Azure RBAC帳戶作為資料摘要的目的地：

   1. 如果您尚未建立可供Adobe Analytics用於驗證的Azure應用程式，然後授與存取控制(IAM)的存取許可權。

      如需詳細資訊，請參閱 [有關如何建立Azure Active Directory應用程式的Microsoft Azure檔案](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. 在Adobe Analytics Admin Console的 [!UICONTROL **目的地**] 區段，選取 [!UICONTROL **Azure RBAC**].

      ![Azure RBAC目的地](assets/datafeed-destination-azurerbac.png)

   1. 選取 [!UICONTROL **選取位置**].

      將會顯示「Azure RBAC匯出位置」頁面。

   1. （視條件而定）如果您先前已新增Azure RBAC帳戶和位置：

      1. 從中選擇帳戶 [!UICONTROL **選取帳戶**] 下拉式功能表。

      1. 從中選擇位置 [!UICONTROL **選取位置**] 下拉式功能表。

      1. 選取 [!UICONTROL **儲存**] > [!UICONTROL **儲存**].

         目的地現在已設定為傳送資料至您指定的Azure RBAC位置。

   1. （視條件而定）如果您先前未新增Azure RBAC帳戶：

      1. 選取 [!UICONTROL **新增帳戶**]，然後指定下列資訊：

         | 欄位 | 函數 |
         |---------|----------|
         | [!UICONTROL **帳戶名稱**] | Azure RBAC帳戶的名稱。 此名稱會顯示在 [!UICONTROL **選取帳戶**] 下拉式欄位，並可是您選擇的任何名稱。 |
         | [!UICONTROL **帳戶說明**] | Azure RBAC帳戶的說明。 此說明會顯示在 [!UICONTROL **選取帳戶**] 下拉式欄位，並可是您選擇的任何名稱。 |
         | [!UICONTROL **應用程式ID**] | 從您建立的Azure應用程式複製此ID。 在Microsoft Azure中，此資訊位於 **概觀** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **租使用者ID**] | 從您建立的Azure應用程式複製此ID。 在Microsoft Azure中，此資訊位於 **概觀** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **密碼**] | 從您建立的Azure應用程式複製密碼。 在Microsoft Azure中，此資訊位於 **憑證和密碼** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. 選取 [!UICONTROL **新增位置**]，然後指定下列資訊：

         | 欄位 | 函數 |
         |---------|----------|
         | [!UICONTROL **名稱**] | 位置的名稱。 此名稱會顯示在 [!UICONTROL **選取位置**] 下拉式欄位，並可是您選擇的任何名稱。 |
         | [!UICONTROL **說明**] | 位置的說明。 此說明會顯示在 [!UICONTROL **選取位置**] 下拉式欄位，並可是您選擇的任何名稱。 |
         | [!UICONTROL **帳戶**] | Azure儲存體帳戶。 |
         | [!UICONTROL **容器**] | 您指定要將Adobe Analytics資料傳送至何處的帳戶中的容器。 請確定您授與許可權，可以將檔案上傳至您先前建立的Azure應用程式。 |
         | [!UICONTROL **前置詞**] | 容器內您要放置資料的資料夾。 指定資料夾名稱，然後在名稱后面加上反斜線以建立資料夾。 例如， `folder_name/`<p>請確定您在設定Azure RBAC帳戶時指定的應用程式ID已被授予 `Storage Blob Data Contributor` 角色以存取容器（資料夾）。</p> <p>如需詳細資訊，請參閱 [Azure內建角色](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p> |

         {style="table-layout:auto"}

      1. 選取 [!UICONTROL **建立**] > [!UICONTROL **儲存**].

         目的地現在已設定為傳送資料至您指定的Azure RBAC位置。

+++

   +++Azure SAS

   您可以使用SAS驗證直接將摘要傳送到Azure容器。 此目的地型別需要應用程式ID、租使用者ID、金鑰儲存庫URI、金鑰儲存庫機密名稱和機密。

   若要將Azure SAS設定為資料摘要的目的地：

   1. 如果您尚未建立應用程式，請建立Adobe Analytics可用於驗證的Azure應用程式。

      如需詳細資訊，請參閱 [有關如何建立Azure Active Directory應用程式的Microsoft Azure檔案](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. 在Adobe Analytics Admin Console的 [!UICONTROL **目的地**] 區段，選取 [!UICONTROL **Azure SAS**].

      ![Azure SAS目的地](assets/datafeed-destination-azuresas.png)

   1. 選取 [!UICONTROL **選取位置**].

      此時會顯示「Azure SAS匯出位置」頁面。

   1. （視條件而定）如果您先前已新增Azure SAS帳戶和位置：

      1. 從中選擇帳戶 [!UICONTROL **選取帳戶**] 下拉式功能表。

      1. 從中選擇位置 [!UICONTROL **選取位置**] 下拉式功能表。

      1. 選取 [!UICONTROL **儲存**] > [!UICONTROL **儲存**].

         目的地現在已設定為傳送資料至您指定的Azure SAS位置。

   1. （視條件而定）如果您先前未新增Azure SAS帳戶：

      1. 選取 [!UICONTROL **新增帳戶**]，然後指定下列資訊：

         | 欄位 | 函數 |
         |---------|----------|
         | [!UICONTROL **帳戶名稱**] | Azure SAS帳戶的名稱。 此名稱會顯示在 [!UICONTROL **選取帳戶**] 下拉式欄位，並可是您選擇的任何名稱。 |
         | [!UICONTROL **帳戶說明**] | Azure SAS帳戶的說明。 此說明會顯示在 [!UICONTROL **選取帳戶**] 下拉式欄位，並可是您選擇的任何名稱。 |
         | [!UICONTROL **應用程式ID**] | 從您建立的Azure應用程式複製此ID。 在Microsoft Azure中，此資訊位於 **概觀** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **租使用者ID**] | 從您建立的Azure應用程式複製此ID。 在Microsoft Azure中，此資訊位於 **概觀** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **金鑰儲存庫URI**] | <p>Azure金鑰儲存庫中SAS權杖的路徑。  若要設定Azure SAS，您需要使用Azure金鑰儲存庫將SAS權杖儲存為秘密。 如需詳細資訊，請參閱 [有關如何從Azure金鑰儲存庫設定和擷取密碼的Microsoft Azure檔案](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>建立金鑰儲存庫URI之後：<ul><li>在金鑰儲存庫上新增存取原則，以授予您建立的Azure應用程式許可權。</li><li>請確定應用程式ID已獲授與 `Key Vault Certificate User` 內建角色，以存取金鑰儲存庫URI。</br><p>如需詳細資訊，請參閱 [Azure內建角色](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p></li></ul><p>如需詳細資訊，請參閱 [有關如何指派金鑰儲存庫存取原則的Microsoft Azure檔案](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
         | [!UICONTROL **金鑰儲存庫秘密名稱**] | 將密碼新增至Azure金鑰儲存庫時建立的密碼名稱。 在Microsoft Azure中，此資訊位於您建立的金鑰儲存庫中，位於 **金鑰儲存庫** 設定頁面。 如需詳細資訊，請參閱 [有關如何從Azure金鑰儲存庫設定和擷取密碼的Microsoft Azure檔案](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
         | [!UICONTROL **密碼**] | 從您建立的Azure應用程式複製密碼。 在Microsoft Azure中，此資訊位於 **憑證和密碼** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. 選取 [!UICONTROL **新增位置**]，然後指定下列資訊：

         | 欄位 | 函數 |
         |---------|----------|
         | [!UICONTROL **名稱**] | 位置的名稱。 此名稱會顯示在 [!UICONTROL **選取位置**] 下拉式欄位，並可是您選擇的任何名稱。 |
         | [!UICONTROL **說明**] | 位置的說明。 此說明會顯示在 [!UICONTROL **選取位置**] 下拉式欄位，並可是您選擇的任何名稱。 |
         | [!UICONTROL **容器**] | 您指定要將Adobe Analytics資料傳送至何處的帳戶中的容器。 |
         | [!UICONTROL **前置詞**] | 容器內您要放置資料的資料夾。 指定資料夾名稱，然後在名稱后面加上反斜線以建立資料夾。 例如， `folder_name/`<p>設定Azure SAS帳戶時，請確定您在「金鑰儲存庫機密名稱」欄位中指定的SAS權杖存放區具有 `Write` 許可權。 這可讓SAS權杖在您的Azure容器中建立檔案。 <p>如果您也希望SAS權杖覆寫檔案，請確定SAS權杖存放區具有 `Delete` 許可權。</p><p>如需詳細資訊，請參閱 [Blob儲存資源](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources) Azure Blob儲存檔案。</p> |

         {style="table-layout:auto"}

      1. 選取 [!UICONTROL **建立**] > [!UICONTROL **儲存**].

         目的地現在已設定為傳送資料至您指定的Azure SAS位置。

+++

   +++Google雲端平台

   您可以直接將摘要傳送至Google Cloud Platform (GCP)貯體。 此目的地型別只需要您的GCP帳戶名稱與地點（貯體）名稱。

   Adobe Analytics使用跨帳戶驗證，將檔案從Adobe Analytics上傳至GCP執行個體中的指定位置。

   若要將GCP貯體設定為資料摘要的目的地：

   1. 在Adobe Analytics Admin Console的 [!UICONTROL **目的地**] 區段，選取 [!UICONTROL **Google Cloud平台**].

      ![Google Cloud Platform目的地](assets/datafeed-destination-gcp.png)

   1. 選取 [!UICONTROL **選取位置**].

      此時會顯示「GCP匯出位置」頁面。

   1. （視條件而定）如果您先前已新增GCP帳戶和位置：

      1. 從中選擇帳戶 [!UICONTROL **選取帳戶**] 下拉式功能表。

      1. 從中選擇位置 [!UICONTROL **選取位置**] 下拉式功能表。

      1. 選取 [!UICONTROL **儲存**] > [!UICONTROL **儲存**].

         目的地現在已設定為傳送資料至您指定的GCP位置。

   1. （視條件而定）如果您先前未新增GCP帳戶：

      1. 選取 [!UICONTROL **新增帳戶**]，然後指定下列資訊：

         | 欄位 | 函數 |
         |---------|----------|
         | [!UICONTROL **帳戶名稱**] | 帳戶的名稱。 這可以是您選擇的任何名稱。 |
         | [!UICONTROL **帳戶說明**] | 帳戶說明。 |
         | [!UICONTROL **專案 ID**] | 您的Google雲端專案ID。 請參閱 [有關取得專案ID的Google Cloud檔案](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

         {style="table-layout:auto"}

      1. 選取 [!UICONTROL **新增位置**]，然後指定下列資訊：

         | 欄位 | 函數 |
         |---------|----------|
         | [!UICONTROL **主體**] | 主體由Adobe提供。 您必須授予許可權才能接收此主體的摘要。 |
         | [!UICONTROL **名稱**] | 帳戶的名稱。 |
         | [!UICONTROL **說明**] | 帳戶說明。 |
         | [!UICONTROL **貯體**] | 您想要將Adobe Analytics資料傳送至的GCP帳戶中的貯體。 <p>確保您已授予Adobe提供的主體下列任一許可權：<ul><li>`roles/storage.objectCreator`：如果您想要將主體限製為僅在GCP帳戶中建立檔案，請使用此許可權。 </br>**重要：** 如果您將此許可權用於排程報告，則對於每個新的排程匯出都必須使用唯一的檔案名稱。 否則，報告產生將失敗，因為主體無權覆寫現有檔案。</li><li>（建議） `roles/storage.objectUser`：如果您希望主參與者有權檢視、列出、更新及刪除GCP帳戶中的檔案，請使用此許可權。</br>此許可權可讓主體覆寫現有檔案以供後續上傳，而不需要為每個新的排程匯出自動產生唯一的檔案名稱。</li></ul><p>如需授與許可權的詳細資訊，請參閱 [將主體新增至貯體層級原則](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) (位於Google Cloud檔案中)。</p> |
         | [!UICONTROL **前置詞**] | 要放置資料之儲存貯體中的資料夾。 指定資料夾名稱，然後在名稱后面加上反斜線以建立資料夾。 例如， `folder_name/` |

         {style="table-layout:auto"}

      1. 選取 [!UICONTROL **建立**] > [!UICONTROL **儲存**].

         目的地現在已設定為傳送資料至您指定的GCP位置。

+++

1. 在  [!UICONTROL **資料欄定義**] 部分，選取最新的 [!UICONTROL **所有Adobe Columns**] 範本，然後填入下列欄位：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **移除逸出字元**] | 在收集資料時，有些字元（例如新的行）可能會造成問題。 如果您想要從摘要檔案中移除這些字元，請勾選此方塊。 |
   | [!UICONTROL **壓縮格式**] | 使用的壓縮型別。 **Gzip** 輸出檔案 `.tar.gz` 格式。 **Zip** 輸出檔案 `.zip` 格式。 |
   | [!UICONTROL **封裝型別**] | 選取 **多個檔案** 用於大多數的資料摘要。 此選項會將您的資料分頁為未壓縮的2GB區塊。 （如果選取了多個檔案，且報表回溯期的未壓縮資料少於2GB，則會傳送一個檔案。） 選取 **單一檔案** 輸出 `hit_data.tsv` 在單一的、可能為大型的檔案中。 |
   | [!UICONTROL **資訊清單**] | Adobe是否應該傳遞 [資訊清單檔案](c-df-contents/datafeeds-contents.md#feed-manifest) 在摘要間隔內未收集到資料時到達目的地。 如果您選取 **資訊清單檔案**，您會在未收集資料時收到類似下列的資訊清單檔案：<p>`text`</p><p>`Datafeed-Manifest-Version: 1.0`</p><p>`Lookup-Files: 0`</p><p>`Data-Files: 0`</p><p> `Total-Records: 0`</p> |
   | [!UICONTROL **欄範本**] | 建立許多資料摘要時，Adobe建議建立欄範本。 選取欄範本就會自動在範本中加入指定的欄。Adobe 也提供數個預設範本。 |
   | [!UICONTROL **可用欄**] | Adobe Analytics中所有可用的資料欄。 按一下[!UICONTROL 全部新增]，將所有欄加入資料摘要中。 |
   | [!UICONTROL **包含的欄**] | 要包含在資料摘要中的欄。 按一下[!UICONTROL 全部移除]，從資料摘要中移除所有欄。 |
   | [!UICONTROL **下載 CSV**] | 下載包含所有已包含欄的CSV檔案。 |

1. 選取 [!UICONTROL **儲存**] 位於右上方。

   歷史資料處理會立即開始。 當資料完成一天量的處理作業時，檔案會傳送至您設定的目的地。

   如需如何存取資料摘要及如何深入瞭解其內容的詳細資訊，請參閱 [資料摘要內容 — 概觀](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md).

## 舊版目的地

>[!IMPORTANT]
>
>本節所述的目的地為舊版，不建議使用。 在建立資料摘要時，請使用下列其中一個目的地： Amazon S3、Google Cloud Platform、Azure RBAC或Azure SAS。 另請參閱 [建立及設定資料摘要](#create-and-configure-a-data-feed) 以取得每一個建議目的地的詳細資訊。


下列資訊提供每個舊版目的地的設定資訊：

### FTP

資料摘要資料可以傳送至Adobe或客戶託管的FTP位置。 FTP 主機、使用者名稱和密碼為必填。請使用路徑欄位將摘要檔案置入檔案夾。資料夾必須已存在；如果指定的路徑不存在，摘要會傳回錯誤。

完成可用欄位時，請使用下列資訊：

* [!UICONTROL **主機**]：輸入所需的FTP目的地URL。 例如，`ftp://ftp.omniture.com`。
* [!UICONTROL **路徑**]：可留空
* [!UICONTROL **使用者名稱**]：輸入使用者名稱以登入FTP站台。
* [!UICONTROL **密碼和確認密碼**]：輸入密碼以登入FTP站台。

### SFTP

SFTP 可支援資料摘要。必須填入 SFTP 主機、使用者名和目的地站點，才能包含有效的 RSA 或 DSA 公開金鑰。建立摘要時，您可以下載相關的公開金鑰。

### S3

您可以直接傳送摘要至 Amazon S3 貯體。此目的地類型需要貯體名稱、存取金鑰 ID 和機密金鑰。 如需詳細資訊，請參閱 Amazon S3 文件中的 [Amazon S3 貯體命名規定](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html)。

您提供來上傳資料摘要的使用者必須具備以下[權限](https://docs.aws.amazon.com/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html)：

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

  >[!NOTE]
  >
  >對於要上傳到 Amazon S3 貯體的每一項作業，[!DNL Analytics] 都會新增貯體所有者到 BucketOwnerFullControl ACL，無論該貯體是否有需要它的原則。 如需詳細資訊，請參閱&quot;[什麼是Amazon S3資料摘要適用的BucketOwnerFullControl設定？](df-faq.md#BucketOwnerFullControl)&quot;

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

資料摘要支援 Azure Blob 目的地。容器、帳戶和金鑰為必填。Amazon 會自動加密閒置的資料。下載資料時，則會自動解密。如需詳細資訊，請參閱 Microsoft Azure 文件中的[建立儲存帳戶](https://docs.microsoft.com/zh-tw/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys)。

>[!NOTE]
>
>您必須實作自己的處理程序，才能管理摘要目的地的磁碟空間。Adobe 不會從伺服器刪除任何資料。
