---
title: 維度概觀
description: 了解什麼是維度以及如何在 Adobe Analytics 中使用維度。
feature: Dimensions
exl-id: dc00e06a-fdb5-40e3-82e2-269bad3b3677
TQID: https://experienceleague.adobe.com/WypIneraYlrSyIpXv3UQWIFn42A-Dxi0SxeJ2VbeubQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 436
ht-degree: 37%

---

# 維度概觀

維度是 Adobe Analytics 中通常會包含字串值的變數。 常見的維度包括[頁面](page.md)、[反向連結網域](referring-domain.md)或 [eVar](evar.md)。 相對地，[量度](../metrics/overview.md)包含繫結至維度的數值。 基本報表會針對一個數值 (量度) 欄顯示字串值 (維度) 列。

例如，如果將「**[!UICONTROL 頁面]**」維度和「**[!UICONTROL 造訪次數]**」量度結合，您將會獲得排名報表，其中顯示您最常造訪的頁面：

| 頁面 | 造訪次數 |
| --- | ---: |
| 首頁 | 800 |
| 產品頁面 | 500 |
| 購買頁面 | 100 |

{style="table-layout:fixed"}

每個維度分別代表您的網站不同的部分或面向。 您可以將其中的一或多個維度與一或多個量度結合，以建立所需的報表。

## 新增維度說明

Analytics 管理員可以在報表套裝中或直接在 Analysis Workspace 中新增維度和其他元件的說明。 有關如何將說明新增至維度的資訊，請參閱[新增元件說明](/help/analyze/analysis-workspace/components/add-component-descriptions.md)。

## 淘汰的維度

下列維度已淘汰。 大部分的Reports &amp; Analytics報表在Analysis Workspace中無法使用。 如果您在舊版報表或歷史資料中遇到這些問題，此處會記錄這些問題以供參考。

* **階層**：自訂維度(`hier1`-`hier5`)，用來擷取網站的階層結構以進行報告。 此版本已淘汰，在Analysis Workspace中不提供。 請改用[eVar](evar.md)和分類。
* **首頁**：指出目前頁面是否為訪客瀏覽器首頁的旗標。 這是舊版維度，但由於現代瀏覽器隱私權實務而無現代相等專案。
* **JavaScript支援**：指出訪客的瀏覽器是否支援JavaScript。 對現代測量不再有意義的舊版維度。
* **JavaScript版本**：回報訪客瀏覽器支援的JavaScript版本。 不再收集的舊版維度。
* **下一頁**：路徑維度，顯示訪客檢視的下一頁。 針對目前的路徑維度使用Analysis Workspace中的[流量視覺效果](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)。
* **上一頁**：顯示訪客已檢視上一頁的路徑維度。 針對目前的路徑維度使用Analysis Workspace中的[流量視覺效果](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)。
* **時區**：訪客的時區，衍生自AppMeasurement影像要求中的時間戳記位移。 Web SDK會使用[`placeContext`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/configure/context)收集時區。
* **最上層網域**：訪客存取點的最上層網域。 舊版Reports &amp; Analytics報表；請改用[網域](domain.md)維度。
* **瀏覽頁碼**：瀏覽中的頁碼。 舊版Reports &amp; Analytics報表；請改用[點選深度](hit-depth.md)維度。
* **訪客狀態**：從`s.state`變數回報美國狀態。 已淘汰，改用使用地域劃分的[美國州](us-states.md)維度。
