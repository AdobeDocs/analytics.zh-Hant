---
title: 同意管理選擇加入
description: 查看訪客選擇加入哪些隱私設定。
exl-id: b2768180-b763-41fb-8cba-665fac047e29
feature: Dimensions
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 91%

---

# 同意管理選擇加入

「同意管理選擇加入」維度[維度](overview.md)會顯示訪客已選擇加入哪些隱私設定。 您可以使用此維度根據隱私設定篩選資料，或查看最常見的隱私選擇加入原因。

## 將資料填入此維度中

此維度會從以下[內容資料變數](/help/implement/vars/page-vars/contextdata.md)收集資料：

* `contextData.['opt.dmp']` 設定為 `Y` 時。如果`opt.dmp`等於`N`，則會填入[同意管理選擇退出](cm-opt-out.md)維度。
* `contextData.['opt.sell']` 設定為 `Y` 時。如果`opt.sell`等於`N`，則會填入[同意管理選擇退出](cm-opt-out.md)維度。

您的組織會確定實施這些內容資料變數的邏輯。這類變數在其設定所在的點擊過後即不存在，因此您必須在每個頁面上設定每個內容資料變數。

## 維度項目

維度項目包括下列二個值：

* **`DMP`**：訪客選擇加入分享至資料管理平台。此維度項目在內容資料變數 `opt.dmp` 等於 `Y` 時出現。
* **`SELL`**：訪客選擇加入將資料分享或銷售至第三方。此維度在內容資料變數 `opt.sell` 等於 `Y` 時出現。
