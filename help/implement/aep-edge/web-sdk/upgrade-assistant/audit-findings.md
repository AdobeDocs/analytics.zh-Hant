---
title: Web SDK升級助理中的稽核結果
description: 在移轉至Web SDK之前，請檢閱並解決標籤元件的選擇性清理建議。
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
source-wordcount: '335'
ht-degree: 2%
---
# 稽核發現

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_auditfindings"
>title="稽核發現"
>abstract="調查結果會指出您可能想要在移轉前清理的規則和資料元素，例如沒有參考的資料元素。 接受結果以在移轉中包含其建議的變更，或拒絕讓元件保持原狀。 此步驟為選用。"

<!-- markdownlint-enable MD034 -->

升級小幫手會檢查您在[元件選擇](component-selection.md)中選取的規則和資料元素，並標示您在移轉之前可能想要清除的規則和資料元素：

* 重複您可以合併的規則或共用事件和條件的規則
* 可能影響資料正確性的規則動作順序
* 可合併的重複資料元素
* 可能不使用的資料元素，您可以將其停用

此步驟為選用。 您可以解析任意數目的發現，或直接繼續進行[對應程式準備](mapper-prep.md)。

## 檢閱發現 {#review}

選取要檢視其詳細資訊的發現專案，包括：

* 結果的說明
* 元件目前的設定
* 在哪裡使用元件，包括在tags屬性和Adobe Analytics中

每個結果都包含建議的動作，視結果型別而定。 例如，對於沒有參考的資料元素，建議的動作是將其停用。

>[!IMPORTANT]
>
>標籤為未使用的資料元素可能仍會動態參照，或從標籤外部參照。 在您接受結果之前，請檢查其建議的變更、自訂程式碼、動作順序和參考，以確認它們會保留您想要的行為。

## 解決發現 {#resolve}

當您採取發現專案的建議動作時，該發現專案即會被接受。 升級小幫手會將變更新增至移轉，並在您[完成移轉](final-review.md#finalize)時套用變更。 如果您不想進行變更，請改為拒絕結果。

如果您改變心意，可以重新開啟已接受或已拒絕的發現。 若要一次更新數個發現，請在清單中選取它們。
