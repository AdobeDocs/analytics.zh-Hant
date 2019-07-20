---
description: 瞭解如何為渠道指派成本和預算額。
seo-description: 瞭解如何為渠道指派成本和預算額。
seo-title: 成本與預算
solution: Analytics
subtopic: 行銷渠道
title: 成本與預算
topic: Reports & Analytics
uuid: 7ba0e968-e565-4d4 c-8fc0-39fc25 d3 e5 b1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 成本與預算

瞭解如何為渠道指派成本和預算額。

## Costs and budgets {#topic_7CCFD3B54440433FBA0E4EE127F58B0C}

瞭解如何為渠道指派成本和預算額。

成本表示您對渠道的花費。預算表示可花費的金額。

檢視 ROI 的便利方法是建立顯示收入減去成本的計算量度。或者建立一個顯示總成本以及每項新增參與成本劃分的計算量度。例如，您可以透過建立計算量度，執行顯示新增參與的[!UICONTROL 「首次接觸渠道」]報表，然後新增「首次接觸成本」量度，顯示每項新增參與的成本。

請參閱[計算量度使用行銷渠道報表](../../components/c-marketing-channels/c-channel-calc-metrics.md#topic_4521D324A79E43EF99E69FCDE1E92F74)。

僅可為渠道指定成本和預算。所有成本均設定有套用於匯報的時間範圍。當成本與渠道直接相關聯時，選擇分配量度來顯示成本針對渠道內促銷活動的劃分方式。

新增成本和預算項目後，即可將表格資料匯出至 CSV 檔案。您亦可將 CSV 檔案匯入「行銷渠道成本」頁面。

## 新增成本和預算項目 {#task_9238A033994440748960DE21593E6388}

新增成本和預算項目至行銷管道。

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. 在[!UICONTROL 「報告套裝管理員」]頁面上，選擇一個報告套裝。
1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Marketing Channels]** &gt; **[!UICONTROL Marketing Channel Costs]**.
1. On the [!UICONTROL Marketing Channel Costs] page, click **[!UICONTROL Add Cost Item]** or **[!UICONTROL Add Budget Item]**.
1. Click **[!UICONTROL Save.]**

   To continue adding cost items, click **[!UICONTROL Save and Add Another]**.

1. (Optional) To export or import CSV files, access the [!UICONTROL Marketing Channel Costs] page, click **[!UICONTROL Export File]** or **[!UICONTROL Import File]**, then follow the prompts.

## Marketing Channel costs - definitions {#reference_0B193210E10A4B6B84A385A781FD9515}

行銷渠道成本或預算的欄位定義



| 欄位 | 定義 |
|--- |--- |
| 名稱 | 成本或預算項目的名稱。(使用 SAINT 時，此為關鍵值。) |
| 渠道 | 想要與該金額相關聯的渠道。指定成本或預算適用於首次接觸渠道或是上次接觸渠道。將首次接觸成本額視作一個一次新增參與。上次接觸成本額用於點進次數。 |
| 日期範圍 | 想要用於該金額的時間。 |
| 類型 | 成本或預算的類型，比率或一次性成本。比率指定一個持續成本，例如每次點按的金額。一次性成本可讓您指定「分配機構」金額。例如，如果您根據點按次數分配成本，占點按總次數 60% 的附屬機構即可分配到總成本的 60%。分發機構值即您在劃分數值分類時所用的量度。 |
| 匯出檔案 | 可讓您將表格資料匯出至 CSV 檔案。 |
| 匯入檔案 | 可讓您將 CSV 檔案匯入「行銷渠道成本」頁面。 |
