---
title: 頁面
description: 頁面名稱。
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
TQID: https://experienceleague.adobe.com/npKfFB-zOPzNGJJ6YZvtz0oA3NDWuQiHYBraH09lc58
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
    internal-label: Attribution
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
source-wordcount: '226'
ht-degree: 54%
---
# 頁面

「頁面」[維度](overview.md)會列出您網站上的頁面名稱。 這是 Adobe Analytics 中最常使用的維度之一，因為它可讓您洞察網站上的哪些頁面表現最佳。

此維度與[網站區段](site-section.md)和[伺服器](server.md)維度有關。 「頁面」最精細，「伺服器」最不精細，「網站區段」介於兩者之間。

## 將資料填入此維度中

在[頁面檢視呼叫(`t()`)](/help/implement/vars/functions/t-method.md)中設定[`pageName`](/help/implement/vars/page-vars/pagename.md)變數。 如果未設定`pageName`變數，此維度會退回使用[`pageURL`](/help/implement/vars/page-vars/pageurl.md)變數。 [連結追蹤呼叫(`tl()`)](/help/implement/vars/functions/tl-method.md)一律會移除此維度，即使`pageName`值存在也一樣。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | [`pageName`](/help/implement/vars/page-vars/pagename.md) |
| **網頁SDK / XDM欄位** | [`web.webPageDetails.name`](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/data-types/webpage-details) |
| **查詢引數** | [`pageName`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML標籤** | [`<pageName>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **位元組限制** | 100位元組 |
| **持續性** | 點擊 |

## 維度項目

維度項目包含網站上頁面的名稱。 您的組織會決定您要使用的特定維度專案。 有些組織會直接使用 `document.title`，有些則會制定自訂的階層連結。 無論您使用何種方法，請確保其一致性，並確實將其記錄在[解決方案設計文件](/help/implement/prepare/solution-design.md)中。

>[!NOTE]
>
>Analysis Workspace 依預設會使用「最後」歸因，並提供使用任何歸因模型的選項。
