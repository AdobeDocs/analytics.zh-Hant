---
description: 設定雲端匯入帳戶和可以上傳分類資料的位置
keywords: Analysis Workspace
title: 設定雲端匯入位置
feature: Classifications
source-git-commit: 8d6ee33e867da274334c8adc557105af4942c894
workflow-type: tm+mt
source-wordcount: '1356'
ht-degree: 6%

---

# 設定雲端匯入位置

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

您必須先新增並設定收集分類資料的位置，才能從雲端目的地匯入Adobe Analytics分類資料。

此程式包括新增和設定帳戶(例如Amazon S3角色ARN、Google Cloud Platform等)以及帳戶內的位置（例如帳戶內的資料夾）。

## 新增帳戶

您需要使用存取雲端目的地帳戶所需的資訊來設定Adobe Analytics。

1. 在Adobe Analytics中選取 [!UICONTROL **元件**] > [!UICONTROL **位置**].
1. 於 [!UICONTROL 位置] 頁面，選取 [!UICONTROL **位置認證**] 標籤。
1. 選取 [!UICONTROL **新增帳戶**]. <!-- add screenshot? -->

   新增帳戶對話方塊隨即顯示。
1. 指定下列資訊： |欄位 |函式 | ---------|----------| | [!UICONTROL **位置帳戶名稱**] |位置帳戶的名稱。 建立位置時會顯示此名稱 | | [!UICONTROL **位置帳戶說明**] |提供帳戶的簡短說明，以協助將其與相同帳戶型別的其他帳戶區分開來。 | | [!UICONTROL **帳戶型別**] |選取您的雲端帳戶型別。 我們建議為每個帳戶型別設定單一帳戶，並視需要在該帳戶內設定多個位置。 |
1. 在 [!UICONTROL **帳戶屬性**] 區段，指定您所選取帳戶型別的特定資訊。

   如需設定指示，請展開以下對應至 [!UICONTROL **帳戶型別**] 您選取的專案。

   +++Amazon S3 Role ARN

   指定下列資訊以設定Amazon S3角色ARN帳戶：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **角色 ARN**] | 您必須提供角色ARN (Amazon資源名稱)，Adobe才能使用它來存取Amazon S3帳戶。 若要這麼做，請建立來源帳戶的IAM許可權原則、將原則附加至使用者，然後建立目的地帳戶的角色。 如需特定資訊，請參閱 [此AWS檔案](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
   | [!UICONTROL **使用者 ARN**] | 使用者ARN (Amazon資源名稱)由Adobe提供。 您必須將此使用者附加至您建立的原則。 |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   指定下列資訊以設定Google Cloud Platform帳戶：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **專案 ID**] | 您的Google Cloud專案ID。 請參閱 [有關取得專案ID的Google Cloud檔案](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   指定下列資訊以設定Azure SAS帳戶：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **應用程式 ID**] | 從您建立的Azure應用程式複製此ID。 在Microsoft Azure中，此資訊位於 **概觀** 標籤中選取「 」。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何透過Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **租用戶 ID**] | 從您建立的Azure應用程式複製此ID。 在Microsoft Azure中，此資訊位於 **概觀** 標籤中選取「 」。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何透過Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **金鑰保存庫 URI**] | <p>Azure金鑰儲存庫中SAS權杖的路徑。  若要設定Azure SAS，您需要使用Azure金鑰儲存庫將SAS權杖儲存為秘密。 如需詳細資訊，請參閱 [有關如何從Azure Key Vault設定和擷取密碼的Microsoft Azure檔案](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>建立金鑰儲存庫URI後，在金鑰儲存庫上新增存取原則，以授予您建立的Azure應用程式的許可權。 如需詳細資訊，請參閱 [有關如何指派金鑰儲存庫存取原則的Microsoft Azure檔案](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **金鑰保存庫祕密名稱**] | 將密碼新增至Azure金鑰儲存庫時建立的密碼名稱。 在Microsoft Azure中，此資訊位於您建立的金鑰儲存庫中，位於 **金鑰儲存庫** 設定頁面。 如需詳細資訊，請參閱 [有關如何從Azure Key Vault設定和擷取密碼的Microsoft Azure檔案](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **位置帳戶密碼**] | 從您建立的Azure應用程式複製密碼。 在Microsoft Azure中，此資訊位於 **憑證和密碼** 標籤中選取「 」。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何透過Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   指定下列資訊以設定Azure RBAC帳戶：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **應用程式 ID**] | 從您建立的Azure應用程式複製此ID。 在Microsoft Azure中，此資訊位於 **概觀** 標籤中選取「 」。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何透過Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **租用戶 ID**] | 從您建立的Azure應用程式複製此ID。 在Microsoft Azure中，此資訊位於 **概觀** 標籤中選取「 」。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何透過Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **位置帳戶密碼**] | 從您建立的Azure應用程式複製密碼。 在Microsoft Azure中，此資訊位於 **憑證和密碼** 標籤中選取「 」。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何透過Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

1. 繼續使用 [新增位置](#add-a-location).

## 新增位置

1. 您必須先新增帳戶，才能新增位置。 [新增帳戶](#add-an-account) 如果您尚未這樣做。
1. 在Adobe Analytics中選取 [!UICONTROL **元件**] > [!UICONTROL **位置**].
1. 於 [!UICONTROL 位置] 頁面，選取 [!UICONTROL **位置**] 標籤。
1. 選取 [!UICONTROL **新增位置**]. <!-- add screenshot? -->

   「位置」對話方塊隨即顯示。
1. 指定下列資訊： |欄位 |函式 | ---------|----------| | [!UICONTROL **名稱**] |位置名稱。  | | [!UICONTROL **說明**] |提供帳戶的簡短說明，以協助將其與相同帳戶型別的其他帳戶區分開來。 | | [!UICONTROL **位置帳戶**] |選取您在中建立的位置帳戶 [新增帳戶](#add-an-account). |

1. 在 [!UICONTROL **位置屬性**] 區段，指定您位置帳戶之帳戶型別的特定資訊。

   如需設定指示，請展開以下與您在「 」中選取的帳戶型別相對應的區段 [!UICONTROL **位置帳戶**] 欄位。

   +++Amazon S3 Role ARN

   指定下列資訊以設定Amazon S3角色ARN位置：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **貯體名稱**] | 您想要將Adobe Analytics資料傳送至的Amazon S3帳戶中的貯體。 確保Adobe提供的使用者ARN有權將檔案上傳至此儲存貯體。 |
   | [!UICONTROL **金鑰前置詞**] | 要放置資料之儲存貯體中的資料夾。 指定資料夾名稱，然後在名稱后面加上反斜線，以建立資料夾。 例如， folder_name/ |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   指定下列資訊以設定Google Cloud平台位置：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **貯體名稱**] | 您想要將Adobe Analytics資料傳送至的GCP帳戶中的貯體。 確保您已授予Adobe所提供之主體的許可權，可將檔案上傳至此儲存貯體。 |
   | [!UICONTROL **金鑰前置詞**] | 要放置資料之儲存貯體中的資料夾。 指定資料夾名稱，然後在名稱后面加上反斜線，以建立資料夾。 例如， folder_name/ |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   指定下列資訊以設定Azure SAS位置：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **容器名稱**] | 您指定的帳戶中要將Adobe Analytics資料傳送至何處的容器。 |
   | [!UICONTROL **金鑰前置詞**] | 容器中要放置資料的資料夾。 指定資料夾名稱，然後在名稱后面加上反斜線，以建立資料夾。 例如， `folder_name/` |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   指定下列資訊以設定Azure RBAC位置：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **容器名稱**] | 您指定的帳戶中要將Adobe Analytics資料傳送至何處的容器。 請確定您授與許可權，可以將檔案上傳至您先前建立的Azure應用程式。 |
   | [!UICONTROL **金鑰前置詞**] | 容器中要放置資料的資料夾。 指定資料夾名稱，然後在名稱后面加上反斜線，以建立資料夾。 例如， `folder_name/` |
   | [!UICONTROL **帳戶名稱**] | Azure儲存體帳戶。 |

   {style="table-layout:auto"}

+++

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

   您現在可以將資料匯入至您設定的帳戶和位置。