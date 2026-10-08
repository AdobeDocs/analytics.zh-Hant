---
title: Web SDK升級助理中的元件選擇
description: 選擇要納入Web SDK移轉中的標籤規則、資料元素和擴充功能。
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
source-wordcount: '401'
ht-degree: 0%
---
# 元件選取

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection"
>title="元件選取"
>abstract="選擇要包含在此移轉中的規則、資料元素和擴充功能。 依預設，會選取對您的Adobe Analytics實作有積極貢獻的元件。 後續步驟僅適用於您在此選取的元件。"

元件選取是移轉的第一步。 使用它從您的標籤屬性中選擇要包含在移轉中的規則、資料元素和擴充功能。

升級小幫手將標籤屬性中的元件組織成&#x200B;**[!UICONTROL 規則]**、**[!UICONTROL 資料元素]**&#x200B;和&#x200B;**[!UICONTROL 延伸模組]**&#x200B;標籤。 每個索引標籤會根據您[建立移轉](manager.md#create)時升級小幫手拍攝的程式庫快照，列出該型別的所有屬性元件。 依預設，只會選取主動對您的Adobe Analytics實施有貢獻的元件。 您可以選取或清除任何元件。

**[!UICONTROL Published]**&#x200B;欄顯示每個元件是否都是您選取之程式庫的一部分。 不屬於程式庫的元件會存在於tags屬性中，但不會存在於該程式庫中。 若要依此篩選清單，請使用&#x200B;**[!UICONTROL Source]**&#x200B;篩選器。

您可以包含與Adobe Analytics無關的元件，例如Adobe Target、Adobe Audience Manager或協力廠商擴充功能的元件，但升級助理不會將其轉換為網頁SDK。

您選取的元件會決定後續要搭配哪些步驟使用。 例如，您可以包含沒有參考的資料元素，以便[稽核結果](audit-findings.md)可以標幟它們以進行清除。

## 檢視元件詳細資料 {#details}

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection_tagsusage"
>title="標籤使用"
>abstract="使用此元件的規則、資料元素和擴充功能。 擴充功能使用方式僅涵蓋擴充功能組態設定。 規則內的使用方式會顯示在規則使用方式下方。"

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection_analyticsusage"
>title="Analytics使用情況"
>abstract="指派此元件的Adobe Analytics變數，依變數型別分組。"

<!-- markdownlint-enable MD034 -->

選取元件的名稱以開啟面板，顯示其設定和使用位置：

* **[!UICONTROL 標籤使用方式]**：使用元件的規則、資料元素和擴充功能。 **[!UICONTROL 擴充功能使用方式]**&#x200B;僅涵蓋擴充功能組態設定。 規則內的使用方式顯示在&#x200B;**[!UICONTROL 規則使用方式]**&#x200B;下。
* **[!UICONTROL Analytics使用情形]**：指派給元件的Adobe Analytics變數，依變數型別分組。

若要在標籤UI中檢視元件，請在面板頂端選取其名稱。

完成時，請選取&#x200B;**[!UICONTROL 儲存並繼續]**&#x200B;以移至[稽核發現](audit-findings.md)。