---
title: 反向連結網域
description: 訪客點進您的網站前所在的上層網域。
feature: Dimensions
exl-id: 9e04cb62-6526-4d84-aff7-c962c0ce42b5
TQID: https://experienceleague.adobe.com/iLpQGPuxOFmhb-WCU0EEfhmGgHgeQaPgBmOETdCczGQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 81%
---
# 反向連結網域

「反向連結網域」[維度](overview.md)會報告訪客從哪些網域點進您的網站。 此維度有助於瞭解哪些第三方網站為您帶來最多流量。 外部網站上必須有連結，且訪客必須點按該連結，才會顯示維度項目。

>[!IMPORTANT]
>
>您必須設定報表套裝的[內部 URL 篩選器](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)，才能使用此維度。 若未設定內部 URL 篩選器，則可能納入內部網域，或使外部網域無法顯示。

相同的報告在 Analysis Workspace 和 Data Warehouse 中可能會顯示不同的結果。 Analysis Workspace 會報告每個個別頁面的反向連結網域，排除與內部 URL 篩選器相符的值。 Data Warehouse 只會報告造訪的第一個反向連結網域，並忽略內部 URL 篩選器。

## 將資料填入此維度中

Adobe會使用反向連結URL的網域部分，從每次點選的[反向連結](referrer.md)衍生此維度。 沒有可設定的變數。 您必須設定報表套裝的[內部URL篩選器](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)；若未設定，可能會包含內部網域或使外部網域無法顯示。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（衍生自反向連結） |
| **網頁SDK / XDM欄位** | 無（衍生自反向連結） |
| **查詢引數** | 不適用 |
| **XML標籤** | 不適用 |
| **位元組限制** | 不適用 |
| **持續性** | 造訪 |

Adobe 會在造訪期間保存反向連結網域。 如果訪客在單次造訪中離開並點進了不同網域的連結，新值將會更新，並持續存在於剩餘的造訪中。 如果您只想查看原始值，請參閱[原始反向連結網域](original-referring-domain.md)。

## 維度項目

維度項目包含訪客點按以進入您的網站的網域。 如果點擊沒有任何設定或保存的反向連結資料，則會歸類到維度項目 `"Typed/Bookmarked"` 下。 此維度項目表示沒有反向連結值，例如，當訪客在位址列中手動輸入瀏覽器位址，或按一下書籤時。 也會針對不符合 Analytics 的重新導向顯示 `"Typed/Bookmarked"` 維度項目。 請參閱技術使用手冊中的[重新導向與別名](/help/technotes/redirects.md)。

### 維度項目包含 `googleusercontent.com`

使用者可以看到包含 `googleusercontent.com` 網域的維度項目。

* **快取頁面**：Google 的編目程式會持續對網站進行編目，並儲存網頁的複本以防網頁離線。 按一下「已快取」連結，即可在大部分搜尋結果旁取得這些快取頁面。 使用者按一下此連結並檢視 Google 快取的內容時，`googleusercontent.com` 即為維度項目。
* **翻譯頁面**：Google 提供強大且便利的翻譯服務。 使用本服務檢視網站時，其來源為 `googleusercontent.com`。 如果使用者按一下連結返回原始內容，則會顯示此維度項目。
