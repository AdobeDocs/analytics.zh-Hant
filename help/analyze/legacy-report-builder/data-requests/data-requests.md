---
description: 在 Report Builder 中建立請求時的第一個步驟。
title: 資料請求 - 請求精靈步驟 1
feature: Report Builder
role: User, Admin
exl-id: 698662a8-8b6b-4338-a315-b41cf6a9424e
source-git-commit: ae6ffed05f5a33f032d0c7471ccdb1029154ddbd
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 90%

---

# 資料請求 - 請求精靈步驟 1

{{legacy-arb}}

在「請求精靈: 步驟 1」表單中，您可以選擇報表套裝、報表類型、區段及設定日期。

![顯示「請求精靈：步驟1」表單的熒幕擷圖。](assets/rw1_overview.png)

1. **[!UICONTROL 報表套裝]**：根據登入憑證，提供給您使用的報表套裝清單。請參閱[選取報表套裝](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)。

1. **範圍選取器**：讓您從 Excel 的儲存格選取報表套裝軟體。請參閱[選取報表套裝](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)。

1. **區段**：區段是自訂資料子集，或由您建立之規則所篩選的資料。區段是以點擊、造訪和訪客為基準。如需區段的詳細資訊，請參閱 [Analytics 分段指南](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html)。

   例如，您可以執行[!UICONTROL 頁面報告]，然後套用首次瀏覽次數區段。

1. **允許發佈清單覆寫**：發佈清單是Reports &amp; Analytics中的功能，已經是[生命週期結束](https://new.express.adobe.com/webpage/WFCyq7w8kijmB?)。

1. **報表類型**：指定要在資料請求中執行基礎報表。您可以針對每個請求執行一份報表，且報表能具有一對多維度和一對多度量。報表類型的度量和維度會顯示在「[!UICONTROL 請求精靈: 步驟 2]」介面中。請參閱[選取報表型別](/help/analyze/legacy-report-builder/data-requests/c-report-types/select-report-types.md)。

1. **日期範圍**：定義請求涵蓋的時間間隔。有幾種請求期間類型可使用，如預置、固定及遞延。期間的最大值為 366。您也可以選擇由儲存格指定的日期範圍，然後再將日期範圍儲存為範本以供日後使用。請參閱[設定報表日期](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md)。

1. **套用粒度**：指定報表所包含之時間詳細資料的等級。請參閱[粒度](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/granularity.md)。

## 疑難排解

請求精靈有時會出現在畫面外，尤其是針對在螢幕設定之間移動的使用者。例如，您工作時使用桌上型電腦，在家中使用筆記型電腦螢幕。如果您在已開啟請求精靈時再次按一下「建立」，會出現下列錯誤：

「您必須先完成請求精靈程序，才能開始新的程序。」

將請求精靈移回畫面上即可解決此問題。

1. 開啟 Microsoft Excel 並登入 Report Builder。
2. 按一下[!UICONTROL 「建立」]就會在畫面外開啟請求精靈。
3. 按下 `[Alt]` + `[Space]`。
4. 按下 `[M]`。
5. 按任意方向鍵。
6. 移動滑鼠，這會將請求精靈加到游標上
7. 按一下滑鼠即可將請求精靈放到螢幕上。
