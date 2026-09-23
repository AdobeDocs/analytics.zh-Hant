---
title: 頁面 URL
description: 頁面的 URL。
feature: Dimensions
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
TQID: https://experienceleague.adobe.com/Qek7BUR15HjFpK-XaYQ-J9fkJQiBfNi-ZoqXqaACP0A
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
source-wordcount: '238'
ht-degree: 52%
---
# 頁面 URL

「頁面URL」[維度](overview.md)會列出您網站上的URL。

>[!IMPORTANT]
>
>此維度僅在 Data Warehouse 中可用。 如果您想要在其他 Analytics 解決方案中使用 URL 維度，請考慮在每次點擊時將數值複製到 [eVar](evar.md)。

## 將資料填入此維度中

AppMeasurement會在每個[頁面檢視呼叫(`t()`)](/help/implement/vars/functions/t-method.md)上自動收集頁面URL。 您可以覆寫使用 [`pageURL`](/help/implement/vars/page-vars/pageurl.md) 變數收集的數值。 如果URL的長度超過255個位元組，則溢位會儲存在`-g`查詢字串引數中。 URL中包含通訊協定和查詢字串。 [連結追蹤呼叫(`tl()`)](/help/implement/vars/functions/tl-method.md)一律會移除此維度，即使URL值存在也一樣。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | [`pageURL`](/help/implement/vars/page-vars/pageurl.md) |
| **網頁SDK / XDM欄位** | [`web.webPageDetails.URL`](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/data-types/webpage-details) |
| **查詢引數** | [`g`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML標籤** | [`<pageUrl>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **位元組限制** | 255位元組（沒有固定的上限和溢位） |
| **持續性** | 點擊 |

## 將 URL 填入 eVar 中

Adobe 建議將 eVar 設為串連字串 `window.location.hostname + window.location.pathname`。 此字串的效用通常會優於 `window.location.href`，因為它省略了通訊協定、查詢字串和錨點標記。

如果您想要讓 eVar 完全符合 Data Warehouse 中的「頁面 URL」維度，您可以使用[動態變數](/help/implement/vars/page-vars/dynamic-variables.md)，並將 eVar 設為每個點擊上的 `D=g`。

## 維度項目

維度項目包含您網站上的頁面 URL。
