---
description: 設定您要條件觸發的動作。
keywords: 動態標籤管理；規則；建立規則；新規則；javascript/第三方標籤；設定條件的動作；新增指令碼；非循序javascript；循序javascript；non-seature html
seo-description: 設定您要條件觸發的動作。
seo-title: 設定條件要觸發的動作
solution: Marketing Cloud、Analytics、Target、動態標籤管理
title: 設定條件要觸發的動作
uuid: 2e892f0b-7261-41ee-b849-6e3054 a38 de0
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 設定條件要觸發的動作

設定您要條件觸發的動作。

設定條件之後，您必須設定要條件觸發的動作。這些動作包括 [!DNL Analytics] 事件、第三方標籤及自訂指令檔。此範例說明如何設定指令檔或第三方標籤。

除了已整合的工具 (如 [!DNL Adobe Analytics] 和 Google Analytics)，動態標籤管理還可以在選取頁面或特定藍本中，觸發任何類型的 JavaScript 或將 HTML 插入網站。

每個規則可依需要觸發任意數目的指令檔或 HTML 插入。

>[!NOTE]
>
>Because DTM allows you to inject custom code into your page, please take care not to create cross-site scripting (XSS) vulnerabilities (see [OWASP’s guide](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)) for more info). 在指令檔內使用資料元素需要特別注意。一律假設資料元素值可能來自未受信任的來源。

**設定條件要觸發的動作**

1. Click **[!UICONTROL JavaScript / Third Party Tags]** to add a new script to your rule.

   ![](assets/scripts-actions.png)

1. Click **[!UICONTROL Add New Script]**.

   ![](assets/scripts-actions2.png)

1. 為指令檔命名。
1. Specify how you want the script to trigger, and paste the desired content into the text area. ![](assets/scripts-actions3.png)

1. Click **[!UICONTROL Save Code]**, and the script will be added to the queue for the rule. ![](assets/scripts-actions4.png)

