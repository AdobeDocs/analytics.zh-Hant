---
description: Analytics 和 Audience Manager 均會使用區段。但是，Analytics 區段與 Audience Manager 區段並非完全相同。這些不同促成了您在 Analytics 和 Audience Manager 報表中看到的差異。因此，當您開始使用這兩個解決方案中的區段時，請務必試用並了解這些差異之處，這是十分有用的。
title: 了解 Analytics 和 Audience Manager 中的區段
feature: Audience Analytics
exl-id: 2bc662e7-7552-41e1-9d4a-bc7aa81b8c1d
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 91%

---

# 了解 Analytics 和 Audience Manager 中的區段

Analytics 和 Audience Manager 均會使用區段。但是，Analytics 區段與 Audience Manager 區段並非完全相同。這些不同促成了您在 Analytics 和 Audience Manager 報表中看到的差異。因此，當您開始使用這兩個解決方案中的區段時，請務必試用並了解這些差異之處，這是十分有用的。

## Audience Manager 區段 {#aam-segments}

Audience Manager區段是一組訪客（使用者ID），符合由邏輯規則聯結的已定義特徵集。 有四項標準可判斷訪客 (使用者 ID) 是否為 Audience Manager 區段的一部分：

* 區段本身設定的規則以及構成每個區段的特徵。這些規則定義了使用者 ID 必須符合或展現為符合區段的條件。
* 演算法塑型。符合特定區段的使用者，根據演算法塑型和分析，可能會符合其他區段。
* 存留時間 (TTL) 間隔。區段成員資格可以在設定的間隔後過期或無限期繼續。
* 使用間隔和頻率。定義使用者進行互動的時間和頻率 (特徵實現) 有助於根據網站、區段或特定創作的真實 (或認知) 興趣級別建立區段。

Audience Manager 的區段成員資格並非固定。使用者可以根據當前時間點是否符合區段標準，進入或退出區段。這代表著 Audience Manager 區段的人口可以隨著時間而增加或減少。

Audience Manager 區段在 Analytics 被表示為對象。

如需詳細資訊，請參閱[區段產生器中的特徵和區段人口資料](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=zh-Hant)以及[訊號、特徵及區段](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html?lang=zh-Hant)。

## Analytics 區段 {#analytics-segments}

Analytics區段是報表中資料的篩選機制。 您可以在訪客、造訪或點擊層級進行篩選，有別於 Audience Manager 僅限定在訪客層級篩選。將 Analytics 區段與 Audience Manager 區段進行比較時，需考量到幾個重要因素：

* Analytics 區段與 Audience Manager 區段的作業資料組並不相同。在資料收集過程中，Analytics 會將多種不同的後處理步驟套用至 Audience Manager 無法使用的資料中。後處理可包括 eVar 持續性、處理規則、查找 (地理位置、行動裝置)、VISTA 等等。Audience Manager 則是透過伺服器端轉送 (或 DIL) 接收預先處理資料。

  依據 Analytics 中永不過期的維度，與 Audience Manager 中的相同維度進行區段比較時，常會出現資料差異情形。例如永遠不會過期的 listVar 或銷售 eVar。

  例如，如果 eVar = blue，並且在 Analytics 中設為永不過期，則 Analytics 中標準為「eVar = blue」的所有區段將一律包含此訪客。而在 Audience Manager 中，該訪客可能會在設定的一段時間後，脫離類似定義的區段。

* Analytics區段的功能比Adobe Audience Manager區段多。 Audience Manager 區段一律在訪客層級進行評估。Analytics 區段則可以在訪客、造訪或點撃層級 (或這些層級的組合) 進行定義。此外，Analytics 也支援 Audience Manager 沒有的進階分段功能，例如依序分段。

* 如前所述，Audience Manager 訪客可以根據當前時間點是否符合區段標準，進入或退出區段。

  相反地，Analytics 會根據報表日期範圍，將訪客納入區段中或排除在外。例如，某位訪客在上個月購買過一次。在Adobe Audience Manager中，無論日期範圍如何，該訪客都會包含在「購買者」區段中。 而在 Analytics 中，此月份報表的區段中不會包含該訪客。但是，根據本月和上月的報表會將該訪客包含在區段中。

請參閱 [Analytics 分段指南](/help/components/segmentation/seg-home.md)，了解更多資訊。
