---
description: 使用「自訂運算式」設定日期範圍時，有兩項重要事項需要考量：
title: 自訂日期考量事項
uuid: a3bb3a63-0f15-4292-ade7-4ea852fe68c8
feature: Report Builder
role: User, Admin
exl-id: 66b817b3-7e9e-4030-92f3-797e730f9661
TQID: https://experienceleague.adobe.com/7PLNffmZnNnQ2X0HgnqYa8R3zWQvFPMSM8sbWocmxH4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 415
ht-degree: 22%

---

# 自訂日期考量事項

{{legacy-arb}}

使用自訂運算式設定日期範圍時，有兩項重要事項需要考量：

* 執行報表（或更新請求的截止日期）會決定可用的資料。
* 報表開始和結束日期的變換會影響報表涵蓋的日期範圍。

由於資料可用性對報表的時間範圍以及您重新整理報表中的請求的日期都比較敏感，因此請確定您會在適當的日期執行報表，以擷取所需的資訊。 以下範例示範這兩個考量事項。

假設您使用「彙總」顆粒度來請求[!UICONTROL 頁面檢視次數]。 在北美，一週從星期日開始。 若要取得星期日至星期六期間（例如2008年11月23日至11月29日）的更新報表，請在星期日（11月30日）執行前一週的報表（11/23至11/29） （重新整理要求）。

使用此自訂運算式：

*從：* cw-1w *到：* cw-1d

以下是當請求的[!UICONTROL 「結束日期」]為 11/30 (含) 時，自訂運算式的分析：

*從：* cw-1w

當週某日從星期日開始，11月30日減七天=上週日從11月23日星期日開始

*至：* cw-1d

當週某日從11月30日星期日開始減一天= 11月29日星期六

自訂運算式對應至試算表後，請使用2008年11月30日星期日作為浮動要求的包含[!UICONTROL 結束日期]重新整理要求。 資料將反映整週時間。

如果您改為重新整理運算式，並將11月29日星期六指定為浮動請求的[!UICONTROL 結束日期]，則資料會反映11/16到11/22這一週。 這是因為請求重新整理的參考日期早了一天。

當請求的[!UICONTROL 「結束日期」]為 11/29 (含) 時，差異如下：

*從：* cw-1w

當週某日從星期日開始，11月23日減七天=上週日從11月16日星期日開始

*至：* cw-1d

當週某日從11月23日星期日開始減一天= 11月22日星期六

在歐洲和其他一些國家，一週從星期一開始，而不是星期日。 在這種情況下，您可以自訂日曆來變更開始日期 （請參閱[自訂行事曆](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md)。）
