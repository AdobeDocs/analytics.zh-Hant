---
title: Web SDK升級助理
description: 規劃並執行將Adobe Analytics標籤擴充功能移轉到Adobe Experience Platform Web SDK。
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
source-git-commit: 212d38950264a33b925b7281c241992cadca2bfb
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 3%
---
# Web SDK升級助理

Web SDK升級小幫手可協助您規劃及執行Adobe Analytics標籤擴充功能移轉至Adobe Experience Platform Web SDK。 它將移轉帶入單一引導式工作區，讓您能夠透過結構化、可追蹤的方式，從現有的標籤實作移至網頁SDK。

## 升級助理的運作方式 {#how-it-works}

每個移轉都會在單一標籤屬性中與Adobe Analytics實作搭配使用。 升級助理會將Web SDK動作新增至您現有的規則，而不會移除其Adobe Analytics動作，因此您的實作會隨著Web SDK繼續將資料傳送至Adobe Analytics。

升級助理只會轉換Adobe Analytics元件。 您可以包含其他擴充功能（例如Adobe Target、Adobe Audience Manager或協力廠商擴充功能）的元件，但升級小幫手不會將其轉換為網頁SDK。

升級助理會引導您完成下列步驟，每個步驟都是以您在上一個步驟中所做的決定為基礎：

1. **[元件選擇](component-selection.md)**：選擇要包含在移轉中的規則、資料元素和延伸模組。
1. **[稽核結果](audit-findings.md)**：檢閱所選元件的選擇性清理建議。
1. **[對應程式準備](mapper-prep.md)**：檢閱報表套裝中的Analytics變數，並選擇要結轉的專案。
1. **[XDM對應](xdm-mapping.md)**：將您的Analytics變數對應到XDM結構描述中的欄位。
1. **[Web SDK實作](web-sdk-implementation.md)**：檢閱升級助理新增至規則的網頁SDK動作。
1. **[最終稽核](final-review.md)**：選取Experience Platform沙箱，稽核移轉建立的內容，然後完成移轉。

每個步驟都會設定移轉的一部分，您可以回到已完成的步驟，隨時檢閱或變更。 在您完成移轉之前，升級小幫手不會變更您的標籤屬性或在Experience Platform中建立任何專案。 當您完成之後，升級小幫手會一次建立所有內容，並將標籤變更新增至新程式庫。 然後您會測試該程式庫，並使用標籤發佈流程將其發佈到生產環境。

>[!IMPORTANT]
>
>升級助理使用人工智慧(AI)產生建議，例如XDM欄位對應和網頁SDK規則設定。 這些建議可能不準確或不完整。 請在將變更發佈到生產環境之前驗證這些變更。

## 先決條件 {#prerequisites}

在建立移轉之前，請確定您具備：

* 升級小幫手所需的[許可權](#permissions)。
* 使用Adobe Analytics擴充功能的標籤屬性。
* 屬性中包含您要移轉之實作的程式庫。 程式庫可以處於任何狀態，包括已發佈。 請參閱標籤使用手冊中的[資料庫](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/publishing/libraries)。

### 權限 {#permissions}

升級小幫手需要下列存取許可權。 請與貴組織的Experience Platform產品管理員合作，取得您缺少的任何許可權。

| 存取型別 | 必填 |
| --- | --- |
| [Experience Platform 權限](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home#permissions) | <ul><li>[!UICONTROL 檢視結構描述]</li><li>[!UICONTROL 管理結構描述]</li><li>[!UICONTROL 檢視資料集]</li><li>[!UICONTROL 管理資料集]</li><li>[!UICONTROL 檢視身分識別命名空間]</li></ul> |
| 產品存取 | <ul><li>資料收集（標籤）</li><li>Adobe Analytics</li></ul> |
| [標籤權利](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/administration/user-permissions) | [!UICONTROL 管理屬性] |

準備就緒後，[建立移轉](manager.md#create)。
