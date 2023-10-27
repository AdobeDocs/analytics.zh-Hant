---
description: 設定雲端匯入帳戶以及可上傳分類資料的位置
keywords: Analysis Workspace
title: 設定雲端匯入位置
feature: Classifications
exl-id: 55179868-6228-44ff-835c-f4a7b38e929b
source-git-commit: f71b80dce9d447c431130901d86947d23e28d378
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 7%

---

# 設定雲端匯入位置

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

您必須先新增並設定帳戶，以及您希望收集分類資料的帳戶位置，才能從雲端目的地匯入Adobe Analytics分類資料。

此程式包括新增及設定帳戶(例如Amazon S3角色ARN、Google Cloud Platform等)以及帳戶內的位置（例如帳戶內的資料夾）。

若要設定雲端匯入位置：

1. 您必須先新增帳戶，才能新增位置。 如果您尚未新增帳戶，請依照所述新增帳戶 [設定雲端匯入帳戶](/help/components/locations/configure-import-accounts.md).
1. 在Adobe Analytics中，選取 [!UICONTROL **元件**] > [!UICONTROL **位置**].
1. 在 [!UICONTROL 位置] 頁面，選取 [!UICONTROL **位置**] 標籤。
1. 選取 [!UICONTROL **新增位置**]. <!-- add screenshot? -->

   「位置」對話方塊隨即顯示。
1. 指定下列資訊： |欄位 |函式 | ---------|----------| | [!UICONTROL **名稱**] |位置名稱。  | | [!UICONTROL **說明**] |提供帳戶的簡短說明，以協助將其與相同帳戶型別的其他帳戶區分開來。 | | [!UICONTROL **位置帳戶**] |選取您在中建立的位置帳戶 [新增帳戶](#add-an-account). |

1. 在 [!UICONTROL **位置屬性**] 區段，指定您位置帳戶之帳戶型別的專屬資訊。

   如需設定指示，請展開以下與您在所選帳戶型別對應的區段 [!UICONTROL **位置帳戶**] 欄位。

   +++Amazon S3 Role ARN

   指定下列資訊以設定Amazon S3角色ARN位置：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **貯體名稱**] | 您想要將Adobe Analytics資料傳送至的Amazon S3帳戶中的貯體。 |
   | [!UICONTROL **金鑰前置詞**] | 要放置資料之儲存貯體中的資料夾。 指定資料夾名稱，然後在名稱后面加上反斜線以建立資料夾。 例如， folder_name/ |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   指定下列資訊來設定Google Cloud平台位置：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **貯體名稱**] | 您想要將Adobe Analytics資料傳送至的GCP帳戶中的貯體。 確保您已授予Adobe所提供之主體的許可權，可將檔案上傳至此儲存貯體。 |
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

   您現在可以從您設定的帳戶和位置匯入資料。

   匯入資料後，資料不會從雲端目的地刪除。

   >[!NOTE]
   >
   >   如果您先前曾使用 [FTP以匯入分類](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) 若為Adobe Analytics，您需要上傳FIN檔案。 從雲端帳戶匯入時，不需要此FIN檔案。

