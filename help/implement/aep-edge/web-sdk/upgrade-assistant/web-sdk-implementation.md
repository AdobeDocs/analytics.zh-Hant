---
title: Web SDK升級助理中的Web SDK實作
description: 檢閱升級助理新增至現有標籤規則的網頁SDK動作。
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
source-wordcount: '311'
ht-degree: 0%
---
# Web SDK實作

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_websdkimplementation"
>title="Web SDK實作"
>abstract="檢閱升級助理新增至規則的網頁SDK動作。 您的Adobe Analytics動作原地不動。 選取要並排比較其目前和Web SDK設定的元件。 只有您佇列的元件會新增至移轉。"

<!-- markdownlint-enable MD034 -->

升級助理使用您選取的元件和您的[XDM對應](xdm-mapping.md)，在每個Adobe Analytics動作之後直接將Web SDK動作新增至您的規則。 Analytics動作會維持不變，因此這些規則會將資料傳送至Adobe Analytics和Web SDK。 大部分的資料元素都會沿用不變，而規則會繼續依名稱參照。

**[!UICONTROL 變更型別]**&#x200B;資料行顯示完成移轉對每個元件的作用：

* **[!UICONTROL 已新增Web SDK動作]**：升級助理已新增Web SDK動作至規則。
* **[!UICONTROL 沒有變更]**：元件會轉送未變更的內容。
* **[!UICONTROL 已封鎖]**：元件需要您檢閱，升級助理才能新增網頁SDK動作。 選取元件以檢視是什麼阻擋了它。

選取要並排比較其目前設定與其Web SDK設定的元件。 如果您需要更多內容，升級助理員會連結至標籤UI中的元件。

排入佇列的元件會新增至移轉。 若要將元件排入佇列，請在清單中選取該元件，或在其詳細資訊中選取&#x200B;**[!UICONTROL 佇列]**。 若要將它取出，請選取[從佇列中移除]。**** 升級助理不會變更您的標籤屬性，直到您[完成移轉](final-review.md#finalize)。

升級助理會使用AI來產生網頁SDK動作，且結果可能不準確或完整。 產生動作不會驗證它們在您的網站上如何行為，因此請在發佈程式庫之前先測試它們。
