---
title: 搜尋關鍵字
description: 訪客用來存取您的網站的搜尋關鍵字。
feature: Dimensions
exl-id: 5a1236a6-f94b-4679-906a-b539afe36887
TQID: https://experienceleague.adobe.com/4naavrC42ddsxGFJfkOJ0wzHLTa7tdMeI9nKDgVWrBY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 70%
---
# 搜尋關鍵字

「搜尋關鍵字」[維度](overview.md)會報告訪客用來存取您的網站的搜尋關鍵字。

>[!IMPORTANT]
>
>隨著隱私權實務趨於嚴謹，大部分的搜尋引擎不再傳遞搜尋關鍵字。 Adobe 已辨識出搜尋引擎但缺少關鍵字的點擊，會歸類到維度項目 `"Keyword unavailable"` 下。

反向連結必須符合下列兩個條件，才能分類為搜尋關鍵字：

* 反向連結網域經 Adobe 認可為有效的[搜尋引擎](search-engine.md)；
* 反向連結 URL 中存在關鍵字查詢字串參數。 如果關鍵字查詢字串存在，但不含任何值，則會歸類到維度項目 `"Keyword unavailable"` 下。

如果您想要區分付費和免費搜尋，必須使用[付費搜尋偵測](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md)。 搜尋關鍵字可使用多個維度：

* **搜尋關鍵字**：用來存取您的網站的搜尋關鍵字，無論是付費還是免費。
* **搜尋關鍵字 - 付費**：用來存取您的網站的搜尋關鍵字 (符合付費搜尋偵測)。
* **搜尋關鍵字 - 免費**：用來存取您的網站的搜尋關鍵字 (不符合付費搜尋偵測)。

## 將資料填入此維度中

Adobe從每個點選的搜尋引擎[反向連結](referrer.md)衍生此維度，從反向連結的查詢字串擷取關鍵字。 沒有可設定的變數。 因為每個值都相依於反向連結，請確定反向連結維度和[內部URL篩選器](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)已正確設定。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（衍生自搜尋引擎反向連結） |
| **網頁SDK / XDM欄位** | 無（衍生自搜尋引擎反向連結） |
| **查詢引數** | 不適用 |
| **XML標籤** | 不適用 |
| **位元組限制** | 不適用 |
| **持續性** | 不適用 |

## 維度項目

維度項目包含用來存取您的網站的搜尋關鍵字。 `"Unspecified"` 維度項目是所有非搜尋流量。
