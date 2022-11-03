---
title: 同意管理選擇退出
description: 查看訪客選擇退出的隱私權設定。
source-git-commit: c305f74d5047db57509de8ff9ee03b8144009f5a
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 5%

---

# 同意管理選擇退出

「同意管理選擇退出」維度會顯示訪客明確選擇退出的隱私權設定。 您可以使用此維度根據隱私權設定來篩選資料，或查看最常見的隱私權選擇退出原因。

## 將資料填入此維度中

此維度會從下列項目收集資料 [內容資料變數](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['cm.ssf']` 設為 `1`. 若 `cm.ssf` 等於 `0` 或空白，則此變數不會執行任何動作。
* `contextData.['opt.dmp']` 設為 `N`. 若 `opt.dmp` 等於 `Y`, [同意管理選擇加入](cm-opt-in.md) 維度會改為填入。
* `contextData.['opt.sell']` 設為 `N`. 若 `opt.sell` 等於 `Y`, [同意管理選擇加入](cm-opt-in.md) 維度會改為填入。

您的組織會決定實施這些內容資料變數的邏輯。 它們不會持續存在超過其設定所在的點擊，因此您必須在每個頁面上設定每個內容資料變數。

## 維度項目

Dimension項目包含下列三個值：

* **`SSF`**:訪客選擇退出 [伺服器端轉送](/help/admin/admin/c-server-side-forwarding/ssf.md). 上下文資料變數出現此維度項目 `cm.ssf` 等於 `1`. 請參閱 [資料隱私權概觀](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html) 中，以取得詳細資訊。 點擊未轉送至Adobe Audience Manager。
* **`DMP`**:訪客選擇退出資料管理平台的共用。 上下文資料變數出現此維度項目 `opt.dmp` 等於 `N`. 類似 `SSF`，點擊不會轉送至Adobe Audience Manager。
* **`SELL`**:訪客選擇退出分享或銷售資料給第三方。 上下文資料變數出現時，會出現此維度 `opt.sell` 等於 `N`.
