---
description: 如果您使用 Akamai 託管，請自主控台測試取消發佈規則。
keywords: Dynamic Tag Management;rule;switcher plug-in;akamai;test akamai;unpublished rules;test unpublished rules;debug rule
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: 測試 Akamai 託管未發佈的規則
uuid: 979e3d74-8d96-47d0-b581-cf5371248434
translation-type: ht
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

---


# 測試 Akamai 託管未發佈的規則

如果您使用 Akamai 託管，請自主控台測試取消發佈規則。

Switcher 外掛程式往往是進行測試的最簡單方式。如需詳細資訊，請參閱 Dynamic Tag Management 產品文件中的 [Search Discovery 外掛程式](https://marketing.adobe.com/resources/help/zh_TW/dtm/search_discovery_plugins.html)。

下列步驟說明如何在不使用 Switcher 外掛程式的情況下進行測試：

1. 存取網站上的 Web 主控台，並鍵入 `localStorage.setItem('sdsat_stagingLibrary', true)`。
1. 按 **[!UICONTROL Enter]** 鍵。
1. 輸入 `_satellite.setDebug(true)`，然後按 **[!UICONTROL Enter]** 鍵。
1. 重新整理頁面。

   此動作會載入您的測試程式庫並設定除錯工具，方便您查看頁面上所有可用之規則 (已發佈/未發佈) 引發的詳細資料。
1. 完成後，請執行 `localStorage.setItem('sdsat_stagingLibrary', false)`，然後按 **[!UICONTROL Enter]** 鍵。

   步驟結果
