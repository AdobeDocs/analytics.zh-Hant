---
title: 同意管理選擇加入
description: 查看訪客選擇加入哪些隱私設定。
exl-id: b2768180-b763-41fb-8cba-665fac047e29
feature: Dimensions
TQID: https://experienceleague.adobe.com/hvtKcglMPFz4FbInpuSs9haS5SwGNQpVWXn12M1x658
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
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 78%
---
# 同意管理選擇加入

「同意管理選擇加入」維度[維度](overview.md)會顯示訪客已選擇加入哪些隱私設定。 您可以使用此維度根據隱私設定篩選資料，或查看最常見的隱私選擇加入原因。

## 將資料填入此維度中

此維度會從以下[內容資料變數](/help/implement/vars/page-vars/contextdata.md)收集資料：

* `contextData.['opt.dmp']` 設定為 `Y` 時。 如果`opt.dmp`等於`N`，則會填入[同意管理選擇退出](cm-opt-out.md)維度。
* `contextData.['opt.sell']` 設定為 `Y` 時。 如果`opt.sell`等於`N`，則會填入[同意管理選擇退出](cm-opt-out.md)維度。

您的組織會確定實施這些內容資料變數的邏輯。 在每個頁面上設定每個內容資料變數。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（透過同意訊號設定） |
| **網頁SDK / XDM欄位** | 無 |
| **查詢引數** | 不適用 |
| **XML標籤** | 不適用 |
| **位元組限制** | 100位元組 |
| **持續性** | 點擊 |

## 維度項目

維度項目包括下列二個值：

* **`DMP`**：訪客選擇加入分享至資料管理平台。 此維度項目在內容資料變數 `opt.dmp` 等於 `Y` 時出現。
* **`SELL`**：訪客選擇加入將資料分享或銷售至第三方。 此維度項目在內容資料變數 `opt.sell` 等於 `Y` 時出現。
