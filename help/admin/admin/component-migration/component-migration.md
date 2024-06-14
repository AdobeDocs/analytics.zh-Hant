---
description: 說明如何將元件和專案從Adobe Analytics移轉至Customer Journey Analytics。
title: 將元件和專案從Adobe Analytics移轉至Customer Journey Analytics
feature: Admin Tools
exl-id: 49c7e47a-464b-4465-9b30-d77f886ca6dc
source-git-commit: b8d47e8802198365b348f94efc3f71ff424e83d1
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 5%

---

# 將元件和專案從Adobe Analytics移轉至Customer Journey Analytics

Adobe Analytics 管理員可以將 Adobe Analytics 專案及其關聯元件移轉到 Customer Journey Analytics。

移轉過程包括：

* 在 Customer Journey Analytics 中重新建立 Adobe Analytics 專案。

* 將 Adobe Analytics 報表套件中的維度和指標對應到 Customer Journey Analytics 資料視圖中的維度和指標。

  有些維度和量度會自動對應，有些則必須在移轉程式中手動對應。 區段也會移轉，但在移轉過程中不需要進行對應。

  移轉完成時，所有移轉的元件都會顯示在移轉摘要中。

## 準備移轉

在將任何專案移轉至Customer Journey Analytics之前，請先瞭解更多有關移轉專案的資訊 [準備將元件和專案從Adobe Analytics移轉至Customer Journey Analytics](/help/admin/admin/component-migration/prepare-component-migration.md).

## 將Adobe Analytics專案移轉至Customer Journey Analytics

>[!IMPORTANT]
>
>在依本節所述將任何專案移轉至Customer Journey Analytics之前，請先瞭解更多有關移轉專案的資訊，請參閱 [準備將元件和專案從Adobe Analytics移轉至Customer Journey Analytics](/help/admin/admin/component-migration/prepare-component-migration.md).
>
>**無論此專案或是在整個IMS組織中移轉的所有未來專案，您對映的任何維度或量度都是永久性的，無論執行移轉的使用者為何。 除非連絡客戶服務，否則無法修改或復原這些對應。**

1. 在 Adobe Analytics 中，選取「[!UICONTROL **管理員**]」索引標籤，然後選取「[!UICONTROL **所有管理員**]」。

1. 在 [!UICONTROL **資料設定和收集**]，選取 [!UICONTROL **元件移轉**].

1. 找到您要移轉的專案。 您可以篩選、排序或搜尋專案清單。

   預設情況下，僅顯示與您共用的專案。 若要檢視貴組織的所有專案，請選取 **篩選** 圖示，然後展開 [!UICONTROL **其他篩選器**] 並選取 [!UICONTROL **顯示全部**]. (如需有關篩選、排序和搜尋專案清單的詳細資訊，請參閱 [篩選、排序和搜尋專案清單](#filter-sort-and-search-the-list-of-projects).)

1. 將游標移至您要移轉的專案上，然後選取 **移轉** 圖示 ![移轉專案](assets/migrate.svg).

   或

   選取您要移轉的專案，然後選取 [!UICONTROL **移轉至Customer Journey Analytics**].

   您一次只能選取一個專案進行移轉。

   此 [!UICONTROL **將project_name移轉至Customer Journey Analytics**] 對話方塊隨即顯示。

   <!-- add screenshot -->

1. 在 [!UICONTROL **專案所有者**] 欄位，開始輸入Customer Journey Analytics中要設定為專案所有者的使用者名稱，然後在下拉式選單中選取其名稱。

   您指定的擁有者擁有專案的完整管理許可權。

1. 在 [!UICONTROL **對應報表套裝的結構描述**] 區段，選取報表套裝。

1. 在 [!UICONTROL **資料檢視**] 下拉式功能表，選取您要移轉專案和元件的Customer Journey Analytics資料檢視。

1. 選取 [!UICONTROL **對應結構描述**].

1. 在 [!UICONTROL **對應結構描述**] 區段，展開 [!UICONTROL **Dimension**] 和 [!UICONTROL **量度**] 區段。

   Adobe Analytics中的某些維度和量度會自動對應至Customer Journey Analytics中的維度或量度。 其他則需要手動對應。

   **自動對應維度和量度**

   >[!NOTE]
   >
   >   如果您使用WebSDK將資料內嵌至Adobe Experience Platform，維度和量度無法自動對應。 如需詳細資訊，請參閱 [必要條件](/help/admin/admin/component-migration/prepare-component-migration.md#prerequisites) 在 [準備將元件和專案從Adobe Analytics移轉至Customer Journey Analytics](/help/admin/admin/component-migration/prepare-component-migration.md).

   Adobe Analytics中的某些維度和量度會自動對應至Customer Journey Analytics中的維度或量度。 您無法針對這些維度和量度做出任何對應決策。

   例如， **造訪** Adobe Analytics中的量度會自動與 **工作階段** Customer Journey Analytics中的量度。

   您可以選取任何維度或量度來檢視其相關聯的ID。

   <!-- update screenshot after I can see the Status column -->

   ![專案移轉綱要](assets/project-migration-schema.png)

   **手動對應維度和量度**

   Adobe Analytics中的部分維度和量度無法自動對應至Customer Journey Analytics中的維度或量度。

   當維度或量度無法自動對應時，橘色計數器會顯示在 [!UICONTROL **Dimension**] 或 [!UICONTROL **量度**] 區段標題，指出需手動對應的維度或量度數目。 在表格中，警告圖示 ![警告圖示](assets/schema-warning.png) 會顯示在每個需要手動對應的維度或量度旁。

   此外， [!UICONTROL **狀態**] 欄顯示 [!UICONTROL **未對應**].

   <!-- update screenshot after I can see the Status column -->

   ![移轉結構描述手動對應](assets/schema-manual-map.png)

1. 若要手動對應維度和度量，請選取包含警告圖示的維度或度量 ![警告圖示](assets/schema-warning.png)，然後在 [!UICONTROL **對應的Customer Journey Analytics量度**] 欄位(或 [!UICONTROL **對應的Customer Journey Analytics維度**] 欄位如果您要對應維度)，請在「Customer Journey Analytics」中選取您要對應至您所選維度或量度的維度或量度。

   ![對應維度和量度](assets/schema-manual-map-drop-down.png)

   維度或量度對應後，警告圖示會消失，且 [!UICONTROL **狀態**] 欄變更為 [!UICONTROL **已對應**] 綠色圓點。 (狀態 [!UICONTROL **已對應**] 灰點表示維度或量度在上次移轉期間已對應；無法更新任何先前的對應。)

   對包含警告圖示的每個維度或量度重複此程式。

   Adobe Analytics報表套裝中的所有維度和量度都會對應至Customer Journey Analytics資料檢視中的維度或量度後，綠色勾號 ![核取標籤](assets/report-suite-check.png) 會出現在中的報表套裝名稱旁 [!UICONTROL **對應報表套裝的結構描述**] 區段。

1. （視條件而定）如果您要移轉的專案包含多個報表套裝，請在 [!UICONTROL **對應報表套裝的結構描述**] 區段，然後重複步驟6到步驟10。 <!-- double-check that the step numbers are still correct -->

1. 選取 [!UICONTROL **移轉**].

   >[!WARNING]
   >
   >   選取後熒幕上會顯示警告訊息 [!UICONTROL **移轉**]. 選擇繼續之前，請先瞭解您對應之任何維度或量度對於此專案及整個組織未來移轉的所有專案而言都是永久性的。 如果繼續，則無法修改您建立的對應。

   移轉完成後， [!UICONTROL **移轉狀態**] 頁面提供已移轉專案的摘要。

   如果移轉失敗，請參閱 [重試失敗的移轉](#retry-a-failed-migration) 區段以取得詳細資訊。

## 重試失敗的移轉

如果移轉失敗，您可以重試移轉。

在重試失敗的移轉之前，請務必移除所有 [不支援的元素](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html#understand-unsupported-elements-that-cause-errors) 從專案中移除。

>[!NOTE]
>
>如果重試後移轉仍持續失敗，請聯絡客戶服務並提供專案ID。 您可以在移轉狀態頁面找到專案ID。 <!-- when does this page display? How can they get there -->

若要重試失敗的移轉：

1. 在 Adobe Analytics 中，選取「[!UICONTROL **管理員**]」索引標籤，然後選取「[!UICONTROL **所有管理員**]」。

1. 在 [!UICONTROL **資料設定和收集**]，選取 [!UICONTROL **元件移轉**].

1. 選取 [!UICONTROL **已失敗**] 在 [!UICONTROL **移轉狀態**] 要重試之專案旁邊的欄。

   ![移轉狀態列失敗](assets/migration-failed.png)

   此 [!UICONTROL **移轉狀態**] 頁面隨即顯示。

   此頁面也會在完成一節所述的移轉步驟後立即顯示 [將Adobe Analytics專案移轉至Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics) 以上。

1. 選取 [!UICONTROL **重試移轉**].

## 篩選、排序和搜尋專案清單

您可以在「元件移轉」頁面上篩選、排序和搜尋專案清單。

### 篩選專案清單

您可以依下列條件篩選：

| 篩選器 | 說明 |
|---------|----------|
| [!UICONTROL **狀態**] | 移轉的狀態： <ul><li>[!UICONTROL **尚未開始**]</li><li>[!UICONTROL **已開始**]</li><li>[!UICONTROL **已完成**]</li><li>[!UICONTROL **已失敗**]</li></ul>。 |
| [!UICONTROL **標記**] | 選取標籤清單中的任何標籤。 只會顯示已套用選取標籤的專案。 |
| [!UICONTROL **報告套裝**] | 在報表套裝清單中選取任何報表套裝。 系統只會顯示使用選定報表套裝的專案。 |
| [!UICONTROL **擁有者**] | 在擁有者清單中選取任何擁有者。 系統只會顯示您所選取使用者擁有的專案。 |
| [!UICONTROL **其他篩選器**] | 下列為其他可用的篩選： <ul><li>[!UICONTROL **我的**]：僅顯示您設為擁有者的專案。</li><li>[!UICONTROL **與我共用**]：僅顯示已與您共用的專案。</li><li>[!UICONTROL **我的最愛**]：僅顯示標籤為我的最愛的專案。 (您可以從以下位置將專案標示為我的最愛： [專案登陸頁面](/help/analyze/landing.md).)</li><li>[!UICONTROL **每月**]</li><li>[!UICONTROL **每年**]</li></ul> |

{style="table-layout:auto"}

### 排序專案清單

您可以依任何欄排序專案清單。

若要排序專案清單，請執行下列動作：

1. 選取要作為排序依據之欄的欄標題。

1. （選擇性）再次選取相同的欄標題來反轉排序順序。

### 搜尋專案

您可以在「元件移轉」頁面上搜尋專案清單，以尋找您要移轉的專案。

1. 在「元件移轉」頁面頂端的搜尋欄位中，開始輸入您要移轉的專案名稱。

1. 當專案出現在下拉式選單中時，請選取專案。

<!-- is there going to be a way to customize the columns that are displayed? -->
