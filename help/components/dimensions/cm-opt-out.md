---
title: 同意管理選擇退出
description: 查看訪客選擇退出哪些隱私設定。
exl-id: 2bf4d22c-5b24-47fb-b489-49388fcca5b1
feature: Dimensions
TQID: https://experienceleague.adobe.com/tsMhHR84qhEUZIZjPTluCJOHMPc37-JRwLsipAycgJI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 265
ht-degree: 93%

---

# 同意管理選擇退出

「同意管理選擇退出」[維度](overview.md)顯示訪客已明確選擇退出哪些隱私設定。 您可以使用此維度根據隱私設定篩選資料，或查看最常見的隱私選擇退出原因。

## 將資料填入此維度中

此維度會從以下[內容資料變數](/help/implement/vars/page-vars/contextdata.md)收集資料：

* `contextData.['cm.ssf']` 設定為 `1` 時。 如果 `cm.ssf` 等於 `0` 或空白，此變數不會產生任何效用。
* `contextData.['opt.dmp']` 設定為 `N` 時。 如果 `opt.dmp` 等於 `Y`，則會填入[同意管理選擇加入](cm-opt-in.md)維度。
* `contextData.['opt.sell']` 設定為 `N` 時。 如果 `opt.sell` 等於`Y`，則會填入[同意管理選擇加入](cm-opt-in.md)維度。

您的組織會確定實施這些內容資料變數的邏輯。 這類變數在其設定所在的點擊過後即不存在，因此您必須在每個頁面上設定每個內容資料變數。

## 維度項目

維度項目包括下列三個值：

* **`SSF`**：訪客選擇退出[伺服器端轉送功能](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)。 此維度項目在內容資料變數 `cm.ssf` 等於 `1` 時出現。 如需詳細資訊，請參閱 Audience Manager 使用手冊中的[資料隱私概觀](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html)。 點擊不會轉送到 Adobe Audience Manager。
* **`DMP`**：訪客選擇退出分享至資料管理平台。 此維度項目在內容資料變數 `opt.dmp` 等於 `N` 時出現。 類似於 `SSF`，點擊不會轉送到 Adobe Audience Manager。
* **`SELL`**：訪客選擇退出將資料分享或銷售至第三方。 此維度項目在內容資料變數 `opt.sell` 等於 `N` 時出現。
