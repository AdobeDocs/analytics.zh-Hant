---
title: 搜尋引擎
description: 訪客用來存取您的網站的搜尋引擎。
feature: Dimensions
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
TQID: https://experienceleague.adobe.com/fOk6ypu24XzT6aypOHUAE-RYSW39wyrzkyt-lvOKy7Y
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
source-wordcount: '265'
ht-degree: 69%
---
# 搜尋引擎

「搜尋引擎」 [維度](overview.md)會報告訪客用來存取您的網站的搜尋引擎。 反向連結必須符合下列兩個條件，才能分類為搜尋引擎：

* 反向連結網域經 Adobe 認可為有效的搜尋引擎；
* 反向連結 URL 中存在關鍵字查詢字串參數。 查詢字串參數可以空白 (基於隱私權實務，數個搜尋引擎也是如此)。

如果您想要區分付費和免費搜尋，必須使用[付費搜尋偵測](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md)。 搜尋引擎有多個可用的維度：

* **搜尋引擎**：用來存取您的網站的搜尋引擎，無論是付費還是免費。
* **搜尋引擎 - 付費**：用來存取您的網站的搜尋引擎 (符合付費搜尋偵測)。
* **搜尋引擎 - 免費**：用來存取您的網站的搜尋引擎 (不符合付費搜尋偵測)。

## 將資料填入此維度中

Adobe從每個點選的[反向連結](referrer.md)衍生此維度，並將其與Adobe內部的多個查閱表格比對。 沒有可設定的變數。 因為每個值都相依於反向連結，請確定反向連結維度和[內部URL篩選器](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)已正確設定。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（衍生自反向連結） |
| **網頁SDK / XDM欄位** | 無（衍生自反向連結） |
| **查詢引數** | 不適用 |
| **XML標籤** | 不適用 |
| **位元組限制** | 不適用 |
| **持續性** | 不適用 |

## 維度項目

維度項目包含用來存取您的網站的搜尋引擎。 範例值包括 `"Google"`、`"Microsoft Bing"` 和 `"DuckDuckGo"`。 `"Unspecified"` 維度項目是所有非搜尋流量。
