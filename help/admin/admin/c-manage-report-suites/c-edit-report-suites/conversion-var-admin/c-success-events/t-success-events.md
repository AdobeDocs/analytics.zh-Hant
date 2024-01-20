---
description: 說明如何設定成功事件的步驟。
title: 設定成功事件
feature: Event
role: Admin
exl-id: 0e9a6d8f-2ce7-4551-885d-bd77ff131da0
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 100%

---

# 設定成功事件

若要設定成功事件：

1. 按一下 **[!UICONTROL Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]**。
1. 選取報表套裝。
1.  按一下&#x200B;**[!UICONTROL 「編輯設定]** > **[!UICONTROL 轉換]** > **[!UICONTROL 成功事件」]**。

   ![步驟結果](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/assets/success_event_page.png)

1.  在&#x200B;**[!UICONTROL 「名稱」]**&#x200B;欄中選取每個項目旁的核取方塊以啟用編輯，然後指定所要的名稱。
1.  在&#x200B;**[!UICONTROL 「類型」]**&#x200B;欄中選取每個項目旁的核取方塊以啟用下拉式清單，然後選取所要的類型。

   >[!NOTE]
   >
   >在變更事件類型之前，請先參閱[變更事件類型](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/event-type.md)。

   如需這些元素的相關資訊，請參閱[成功事件頁面 - 說明](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md)。

1. 在&#x200B;**[!UICONTROL 「極性」]**&#x200B;欄中，指定此量度的趨勢上升是好事或壞事。
1. 在&#x200B;**[!UICONTROL 「可見性」]**&#x200B;欄中，您可以在功能表、量度選擇器、計算量度產生器及區段產生器中隱藏標準 (內建) 量度、自訂事件及內建事件。

   此設定不會影響該量度或事件的資料彙集作業，只會影響其使用者介面的可見性，如下所示：


   | 設定 | 可見於 | 不可見於 |
   |---------|----------|---------|
   | [!UICONTROL **隨處可見**] | <ul><li>Analysis Workspace</li><li>區段產生器</li><li>計算量度產生器</li></ul> | 不適用 |
   | [!UICONTROL **產生器**] | <ul><li>區段產生器</li><li>計算量度產生器</li><li>Analysis Workspace</li></ul> |
   | [!UICONTROL **隨處隱藏**] | 不適用 | <ul><li>Analysis Workspace</li><li>區段產生器</li><li>計算量度產生器</li></ul> |

1. 提供說明。
1. 檢查是否一律記錄事件。
1. 啟用或停用參與率度量。

   >[!NOTE]
   >
   >您可以啟用的參與率最多可達 100 個自訂事件。除此之外，您還可在[計算量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md)產生器中建立參與率量度。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。
