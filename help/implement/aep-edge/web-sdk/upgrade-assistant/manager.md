---
title: 在Web SDK升級助理中管理移轉
description: 在Web SDK升級助理中建立、檢視及開啟移轉。
feature: Implementation Basics
role: Admin, Developer, Leader
badge: Beta
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
    internal-label: Use cases
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 629efca210346d32b8555c60f7db15d1d8285b20
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%
---
# 管理移轉

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_migrations"
>title="移轉"
>abstract="每次移轉都會將一個Tags屬性中的Adobe Analytics實作升級為Web SDK。 開啟移轉，從您中斷的地方繼續，或選取「新增」開始移轉。"

**[!UICONTROL 移轉]**&#x200B;頁面是Web SDK升級助理的起點。 其中會列出您組織中的移轉，包括每個移轉的進度、狀態以及建立者。 您可以在此頁面建立移轉或開啟現有的移轉。

## 建立移轉 {#create}

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_newmigration"
>title="新移轉"
>abstract="選取您要移轉的tags屬性，並選取該屬性中的程式庫。 當您建立移轉時，Upgrade Assistant會建立程式庫的快照。 移轉快照後對程式庫進行的變更不會包括在內。 您必須完成移轉，標籤屬性才會變更。"

<!-- markdownlint-enable MD034 -->

在建立移轉之前，請確定您符合[必要條件](overview.md#prerequisites)。

1. 在&#x200B;**[!UICONTROL 移轉]**&#x200B;頁面上，選取&#x200B;**[!UICONTROL 新增]**。
1. 輸入移轉的名稱，並視需要輸入說明。
1. 選取您要移轉的標籤屬性。
1. 選取標籤庫。 當您建立移轉時，Upgrade Assistant會建立您實作的快照，如同此程式庫中一樣。 之後您對程式庫進行的變更不會反映在移轉中。
1. 選取&#x200B;**[!UICONTROL 建立]**。

新的移轉會顯示在清單中。 開啟它以啟動[元件選擇](component-selection.md)。

## 開啟移轉 {#open}

選取移轉的名稱以開啟。 移轉步驟會顯示在左側導覽中。 您可以隨時返回任何已完成的步驟進行檢閱或變更，但您尚未到達的步驟無法使用。

升級小幫手會在您執行各個步驟時儲存進度，以便您離開移轉程式並稍後返回。 在您[完成移轉](final-review.md#finalize)之前，您設定的任何專案都不會生效。 在您完成移轉後，移轉會變成唯讀。 您仍然可以開啟它以檢視它建立的內容，但您無法變更它。

## 其他移轉動作 {#actions}

選取移轉的列以顯示可執行的動作：

* **[!UICONTROL 繼續]**：開啟移轉。
* **[!UICONTROL 重複執行]**：建立移轉的復本。
* **[!UICONTROL 重新命名]**：變更移轉的名稱和描述。
* **[!UICONTROL 封存]**：將移轉狀態變更為&#x200B;**[!UICONTROL 已封存]**。
* **[!UICONTROL 刪除移轉]**：永久刪除移轉。 您無法復原此操作。
