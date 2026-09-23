---
title: 找不到頁面 (維度)
description: 在您的網站上傳回錯誤的 URL。
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
TQID: https://experienceleague.adobe.com/0S2WzNRJrtOa9ZPTg5cmbwxMLJE5tI6Qa3GtZs6GqKc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 50%
---
# 找不到頁面

>[!BEGINSHADEBOX]

*此說明頁面說明「找不到頁面」作為[維度](overview.md)時的運作方式。 請參閱[找不到頁面](../metrics/pages-not-found.md)量度頁面，瞭解它作為量度時的運作方式。*

>[!ENDSHADEBOX]

「找不到頁面」維度會顯示包含錯誤的 URL。 如果您想要減少訪客在您網站上收到的錯誤數，此維度就十分實用。

* 您可以在[流量視覺效果](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)中使用此維度，以查看訪客在點進哪些頁面之後遇到錯誤。 然後，您可以與組織中的開發團隊合作，以修正每個頁面上的連結。
* 您可以將此維度與[反向連結](referrer.md)維度搭配使用，以查看訪客從何處透過外部連結到達您的網站。 然後，您可以實作重新導向連至所需的位置，或與第三方合作以修正連結。

>[!NOTE]
>
>在Data Warehouse中，此維度名為&#39;[!UICONTROL 頁面型別錯誤]&#39;。

## 將資料填入此維度中

AppMeasurement 會使用 [`pageType`](/help/implement/vars/page-vars/pagetype.md) 變數收集這項資料。 當`pageType`設為`errorPage`時，點選的頁面URL會記錄為維度專案。 如果未定義`pageType`變數或將其設定為任何其他值，則不會收集此維度的資料。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | [`pageType`](/help/implement/vars/page-vars/pagetype.md) |
| **網頁SDK / XDM欄位** | [`web.webPageDetails.isErrorPage`](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/data-types/webpage-details) |
| **查詢引數** | [`pageType`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML標籤** | [`<pageType>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **位元組限制** | 不適用 |
| **持續性** | 點擊 |

## 維度項目

維度項目包含您的網站上發生錯誤之頁面的 URL。
