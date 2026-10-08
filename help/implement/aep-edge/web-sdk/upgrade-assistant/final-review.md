---
title: 在網路SDK升級助理中進行最終稽核
description: 檢閱並完成網站SDK移轉，然後將產生的標籤程式庫發佈至生產環境。
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
source-wordcount: '469'
ht-degree: 0%
---
# 最終稽核

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_finalreview"
>title="最終稽核"
>abstract="選取要使用的Experience Platform沙箱，然後檢閱此移轉建立或變更的所有內容。 在您完成移轉之前，不會有任何變更。 當您完成時，升級小幫手會一次建立所有內容、將標籤變更新增至新程式庫，並讓此移轉成為唯讀。 然後您自己將該程式庫發佈到生產環境。"

<!-- markdownlint-enable MD034 -->

最終檢閱是移轉的最後一步。 它會顯示移轉在Experience Platform和tags屬性中建立或變更的所有內容。

## 檢閱移轉建立的內容 {#review}

首先，選取移轉作業用來建立其資源的Experience Platform沙箱。 您必須先選取沙箱，才能完成移轉。

接著，升級小幫手會列出完成移轉作業所建立或變更的所有專案：

* **[!UICONTROL XDM]**：以您的XDM對應命名的新結構描述，以及它需要的自訂欄位群組。 標準欄位群組已存在，因此結構描述會照原樣使用它們。 只有當您選擇在[XDM對應](xdm-mapping.md#schema)中建立新結構描述時，才會顯示此區段。
* **[!UICONTROL 資料集]**：兩個資料集，一個用於開發，一個用於生產。 每個檔案都以移轉命名，例如`My migration - Development`。
* **[!UICONTROL 資料串流]**：兩個資料串流，一個用於開發，另一個用於生產，命名方式與資料集相同。
* **[!UICONTROL Adobe標籤]**：以移轉命名的新資料庫，例如`Library - "My migration"`。 程式庫包含移轉變更的規則和資料元素，以及Web SDK動作所需的擴充功能設定。

## 完成移轉 {#finalize}

在您完成移轉之前，升級助理不會變更您的標籤屬性，或在Experience Platform中建立任何內容。

>[!IMPORTANT]
>
>完成移轉後，系統就會變成唯讀。 您仍然可以從&#x200B;**[!UICONTROL 移轉]**&#x200B;頁面開啟它，以檢視它建立的內容，但無法變更它或再次完成它。 由於新程式庫仍在開發中，您發佈程式庫之前，可以在標籤UI中編輯或移除標籤變更。

1. 選取&#x200B;**[!UICONTROL 建立成品]**。
1. 在&#x200B;**[!UICONTROL 驗證這些建議]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 繼續]**。
1. 在&#x200B;**[!UICONTROL 完成此移轉？]** 對話方塊，選取&#x200B;**[!UICONTROL 完成]**。

升級小幫手會一次建立所有內容，並顯示進度。 它會新增標籤變更至新程式庫，但不會發佈程式庫。

## 發佈您的變更 {#publish}

完成移轉後，請透過標籤發佈流程移動新程式庫：

1. 在您的開發環境中建置並測試程式庫，以確保您的Web SDK實作會傳送您預期的資料。
1. 提交程式庫以供核准，並在您的中繼環境中測試。
1. 核准程式庫並將其發佈到生產環境。

請參閱標籤使用手冊中的[發佈流程](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/publishing/publishing-flow)。
