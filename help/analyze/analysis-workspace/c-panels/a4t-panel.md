---
description: Analytics for Target(A4T)面板可讓您分析分析分析工作區中的Adobe Target活動和體驗。
title: Analytics for Target(A4T)面板
translation-type: tm+mt
source-git-commit: f9190c15da2d94b3c9006f973fa4aef92162ff04
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 14%

---


# Analytics for Target(A4T)面板

「Analytics for Target」(A4T) 面板可讓您在 Analysis Workspace 中分析 Adobe Target 活動和體驗。此外，您還可以檢視最多3個成功度量的提升度與信賴度。 若要存取A4T面板，請導覽至已啟用A4T元件的報表套裝。 然後，按一下最左側的面板圖示，並將「Analytics for Target」面板拖曳至您的分析工作區專案中。

## 面板輸入 {#Input}

您可以使用下列輸入設定來設定A4T面板：

| 設定 | 說明 |
|---|---|
| 目標活動 | 從「目標活動」清單中選取，或從左側導軌拖放活動。<br>**注意：**清單會填入至少有1次點擊的最後6個月活動。 如果您在清單中未看到任何活動，則可能會超過6個月。 它仍然可以從左側導軌中添加，其回顧期最長為18個月。 |
| 控制體驗 | 選擇您的控制體驗。 您可以視需要在下拉式清單中變更它。 |
| 標準化量度 | 從「獨特訪客」、「瀏覽」或「活動印象」中選擇。 建議在大多數分析使用案例中使用獨特訪客。 此量度（也稱為計算方法）會成為提升度計算的分母。 也會影響在套用可信度計算前彙總資料的方式。 |
| 成功度量 | 從下拉式清單中選取最多3個標準（非計算）成功事件，或從左側導軌拖放度量。 每個量度在轉譯面板中都會有專屬的表格和視覺化。 |
| 日曆日期範圍 | 這會根據Adobe Target的活動日期範圍自動填入。 如有需要，您可加以變更。 |

![面板產生器](assets/a4t-panel-builder.png)

## 面板輸出 {#Output}

「Analytics for Target」面板會傳回一組豐富的資料和視覺化，協助您更清楚瞭解Adobe Target活動和體驗的執行方式。 在面板的頂部，會提供摘要行以提醒您選取的面板設定。 您隨時可以按一下右上方的編輯鉛筆來編輯面板。

針對您選取的每個成功度量，會顯示一個自由表格和一個轉換率趨勢：

![已呈現](assets/a4t-rendered.png)


每個自由表格都會顯示下列量度欄：

| 量度 | 說明 |
|---|---|
| 標準化量度 | 獨特訪客、瀏覽或活動印象。 |
| 成功度量 | 產生器中選取的量度 |
| 轉換率 | 成功度量／標準化度量 |
| 提升度 | 對照控制體驗來比較每一個體驗的轉換率。<br>**注意：**提升度是Target體驗的「鎖定量度」; 無法劃分或與其他維度搭配使用。 |
| 提升度 (下限) | 代表變異數體驗對控制的最差提升度。 |
| 提升度 (中) | 代表 95% 信賴區間中，變異數體驗對控制的中點提升度。這是「報告與分析」中的「提升度」。 |
| 提升度 (上限) | 代表變異數體驗對控制的最佳提升度。 |
| 可信度 | 學生t-test會計算信賴等級，指出如果再次執行測試，結果重複的可能性。 量度已套用75%/85%/95%的固定條件格式範圍。 如果需要，可在「欄設定」下自訂此格式。 <br>**注意：**信賴度是Target體驗的「鎖定量度」; 無法劃分或與其他維度搭配使用。 |

與分析工作區中的任何面板一樣，您可以新增其他表格和視覺化來 [繼續分析](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) ，以協助您分析Adobe Target活動。

## 常見問題解答 {#FAQ}

| 問題 | 回答 |
|---|---|
| A4T支援哪些活動類型？ | [進一步瞭解](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-activity-setup.html) ，支援哪些活動類型。 |
| 提升度和信賴度計算中是否支援計算量度？ | 不可以，[進一步瞭解](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence.html) 「提升度與信賴度」中為何不支援計算量度。 不過，計算量度可用於這些量度以外的A4T報表。 |
| 為什麼Target和Analytics之間會有不同的獨特訪客？ | [進一步瞭解](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports.html) ，產品之間的獨特訪客差異。 |
| 當我在分析中套用特定Target活動的點擊區段時，為什麼會看到傳回的不相關體驗？ | A4T維度是清單變數，這表示它可同時包含許多活動（和體驗）。 [更多詳情](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports.html) |
| 信賴度量是否可計算極端訂單，或套用Bonferroni修正多個選件？ | 不可以，[進一步瞭解](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence.html) Analytics如何計算信心。 |

如需Analytics for Target報表的詳細資訊，請造 [訪A4T報表](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/reporting.html)
