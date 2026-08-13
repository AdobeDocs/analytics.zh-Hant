---
description: 瞭解如何將標準和有限的格式套用至儲存格範圍。
title: 如何在Report Builder中格式化日期
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
feature: Report Builder
role: User, Admin
exl-id: 9b251b09-9156-40b5-8e1f-fb6594a25c26
TQID: https://experienceleague.adobe.com/8FuosvmSvi-bRNaG5QbwUExuDffOIXbrkuiQLh0NZXM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 271
ht-degree: 24%

---

# 格式化日期

{{legacy-arb}}

除了可透過Excel的「格式>儲存格(Ctrl+1)」功能使用的標準儲存格格式選項外，您還可以透過Report Builder將有限的格式套用至儲存格範圍。 這些格式選擇取決於您選擇的量度。

[新增維度](/help/analyze/legacy-report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md)至「列標籤」格線後，請按一下&#x200B;**[!UICONTROL 「格式」]**。

在「**[!UICONTROL 格式]**」功能表中按一下「**[!UICONTROL 自訂格式]**」以套用日期的自訂格式，其形式與在開頭和結尾附加文字的功能相似。 例如，您可以輸入始終在日期之後發生的文字（例如A.D. B.C.E. A.H.等）。 您可以在日期之前新增文字，例如[!UICONTROL 開始日期]和[!UICONTROL 開始和結束日期]。 此外，您可以建構從日、月、年縮寫的自訂日期運算式，並在日期各部分之間使用自訂分隔符號。 所有日期格式都必須由三個縮寫組成，且必須括在方括弧中。

下表說明如何在[!UICONTROL 「自訂格式」]欄位中使用日期縮寫：

| 縮寫 | 含義 | 使用2012年3月14日星期三的範例 |
|--- |--- |--- |
| MM/dd/yyyy | 完整數值日期 | 03/14/2012 |
| M | 月數 | 3 |
| 公厘 | 月份數&lt; 10，帶有0個邊框間距 | 03 |
| MMM | 月份的簡短名稱 | 3 月 |
| MMMM | 月份的完整名稱 | 3 月 |
| D | 日期的完整名稱 | 2012年3月14日，星期三 |
| d | 天數 | 14 |
| dd | 天數，0以內距&lt; 10表示 | 01 - 09 |
| ddd | 日的簡短名稱 | 週三 |
| dddd | 一天的完整名稱 | 星期三 |
| yy | 2位數年份 | 10 |
| yyyy | 完整4位數年份 | 2012 |
