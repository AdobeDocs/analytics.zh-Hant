---
description: Analytics和Audience Manager都使用區段。 不過，Analytics區段與Audience Manager區段不完全相同。 這些差異會部分導致您在Analytics和Audience Manager報表中看到的差異。 因此，當您開始使用這兩個解決方案中的區段時，請務必試用並了解這些差異之處，這是十分有用的。
title: 了解 Analytics 和 Audience Manager 中的區段
feature: Audience Analytics
exl-id: 2bc662e7-7552-41e1-9d4a-bc7aa81b8c1d
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 22%

---

# 了解 Analytics 和 Audience Manager 中的區段

Analytics和Audience Manager都使用區段。 不過，Analytics區段與Audience Manager區段不完全相同。 這些差異會部分導致您在Analytics和Audience Manager報表中看到的差異。 因此，當您開始使用這兩個解決方案中的區段時，請務必試用並了解這些差異之處，這是十分有用的。

## Audience Manager 區段 {#aam-segments}

Audience Manager區段是一組訪客（使用者ID），符合由邏輯規則聯結的已定義特徵集。 有四項標準可判斷訪客 (使用者 ID) 是否為 Audience Manager 區段的一部分：

* 對區段本身設定的規則，以及構成每個區段的特徵。 這些規則會定義使用者ID必須符合或必須具備區段資格的條件。
* 演算法塑型。根據演演算法建模和分析，符合特定區段資格的使用者可能符合其他區段的資格。
* 存留時間(TTL)間隔。 區塊會籍可在設定的間隔後到期，或無限期繼續。
* 使用間隔和頻率。 定義使用者何時及多久進行互動（特徵實現）有助於根據網站、區域或特定創意內容的實際（或感知）興趣水準建立區段。

Audience Manager區段會籍不穩定。 使用者可依據其在目前時間點是否符合區段條件而輸入或退出區段。 這表示Audience Manager區段的母體數量可能會隨著時間增加或減少。

Audience Manager區段在Analytics中稱為受眾。

如需詳細資訊，請參閱區段產生器[中的](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=zh-Hant)特徵和區段母體資料，以及[訊號、特徵和區段](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html?lang=zh-Hant)。

## Analytics 區段 {#analytics-segments}

Analytics區段是報表中資料的篩選機制。 您可以在訪客、造訪或點擊層級進行篩選，有別於 Audience Manager 僅限定在訪客層級篩選。將 Analytics 區段與 Audience Manager 區段進行比較時，需考量到幾個重要因素：

* Analytics區段與Audience Manager區段運作於不同的資料集。 在資料收集期間，Analytics會將許多不同的後處理步驟套用至Audience Manager無法使用的資料。 後續處理可包括eVar持續性、處理規則、查詢（地理位置、行動裝置）、VISTA和許多其他。 Audience Manager會透過伺服器端轉送(或DIL)接收預先處理的資料。

  將根據Analytics從未過期之維度的區段與Audience Manager中的相同維度進行比較時，會發生常見的資料差異。 例如，永不過期的listVar或銷售eVar。

  例如，如果 eVar = blue，並且在 Analytics 中設為永不過期，則 Analytics 中標準為「eVar = blue」的所有區段將一律包含此訪客。然而，在Audience Manager中，該訪客可能在一段時間後退出類似定義的區段。

* Analytics區段的功能比Adobe Audience Manager區段多。 Audience Manager區段一律會在訪客層級進行評估。 您可以在訪客、造訪或點選層級（或這些層級的組合）定義Analytics區段。 此外，Analytics支援Audience Manager所沒有的進階分段功能，例如循序分段。

* 如前所述，Audience Manager訪客可在目前時間點，根據是否符合區段條件進入或退出區段。

  相反地，在Analytics中，將會根據報表日期範圍將訪客納入區段或從中排除。 例如，某位訪客上個月購買產品。 在Adobe Audience Manager中，無論日期範圍如何，該訪客都會包含在「購買者」區段中。 在Analytics中，根據當月的報表不會將訪客納入區段中。 不過，根據本月與上個月的報表會將此訪客納入區段中。

請參閱 [Analytics 分段指南](/help/components/segmentation/seg-home.md)，了解更多資訊。
