---
description: 如果您使用 Akamai 託管，請自主控台測試取消發佈規則。
keywords: 動態標籤管理；rule;switcher plugin;akamai;test akamai;unpublished rules;test unpublished rules;debug rule
seo-description: 如果您使用 Akamai 託管，請自主控台測試取消發佈規則。
seo-title: 為 Akamai 主機測試未發佈的規則
solution: Experience Cloud,Analytics,Target，動態標籤管理
title: 為 Akamai 主機測試未發佈的規則
uuid: 979e3d74-8d96-47d0-b581-cf5371248434
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# 為 Akamai 主機測試未發佈的規則

如果您使用 Akamai 託管，請自主控台測試取消發佈規則。

Switcher 外掛程式往往是進行測試的最簡單方式。如需詳細資訊，請參閱動態標籤管理產品文件中的 [Search Discovery 外掛程式](https://marketing.adobe.com/resources/help/en_US/dtm/search_discovery_plugins.html)。

下列步驟會說明，如何在不使用 Switcher 外掛程式的情況下進行測試:

1. 存取網站上的 Web 主控台，並鍵入 `localStorage.setItem('sdsat_stagingLibrary', true)`.
1. Press **[!UICONTROL Enter]**.
1. 鍵 `_satellite.setDebug(true)`入，然後按 **[!UICONTROL Enter]**。
1. 重新整理頁面。

   此動作會載入您的測試程式庫並設定除錯程式，方便您查看頁面上所有可用之規則 (已發佈/未發佈) 觸發的詳細資料。
1. 完成後，運行 `localStorage.setItem('sdsat_stagingLibrary', false)`，然後按 **[!UICONTROL Enter]**。

   步驟結果