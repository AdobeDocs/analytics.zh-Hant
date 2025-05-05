---
description: 「區段管理員」提供許多管理區段的方式，例如共用、篩選、標記、核准、複製、刪除和標示為我的最愛。
title: 管理區段（區段管理員）
feature: Segmentation
exl-id: be182a55-23cb-415f-a7d0-3c1efeead1a1
source-git-commit: 8e8f59f747ddacc5462cbc177d199a5e0e91908a
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 27%

---

# 區段管理員

「區段管理員」提供許多管理區段的方式，例如共用、篩選、標記、核准、複製、刪除和標示為我的最愛。

「Analytics 區段管理員」會顯示您所擁有以及已經與您共用的區段。管理員級使用者可以查看組織中的所有區段。此概覽會介紹「區段管理員」的使用者介面和功能。

![區段管理員](assets/segments-manager.png)

## 存取「區段管理員」

1. 在Adobe Analytics中，選取&#x200B;**[!UICONTROL 元件]**&#x200B;索引標籤，然後選取&#x200B;**[!UICONTROL 區段]**。

   或

   在現有報表中，選取左側導覽的「區段」圖示![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg)，然後選取&#x200B;**[!UICONTROL 管理]**。

## 「區段管理員」中的可用動作

在「區段管理員」中，您可以：

* [篩選區段](/help/components/segmentation/segmentation-workflow/t-seg-filter.md)

* [將區段標示為最愛](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md)

* [核准區段](/help/components/segmentation/segmentation-workflow/seg-approve.md)

* [標記區段](/help/components/segmentation/segmentation-workflow/seg-tag.md)

* [共用區段](/help/components/segmentation/segmentation-workflow/t-seg-share.md)

* 將區段匯出至CSV檔案。

* [複製區段](/help/components/segmentation/segmentation-workflow/seg-copy.md)

* [刪除區段](/help/components/segmentation/segmentation-workflow/seg-delete.md)

## 設定欄

您可以設定要顯示的欄，以設定「區段管理員」中每個區段顯示的資訊。

若要在「區段管理員」中設定可見欄：

1. 在Adobe Analytics中，選取&#x200B;**[!UICONTROL 元件]**&#x200B;索引標籤，然後選取&#x200B;**[!UICONTROL 區段]**。

1. 在區段管理員中，選取&#x200B;**自訂欄**&#x200B;圖示![自訂欄圖示](assets/customize-columns-icon.png)，然後選取您要顯示在區段管理員中的欄。

   可使用下列欄:

   | 欄標題 | 說明 |
   |---|---|
   | 標題和說明 | 這些值會在區段產生器中提供。 若要編輯標題和說明，請選取標題連結以開啟區段產生器。 |
   | 我的最愛 | 在每個區段旁顯示星號圖示，讓您將區段標示為我的最愛。 如需詳細資訊，請參閱[將區段標示為我的最愛](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md)。 |
   | 報告套裝 | 此欄指出上次將區段儲存到的目標報表套裝。 |
   | 擁有者 | 指出區段的擁有者。如果您不是管理員，您只能看見自己所擁有或已共用給您的區段。 |
   | 標記 (未在欄選擇器中勾選，因此此欄不會出現) | 由您或共用區段給您的人員對區段套用的標記。 |
   | 共用對象 | 列出您將區段共用給的目標個人或群組 (僅限管理員使用) 或「全部」(僅限管理員使用)。 <p>當您共用區段時，區段名稱旁邊會顯示共用圖示。</p> |
   | 修改日期 | 顯示上次修改區段的日期。 |
   | 使用於 | 顯示目前區段的使用位置以及在每個區域中使用區段的次數。 <p>例如，如果區段用於40個專案和2個警示，則此欄的值顯示為&#x200B;[!UICONTROL **42個元件**]。</p> <p>選取此欄中的值，以檢視使用區段的劃分(例如，[!UICONTROL **專案(40)**]、[!UICONTROL **警報(2)**])。 此外，您可以檢視使用區段的專案清單。 例如，檢視使用它們的專案清單，選取&#x200B;[!UICONTROL **專案(40)**]&#x200B;連結。</p><p>下列各區顯示在該區域使用的區段例項數：</p>  <ul><li>[!UICONTROL **專案**]<p>包含[在區段產生器](/help/components/segmentation/segmentation-workflow/seg-build.md)中建立且適用於所有專案的區段。</p></li><li>[!UICONTROL **臨時元件**]<p>包含[建立為快速區段](/help/analyze/analysis-workspace/components/segments/quick-segments.md)的區段，且僅適用於單一專案。</p></li><li>[!UICONTROL **已排程的專案**]</li><li>[!UICONTROL **行動計分卡**]</li><li>[!UICONTROL **註解**]</li><li>[!UICONTROL **警報**]</li><li>[!UICONTROL **計算量度**]</li><li>[!UICONTROL **Report Builder**]<p>選取此選項可下載包含下列資料欄的CSV檔案：</p><ul><li>Report Builder名稱</li><li>上次存取</li><li>上次存取IMS使用者ID</li><li>上次存取的使用者名稱</li></ul><p>檢視Report Builder的資訊時，自2024年9月起即可使用相關資訊。</p></li></ul><p>此資訊可協助您判斷元件是否對貴組織中的使用者有價值、元件使用位置以及元件是否需要刪除或修改。</p><p>檢視此欄時請考慮以下事項：</p><ul><li>此資訊僅供系統管理員使用。</li><li>預設不會顯示&#x200B;**資料行中使用的**。 [設定資料行](#configure-columns)以顯示它。</li><li>如果區段在其定義中包含另一個區段，則該區段的任何使用都不會顯示在&#x200B;[!UICONTROL **Used in**]&#x200B;欄中。 如果區段包含在另一種元件型別（例如計算量度）的定義中，則使用狀況會顯示在&#x200B;[!UICONTROL **用於**]&#x200B;欄中。</li><li>此資訊不包括來自API或Data Warehouse的使用情況。</li><li>如果此欄中沒有指定元件的資料，但具有&#x200B;[!UICONTROL **上次使用**]&#x200B;日期，則表示該元件可能已用於分析而未儲存。</li><li>使用情況資訊從 2023 年 9 月開始提供。</li></ul><p>您可以搭配此資訊使用[資料字典](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)，協助您追蹤並更清楚瞭解組織中如何使用元件。</p> |
   | 上次使用 | 顯示上次在下列任何元件型別中使用區段的日期： <ul><li>警報</li><li>計算量度</li><li>專案</li><li>已排程的專案</li><li>區段</li></ul> <p>此資訊可協助您判斷元件是否對貴組織中的使用者有價值、元件使用位置以及元件是否需要刪除或修改。</p><p>檢視此欄時請考慮以下事項：</p><ul><li>此資訊不包括API、Report Builder或Data Warehouse的使用情況。</li><li>對於某些元件，如果元件是在2023年9月之前最後一次使用，則此欄可能不包含資料。</li><li>此資訊僅供系統管理員使用。</li></ul><p>您可以搭配此資訊使用[資料字典](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)，協助您追蹤並更清楚瞭解組織中如何使用元件。 |

   {style="table-layout:auto"}

## 操作說明影片 {#section_B3C5DA22DC5248DBA17C56E03DA2D4F2}

此 [Adobe Analytics 影片](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/segmentation/segment-management-and-sharing.html?lang=zh-Hant)提供如何使用區段管理員的簡短概覽。


