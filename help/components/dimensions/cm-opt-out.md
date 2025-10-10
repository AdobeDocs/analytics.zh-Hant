---
title: 同意管理選擇退出
description: 查看訪客選擇退出哪些隱私設定。
exl-id: 2bf4d22c-5b24-47fb-b489-49388fcca5b1
feature: Dimensions
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 93%

---

# 同意管理選擇退出

「同意管理選擇退出」[維度](overview.md)顯示訪客已明確選擇退出哪些隱私設定。 您可以使用此維度根據隱私設定篩選資料，或查看最常見的隱私選擇退出原因。

## 將資料填入此維度中

此維度會從以下[內容資料變數](/help/implement/vars/page-vars/contextdata.md)收集資料：

* `contextData.['cm.ssf']` 設定為 `1` 時。如果 `cm.ssf` 等於 `0` 或空白，此變數不會產生任何效用。
* `contextData.['opt.dmp']` 設定為 `N` 時。如果 `opt.dmp` 等於 `Y`，則會填入[同意管理選擇加入](cm-opt-in.md)維度。
* `contextData.['opt.sell']` 設定為 `N` 時。如果 `opt.sell` 等於`Y`，則會填入[同意管理選擇加入](cm-opt-in.md)維度。

您的組織會確定實施這些內容資料變數的邏輯。這類變數在其設定所在的點擊過後即不存在，因此您必須在每個頁面上設定每個內容資料變數。

## 維度項目

維度項目包括下列三個值：

* **`SSF`**：訪客選擇退出[伺服器端轉送功能](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)。此維度項目在內容資料變數 `cm.ssf` 等於 `1` 時出現。如需詳細資訊，請參閱 Audience Manager 使用手冊中的[資料隱私概觀](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html?lang=zh-Hant)。點擊不會轉送到 Adobe Audience Manager。
* **`DMP`**：訪客選擇退出分享至資料管理平台。此維度項目在內容資料變數 `opt.dmp` 等於 `N` 時出現。類似於 `SSF`，點擊不會轉送到 Adobe Audience Manager。
* **`SELL`**：訪客選擇退出將資料分享或銷售至第三方。此維度項目在內容資料變數 `opt.sell` 等於 `N` 時出現。
