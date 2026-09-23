---
title: 伺服器
description: 伺服器的名稱。
feature: Dimensions
exl-id: c2454c0d-497e-46f8-8569-7d0517097cab
TQID: https://experienceleague.adobe.com/BDVwwy3jCtHrcWLy2nOHVnDRbFiAoR-EeOzp-35XjBs
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
source-wordcount: '183'
ht-degree: 61%
---
# 伺服器

「伺服器」[維度](overview.md)通常會列出網站的主機名稱。 對於結合多個網域或子網域的報表套裝，此維度十分有助於瞭解哪些網域或子網域的效能最佳。

此維度與[頁面](page.md)和[網站區段](site-section.md)維度有關。 「頁面」最精細，「伺服器」最不精細，「網站區段」介於兩者之間。

## 將資料填入此維度中

AppMeasurement使用[`server`](/help/implement/vars/page-vars/server.md)變數收集這項資料，該變數的功能與prop相同。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | [`server`](/help/implement/vars/page-vars/server.md) |
| **網頁SDK / XDM欄位** | [`web.webPageDetails.server`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/webpage-details) |
| **查詢引數** | [`server`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML標籤** | [`<server>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **位元組限制** | 100位元組 |
| **持續性** | 點擊 |

## 維度項目

維度項目包含您網站上的伺服器。 您的組織會決定您要使用的特定維度項目。 有些組織會使用 `window.location.hostname`，有些則會制定自訂值。 無論您使用何種方法，請確保其一致性，並確實將其記錄在[解決方案設計文件](/help/implement/prepare/solution-design.md)中。
