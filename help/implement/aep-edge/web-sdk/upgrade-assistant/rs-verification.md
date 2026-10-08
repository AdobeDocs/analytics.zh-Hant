---
title: 在網頁SDK升級助理中驗證報表套裝
description: 檢閱報表套裝中的Analytics變數，並選擇要轉入XDM對應的變數。
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
source-wordcount: '510'
ht-degree: 0%
---
# 報表套裝驗證

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_rsverification"
>title="報表套裝驗證"
>abstract="檢閱標籤屬性傳送至每個報表套裝的Analytics變數。 您在此處選取的變數會結轉到XDM對應。 使用標籤檢查最近使用的資料、尋找重複變數，以及在報表套裝間比較設定。"

<!-- markdownlint-enable MD034 -->

升級助理可識別您的標籤屬性傳送資料的目標報表套裝，然後將實施中的Analytics變數與每個報表套裝的設定和最新資料進行比較。 使用此步驟來決定哪些變數可結轉到[XDM對應](xdm-mapping.md)。

Upgrade Assistant會使用您的報表套裝來瞭解您的實施所設定的變數及其設定方式。 活動資料涵蓋過去90天。

## 變數活動 {#variable-activity}

**[!UICONTROL 變數活動]**&#x200B;索引標籤會列出您選擇在[變數分析](#variable-analysis)中對應的報表套裝的Analytics變數，並顯示每個變數是否在過去90天內收集資料。

您選取的變數會結轉到XDM對應。 請考慮清除不再收集資料的變數，或清除您不需要在網頁SDK實作中的變數。 沒有最近活動的變數可能仍在使用中（例如，如果是季節性變數或低流量），在清除前請確認您不需要變數。

對於您結轉的每個清單變數和清單屬性，輸入分隔其值的分隔字元。 升級助理無法從Adobe Analytics取得分隔字元，而且您必須每個分隔字元都有分隔字元，才能繼續。

## 變數分析 {#variable-analysis}

如果您的標籤屬性傳送資料至多個報表套裝，請先選擇要對應的報表套裝。 **[!UICONTROL 變數分析]**&#x200B;標籤接著會標籤在您對應之前可能需要決定的變數：

* 看起來會收集相同資料的變數。 確認擷取到的資訊相同，然後決定是否將其合併為單一變數，或將其分開。
* 最近未收集資料的變數。
* 值全部為「未指定」的變數。

## 比較報表套裝 {#compare}

如果您的標籤屬性傳送資料至多個報表套裝，**[!UICONTROL 比較報表套裝]**&#x200B;索引標籤會比較這些報表套裝中最多三個的每個變數設定。 使用它將報表套裝對應至結構之前，找出在報表套裝之間設定不同的變數。

## 更新報表套裝資料 {#refresh}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_rsverification_refresh"
>title="重新整理報表套裝資料"
>abstract="再次檢查連結至此標籤屬性的報表套裝，包括其變數設定和最近使用的資料，然後重新執行變數分析。 如果升級助理尚未找到任何報表套裝，會先在標籤屬性中尋找它們。 您的選擇與決定都會保留。"

<!-- markdownlint-enable MD034 -->

您可以在此步驟中變更升級助理分析的報表套裝。 如果您的報表套裝組態在移轉過程中變更，請選取&#x200B;**[!UICONTROL 重新整理報表套裝資料]**&#x200B;以重新執行分析。 升級小幫手會保留您現有的選擇與決定。

完成後，選取[儲存並繼續] **以移至[XDM對應](xdm-mapping.md)。**
