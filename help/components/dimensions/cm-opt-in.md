---
title: 同意管理選擇加入
description: 查看訪客選擇加入哪些隱私設定。
source-git-commit: 49b2c144fea5786564ccb6dc70adead3bc669596
workflow-type: ht
source-wordcount: '182'
ht-degree: 100%

---

# 同意管理選擇加入

「同意管理選擇加入」維度顯示訪客選擇加入哪些隱私設定。您可以使用此維度根據隱私設定篩選資料，或查看最常見的隱私選擇加入原因。

## 將資料填入此維度中

此維度會從以下[內容資料變數](/help/implement/vars/page-vars/contextdata.md)收集資料：

* `contextData.['opt.dmp']` 設定為 `Y` 時。如果`opt.dmp`等於`N`，則會填入[同意管理選擇退出](cm-opt-out.md)維度。
* `contextData.['opt.sell']` 設定為 `Y` 時。如果`opt.sell`等於`N`，則會填入[同意管理選擇退出](cm-opt-out.md)維度。

您的組織會確定實施這些內容資料變數的邏輯。這類變數在其設定所在的點擊過後即不存在，因此您必須在每個頁面上設定每個內容資料變數。

## 維度項目

維度項目包括下列二個值：

* **`DMP`**：訪客選擇加入分享至資料管理平台。此維度項目在內容資料變數 `opt.dmp` 等於 `Y` 時出現。
* **`SELL`**：訪客選擇加入將資料分享或銷售至第三方。此維度在內容資料變數 `opt.sell` 等於 `Y` 時出現。