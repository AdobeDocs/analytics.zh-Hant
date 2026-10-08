---
title: Web SDK升級助理中的XDM對應
description: 在移轉Web SDK的過程中，將Adobe Analytics變數對應至XDM結構描述中的欄位。
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
source-wordcount: '419'
ht-degree: 3%
---
# XDM對應

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_xdmmapping"
>title="XDM對應"
>abstract="將您選取的Analytics變數對應至XDM結構描述中的欄位。 升級助理可以建立具有AI建議對應的新結構描述，或將變數對應到您已擁有的結構描述。 請先檢閱所有對應，然後再繼續。"

<!-- markdownlint-enable MD034 -->

Web SDK會使用[體驗資料模型(XDM)](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/home)欄位傳送資料，因此您從[報表套裝驗證](rs-verification.md)結轉的每個Analytics變數都需要XDM結構描述中的相符欄位。 在此步驟中，您可以選擇結構描述，並將變數對應至其欄位。

## 選擇結構描述 {#schema}

您可以使用下列兩種方式之一建立對應：

* **建立新的結構描述**：升級助理員會分析您的Analytics變數，並為每一個變數建議XDM欄位，然後根據這些建議產生結構描述以供您檢閱。
* **使用現有的結構描述**：選取Experience Platform中已存在的結構描述，然後自行將每個變數對應到欄位。

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_xdmmapping_fieldgroups"
>title="欄位群組偏好"
>abstract="選擇升級助理在建置方案時偏好的欄位群組型別。 標準欄位群組由Adobe定義。 自訂欄位群組由您的組織定義。"

<!-- markdownlint-enable MD034 -->

當您建立新綱要時，您也可以選擇升級助理員偏向標準或自訂欄位群組。 標準欄位群組由Adobe定義，自訂欄位群組則由您的組織定義。 請參閱XDM檔案中的[欄位群組](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#field-group)。

## 檢閱對應 {#review}

對應會連同對應到的XDM欄位一併列出每個Analytics變數，並預覽其旁邊的完整結構描述。 選取結構描述的一部分，將清單篩選為與其對應的變數。 您可以調整個別對應和結構描述本身。

升級助理使用AI來建議對應，結果可能不準確或不完整。 請先檢閱每個對應，然後再繼續。 在您[完成移轉](final-review.md#finalize)之前，升級小幫手不會在Experience Platform中建立結構描述。

完成時，請選取&#x200B;**[!UICONTROL 儲存並繼續]**&#x200B;以儲存您的對應並移至[網頁SDK實作](web-sdk-implementation.md)。 若要在儲存對應之後變更對應，請選取[編輯]，進行變更，然後選取[儲存]，再選取[繼續]。]********[!UICONTROL &#x200B;當您完成移轉時，不會包含您未以此方式儲存的變更。
