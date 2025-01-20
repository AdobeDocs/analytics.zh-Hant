---
description: 使用「摘要數字」和「摘要變更」視覺效果來呈現專案中的重要資料點。
title: 摘要數字和摘要變更
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
feature: Visualizations
role: User, Admin
exl-id: d6a08201-ca3a-48ff-983a-3ec6b989deda
source-git-commit: 76abe4e363184a9577622818fe21859d016a5cf7
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 93%

---

# [!UICONTROL 摘要數字]和[!UICONTROL 摘要變更]

_本文記錄了_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;中的摘要編號和摘要變更視覺效果。_<br/>_檢視此文章的_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;版本的[摘要編號和摘要變更](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/summary-number-change)。_

以下是有關這兩個視覺效果的影片：

>[!VIDEO](https://video.tv.adobe.com/v/335564/?quality=12)

## [!UICONTROL 摘要數字]視覺效果 {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="摘要數字"
>abstract="建立顯示總計和小計的視覺效果。"

<!-- markdownlint-enable MD034 -->

使用[!UICONTROL 摘要數字]視覺效果可強調專案中重要的大數字。 此視覺效果的運作方式如下：

* 如果未選取儲存格，則會選取該欄的總計。
* 如果選取單一儲存格，則會顯示該儲存格的摘要。
* 如果選取多個儲存格，則會顯示第一個選取的儲存格。
* 如果選取欄，則會挑選欄中第一個儲存格的值。

按一下右上角的&#x200B;**「視覺效果設定」**&#x200B;齒輪，設定「摘要數字」設定：

| 設定 | 定義 |
|--- |--- |
| [!UICONTROL 百分比] | 顯示百分比而非原始數字。 |
| [!UICONTROL 可見圖例] | 顯示所顯示量度的相關資訊。 |
| [!UICONTROL 縮簡值] | 選擇此選項即可縮簡值，最多可顯示 3 位小數位數。 |
| [!UICONTROL 值摘要依據] | 選擇此選項即可顯示一系列資料的最大值、最小值、平均值、中間值或總和。 |

## [!UICONTROL 摘要變更]視覺效果 {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="摘要變更"
>abstract="建立顯示兩個數字之間的差異 (變化) 的視覺效果"

<!-- markdownlint-enable MD034 -->

使用[!UICONTROL 摘要變更]視覺效果可顯示兩個數字間的差異 (變更)。 可透過[自訂事件極性](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md)或計算量度的[顯示上升趨勢的方式](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=zh-Hant)選項，控制[!UICONTROL 摘要變更]的綠色和紅色。

此視覺效果的運作方式如下：

* 如果未選取儲存格，則會比較欄中前兩個儲存格的值。
* 如果選取一個儲存格，由於與自身比較儲存格的值，因此會顯示 0。
* 如果選取兩個儲存格，會取第一個選取的儲存格為分子，第二個選取的儲存格為分母。
* 如果選取超過兩個儲存格，僅會比較前兩個選取的儲存格。
* 如果選取某個範圍中的儲存格，會比較該範圍第一個與最後一個選取的儲存格。
* 如果選取欄，會就第一個值的本身進行比較，顯示變更為 0。


![](assets/summary-change.png)


按一下右上角的&#x200B;**「視覺效果設定」**&#x200B;齒輪，設定「摘要變更」設定：

| 設定 | 定義 |
| --- | --- |
| [!UICONTROL 百分比] | 顯示百分比而非原始數字。 |
| [!UICONTROL 可見圖例] | 顯示所顯示量度的相關資訊。 |
| [!UICONTROL 顯示百分比變化] | 顯示 2 個數字之間的百分比變化。 |
| [!UICONTROL 顯示原始資料差異] | 顯示 2 個數字之間的原始差異。您也可以縮簡值，使用此選項顯示最多小數點後 3 位。 |
