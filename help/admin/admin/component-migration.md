---
description: 說明如何將元件和專案從Adobe Analytics移轉至Customer Journey Analytics。
title: 將元件和專案從Adobe Analytics移轉至Customer Journey Analytics
feature: Admin Tools
source-git-commit: 73cbfbbad4d8e7bb3107ee08861a6342aba85e84
workflow-type: tm+mt
source-wordcount: '1133'
ht-degree: 10%

---

# 將元件和專案從Adobe Analytics移轉至Customer Journey Analytics

Adobe Analytics管理員可將Adobe Analytics元件和專案移轉至Customer Journey Analytics。

移轉程式包括：

* 在Customer Journey Analytics中重新建立Adobe Analytics專案。

* 將Adobe Analytics報表套裝中的維度和量度與Customer Journey Analytics資料檢視中的維度和量度比對。

  有些維度和量度會自動比對，有些則必須在移轉程式中手動比對。

## 準備移轉

### 先決條件

在專案及其相關維度和量度準備移轉之前，您首先需要：

* 使用Analytics來源聯結器檢視Customer Journey Analytics中的Adobe Analytics報告套裝資料。 若要這麼做，您需要：

   * [設定報表套裝以擷取至Adobe Experience Platform和Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

   * [擷取及使用資料](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=zh-Hant)

* 確保Customer Journey Analytics中的使用者已布建至資料相符的資料檢視。

  如需詳細資訊，請參閱 [Admin Console中的Customer Journey Analytics許可權](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) 在 [Customer Journey Analytics存取控制](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

  Admin Console 中每個產品設定檔都有 權限 索引標籤。您可以將使用者新增到特定的產品設定檔。然後，將權限指派給指定的資料檢視，並指定產品設定檔中的使用者擁有哪些權限。

* 建立移轉計畫，如下節所述， [建立組織的移轉計畫](#create-a-migration-plan-as-an-organization).

### 瞭解移轉包含的內容

下表概述移轉中包含的專案和元件元素：


|  | 專案 | Dimension和量度 |
|---------|----------|---------|
| **日期範圍** | 是 | 不適用 |
| **區段** | 是 | 不適用 |
| **快速區段** | 是 | 不適用 |
| **面板** | 是 | 不適用 |
| **視覺效果** | 是 | 不適用 |
| **所有者** | （由進行移轉的使用者定義） | ? |
| **組織** | 否 | 不適用 |
| **共用（專案角色）** | 否 | 否 |
| **註解** | 否 | 不適用 |
| **檔案夾結構** | 否 | 不適用 |
| **說明** | 是 | ? |
| **標記** | ? | ? |
| **時程表** | ? | 不適用 |
| **歸因（在維度上）** | 不適用 | ? |
| **異常偵測** | ? | 不適用 |
| **貢獻分析** | ? | 不適用 |
| **警報** | ? | 不適用 |

{style="table-layout:auto"}

### 建立組織的移轉計畫

因為任何符合特定專案移轉的元件都適用於整個組織未來的專案移轉，所以您的組織必須提前計畫所有專案移轉。

作為組織，您應該決定哪些維度和量度將符合哪些維度和量度，以避免個別管理員在專案移轉時於筒倉中做出決策。

## 將Adobe Analytics專案移轉至Customer Journey Analytics

>[!IMPORTANT]
>
>在依本節所述將任何專案移轉至Customer Journey Analytics之前，請先瞭解更多有關移轉專案的資訊，請參閱 [規劃移轉](#plan-the-migration) 一節。
>
>您符合的任何維度或量度都是永久性的，不論是此專案還是整個組織內移轉的所有未來專案皆然。 您無法修改任何符合的專案。



1. 在Adobe Analytics中，選取 [!UICONTROL **管理員**] 索引標籤，然後選取 [!UICONTROL **所有管理員**].

1. 在 [!UICONTROL **資料設定和收集**]，選取 [!UICONTROL **元件移轉**].

1. （視條件而定）若要快速找到您要移轉的專案，您可以：

   * 選取篩選圖示，即可篩選專案清單。

     您可以依下列條件篩選：

      * 狀態

      * 標記

      * 報表套裝

      * 擁有者

      * 其他篩選器

   * 使用搜尋欄位來搜尋您要移轉的專案。

1. 將游標移至您要移轉的專案上，然後選取 **移轉** 圖示 ![移轉專案](assets/migrate.svg).

   或

   選取您要移轉的專案，然後選取 [!UICONTROL **移轉至Customer Journey Analytics**].

   您一次只能選取一個專案進行移轉。

   此 [!UICONTROL **將project_name移轉至Customer Journey Analytics**] 對話方塊隨即顯示。

   <!-- add screenshot -->

1. 在 [!UICONTROL **專案所有者**] 欄位，開始輸入Customer Journey Analytics中要設定為專案所有者的使用者名稱，然後在下拉式選單中選取其名稱。

   您指定的所有者擁有此專案的完整管理權限.

1. 在 [!UICONTROL **匹配報表套裝的結構描述**] 區段，選取報表套裝。

1. 在 [!UICONTROL **資料檢視**] 下拉式功能表，選取您要移轉專案和元件的Customer Journey Analytics資料檢視。

1. 選取 [!UICONTROL **符合結構描述**].

1. 在 [!UICONTROL **符合結構描述**] 區段，展開 [!UICONTROL **Dimension**] 和 [!UICONTROL **量度**] 區段。

   Adobe Analytics中的某些維度和量度會自動符合Customer Journey Analytics中的維度或量度。 其他需要手動比對。

   **自動比對的維度和量度**

   Adobe Analytics中的某些維度和量度會自動符合Customer Journey Analytics中的維度或量度。 您無法針對這些維度和量度做出任何相符的決定。

   例如， **造訪** Adobe Analytics中的量度會自動比對至 **工作階段** Customer Journey Analytics中的量度。

   您可以選取任何維度或量度來檢視其相關聯的ID。

   <!-- update screenshot after I can see the Status column -->

   ![專案移轉綱要](assets/project-migration-schema.png)

   **手動比對維度和量度**

   Adobe Analytics中的其他維度和量度無法自動比對Customer Journey Analytics中的維度或量度。

   當維度或量度無法自動比對時，橘色計數器會顯示在 [!UICONTROL **Dimension**] 或 [!UICONTROL **量度**] 區段標題，指出需要手動比對的維度或量度數目。 在表格中，警告圖示 ![警告圖示](assets/schema-warning.png) 會顯示在每個需要手動比對的維度或量度旁。

   <!-- update screenshot after I can see the Status column -->

   ![移轉結構描述手動比對](assets/schema-manual-map.png)

1. 若要手動比對維度和量度，請選取包含警告圖示的維度或量度 ![警告圖示](assets/schema-warning.png)，然後在 [!UICONTROL **符合Customer Journey Analytics量度**] 欄位(或 [!UICONTROL **符合Customer Journey Analytics維度**] 欄位（如果您比對維度），請在「Customer Journey Analytics」中選取您要與所選維度或量度比對的維度或量度。

   ![比對維度和量度](assets/schema-manual-map-drop-down.png)

   對包含警告圖示的每個維度或量度重複此程式。

   Adobe Analytics報表套裝中的所有維度和量度符合Customer Journey Analytics資料檢視中的維度或量度後，綠色勾號 ![核取標籤](assets/report-suite-check.png) 會出現在中的報表套裝名稱旁 [!UICONTROL **匹配報表套裝的結構描述**] 區段。

1. （視條件而定）如果您要移轉的專案包含多個報表套裝，請在 [!UICONTROL **匹配報表套裝的結構描述**] 區段，然後重複步驟6到步驟10。 <!-- double-check that the step numbers are still correct -->

1. 選取 [!UICONTROL **移轉**].

   >[!WARNING]
   >
   >   選取後熒幕上會顯示警告訊息 [!UICONTROL **移轉**]. 在選擇繼續之前，請先瞭解您符合的任何維度或量度對於此專案及整個組織移轉的所有未來專案而言都是永久性的。 如果繼續，將無法修改您所做的相符專案。
