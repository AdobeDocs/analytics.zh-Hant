---
description: 設定雲端匯入帳戶和可以上傳分類資料的位置
keywords: Analysis Workspace
title: 設定雲端匯入位置
feature: Classifications
source-git-commit: 4efb0623d734419c376ca5f2bf2bbd94097ee4e4
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 8%

---

# 設定雲端匯入位置

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

從雲端目的地匯入Adobe Analytics分類資料之前，您需要新增並設定帳戶，以及該帳戶中要收集分類資料的位置。

此程式包括新增和設定帳戶(例如Amazon S3角色ARN、Google Cloud Platform等)以及帳戶內的位置（例如帳戶內的資料夾）。

若要設定雲端匯入位置：

1. 您必須先新增帳戶，才能新增位置。 如果您尚未建立帳戶，請依照中的說明新增帳戶 [設定雲端匯入帳戶](/help/components/locations/configure-import-accounts.md).
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