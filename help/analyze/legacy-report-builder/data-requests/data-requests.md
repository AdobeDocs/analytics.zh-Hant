---
description: 在 Report Builder 中建立請求時的第一個步驟。
title: 資料請求 - 請求精靈步驟 1
feature: Report Builder
role: User, Admin
exl-id: 698662a8-8b6b-4338-a315-b41cf6a9424e
TQID: https://experienceleague.adobe.com/87MzdxBePRZKBttF3P6XhuDq5hR6XpEWaLdrYDMu-5Y
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 401
ht-degree: 57%

---

# 資料請求 - 請求精靈步驟 1

{{legacy-arb}}

在「請求精靈: 步驟 1」表單中，您可以選擇報表套裝、報表類型、區段及設定日期。

![顯示「請求精靈：步驟1」表單的熒幕擷圖。](assets/rw1_overview.png)

1. **[!UICONTROL 報表套裝]**：根據您的登入認證，可供您使用的報表套裝清單。 請參閱[選取報表套裝](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)。

1. **範圍選擇器**：可讓您從Excel的儲存格中選取報表套裝ID。 請參閱[選取報表套裝](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)。

1. **區段**：區段是自訂資料子集，或由您建立之規則所篩選的資料。 區段是以點選、造訪和訪客為基礎。 如需區段的詳細資訊，請參閱[Analytics分段指南](/help/components/segmentation/seg-home.md)。

   例如，您可以執行[!UICONTROL 頁面報告]，然後套用首次瀏覽次數區段。

1. **允許發佈清單覆寫**：發佈清單是Reports &amp; Analytics中的功能，已經是[生命週期結束](https://new.express.adobe.com/webpage/WFCyq7w8kijmB？)。

1. **報表型別**：指定要在資料要求中執行的基礎報表。 您針對每個請求執行一個報表，而該報表可包含一對多維度和一對多量度。 報表型別的量度和維度會顯示在[!UICONTROL 請求精靈；步驟2]介面中。 請參閱[選取報表型別](/help/analyze/legacy-report-builder/data-requests/c-report-types/select-report-types.md)。

1. **日期範圍**：定義請求所涵蓋的時間範圍。 有數種型別的請求時段可供使用，例如預設集、固定和滾動。 句點數上限為366。 您也可以選擇由儲存格指定的日期範圍，然後再將日期範圍儲存為範本以供日後使用。  請參閱[設定報表日期](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md)。

1. **套用顆粒度**：指定報表所包含之時間詳細資料的等級。 請參閱[顆粒度](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/granularity.md)。

## 疑難排解

請求精靈有時會出現在畫面外，尤其是針對在螢幕設定之間移動的使用者。 例如，您工作時使用桌上型電腦，在家中使用筆記型電腦螢幕。 如果您在已開啟請求精靈時再次按一下「建立」，會出現下列錯誤：

「您必須先完成請求精靈程序，才能開始新的程序。」

將請求精靈移回畫面上即可解決此問題。

1. 開啟 Microsoft Excel 並登入 Report Builder。
2. 按一下[!UICONTROL 「建立」]就會在畫面外開啟請求精靈。
3. 按下 `[Alt]` + `[Space]`。
4. 按下 `[M]`。
5. 按任意方向鍵。
6. 移動滑鼠，這會將請求精靈加到游標上
7. 按一下滑鼠即可將請求精靈放到螢幕上。
