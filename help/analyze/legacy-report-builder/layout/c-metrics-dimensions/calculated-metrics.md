---
description: Report Builder 5.2支援Adobe Analytics統一計算量度。 除了其他創新項目以外，現在所有計算量度都有全域 ID，不再侷限於單一報表套裝。
title: 計算量度
feature: Report Builder
role: User, Admin
exl-id: 462086eb-675f-443c-b3a6-b4fa390254da
TQID: https://experienceleague.adobe.com/Ae-k-aIMg3n3kXYWFngOzYihtlexLCoD5CmnEN3afhI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 396
ht-degree: 22%

---

# 計算量度

{{legacy-arb}}

Report Builder 5.2和更新版本支援Adobe Analytics計算量度。 現在，所有計算量度都有全域ID，不再侷限於單一報表套裝。

>[!NOTE]
>
>現有活頁簿可能會指向使用舊式量度 ID 的請求。 當您使用Report Builder 5.2時，這些舊式量度ID將會轉換為新的全域ID。 如果您將此活頁簿共用給Report Builder v5.1或較舊版本的使用者，該使用者將無法看到計算量度。

若要進一步瞭解如何使用新的計算量度產生器和管理器來建立和管理計算量度，請參閱[計算量度](/help/components/calculated-metrics/cm-overview.md)指南。

在「請求精靈」的步驟2中，您可以篩選及套用計算量度。

## 篩選計算量度 {#section_376E986D3E684999A7CDB08E53854159}

**按一下「篩選」圖示來篩選**&#x200B;計算量度： ![顯示「應用程式」、「使用者」、「專案」欄位的「篩選」選項熒幕擷圖。](/help/admin/tools/assets/filter.png)

「進階篩選器」對話方塊中會同時填入標準和計算量度。

可用的篩選條件包括：

![熒幕擷圖顯示下表描述的「進階篩選」選項。](assets/advanced_filters.png)

| 篩選器名稱 | 說明 |
|---|---|
| 標記 | 可讓您篩選具有特定標籤的計算量度。 請注意，標籤篩選器會使用AND運運算元。 如果您檢查兩個標籤，右窗格會顯示已使用&#x200B;**both**&#x200B;標籤標籤的量度。 |
| 報表套裝 | 如果您在 *的「計算量度產生器」中套用「僅*&#x200B;報表套裝名稱[!DNL Adobe Analytics]」篩選條件，接著在 [!DNL Report Builder] 中顯示「進階篩選器」，則進階篩選器只會顯示所選報表套裝的計算量度。 |
| 所有者 | 可讓您依擁有者篩選量度。 請注意，擁有者篩選器會使用OR運運算元。 如果檢查兩個擁有者，右窗格會顯示&#x200B;**任一**&#x200B;擁有者擁有的量度。 |
| 其他篩選器>已核准 | 顯示所有正式核准的量度。 |
| 其他篩選器>我的最愛 | 顯示所有標示為我的最愛的量度。 |
| 其他篩選器 > 我的 | 顯示您擁有的所有量度。 |
| 其他篩選器 > 與我共用 | 顯示其他人與您共用的所有量度。 |

## 套用計算量度 {#section_DF5CF349460A45FDA4B6E6BB8B52F18E}

選取篩選器後，按一下&#x200B;**[!UICONTROL 套用]**&#x200B;以套用至您的請求。 選取的量度現在已新增至報表版面配置。

![熒幕擷圖顯示「請求精靈：步驟2 — 網站總計」，指向「進階篩選器」視窗並套用報表量度。](assets/filtering_for_metric.png)
