---
description: 設定您要條件觸發的動作。
keywords: Dynamic Tag Management;規則;建立規則;新規則;JavaScript/第三方標籤;設定條件的動作;新增指令檔;非循序 JavaScript;循序 JavaScript;非循序 HTML
seo-description: 設定您要條件觸發的動作。
seo-title: 設定條件要觸發的動作
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: 設定條件要觸發的動作
uuid: 2e892f0b-7261-41ee-b849-6e3054a38de0
translation-type: ht
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# 設定條件要觸發的動作

設定您要條件觸發的動作。

設定條件之後，您必須設定要條件觸發的動作。這些動作包括 [!DNL Analytics] 事件、第三方標籤及自訂指令檔。此範例說明如何設定指令檔或第三方標籤。

除了已整合的工具 (如 [!DNL Adobe Analytics] 和 Google Analytics)，動態標籤管理還可以在選取頁面或特定藍本中，觸發任何類型的 JavaScript 或將 HTML 插入網站。

每個規則可依需要觸發任意數目的指令檔或 HTML 插入。

>[!NOTE]
>
>因為 DTM 可讓您將自訂程式碼插入至您的頁面，請注意不要產生跨網站指令檔 (XSS) 弱點 (如需詳細資訊，請參閱 [OWASP 的指南](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)))。在指令檔內使用資料元素需要特別注意。一律假設資料元素值可能來自未受信任的來源。

**設定條件要觸發的動作**

1. 按一下 **[!UICONTROL JavaScript / 第三方標籤]**，以將指令檔新增至規則。

   ![](assets/scripts-actions.png)

1. 按一下&#x200B;**[!UICONTROL 新增指令檔]**。

   ![](assets/scripts-actions2.png)

1. 為指令檔命名。
1. 指定您要如何觸發指令檔，並將所需內容貼到文字區域中。![](assets/scripts-actions3.png)

1. 按一下&#x200B;**[!UICONTROL 儲存程式碼]**，如此便會將指令檔新增至規則的佇列中。![](assets/scripts-actions4.png)

