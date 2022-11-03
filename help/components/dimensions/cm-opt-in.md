---
title: 同意管理選擇加入
description: 查看訪客選擇加入的隱私權設定。
source-git-commit: 49b2c144fea5786564ccb6dc70adead3bc669596
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 7%

---

# 同意管理選擇加入

「同意管理選擇加入」維度會顯示訪客已選擇加入的隱私權設定。 您可以使用此維度根據隱私權設定來篩選資料，或查看最常見的隱私權選擇加入原因。

## 將資料填入此維度中

此維度會從下列項目收集資料 [內容資料變數](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['opt.dmp']` 設為 `Y`. 若 `opt.dmp` 等於 `N`, [同意管理選擇退出](cm-opt-out.md) 維度會改為填入。
* `contextData.['opt.sell']` 設為 `Y`. 若 `opt.sell` 等於 `N`, [同意管理選擇退出](cm-opt-out.md) 維度會改為填入。

您的組織會決定實施這些內容資料變數的邏輯。 它們不會持續存在超過其設定所在的點擊，因此您必須在每個頁面上設定每個內容資料變數。

## 維度項目

Dimension項目包含下列兩個值：

* **`DMP`**:訪客選擇分享至資料管理平台。 上下文資料變數出現此維度項目 `opt.dmp` 等於 `Y`.
* **`SELL`**:訪客選擇分享或銷售資料給第三方。 上下文資料變數出現時，會出現此維度 `opt.sell` 等於 `Y`.
