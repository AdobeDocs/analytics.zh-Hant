---
description: 使用動態標籤管理建立用於部署的 Adobe Analytics 工具。此程序說明手動 (舊版) 實作方式。
keywords: 動態標籤管理
seo-description: 使用動態標籤管理建立用於部署的 Adobe Analytics 工具。此程序說明手動 (舊版) 實作方式。
seo-title: 手動實作 Adobe Analytics (舊版)
solution: Marketing Cloud、Analytics、Target、動態標籤管理
title: 手動實作 Adobe Analytics (舊版)
uuid: d ad2035-393d-4a77-81f6-e749 ee717 c09
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# 手動實作 Adobe Analytics (舊版)

Create an Adobe Analytics tool for deployment using [!UICONTROL Dynamic Tag Management]. 此程序說明手動 (舊版) 實作方式。

如需自動實作管理的更多資訊，請參閱 [新增 Adobe Analytics 工具](../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8).

If you want to change a manual configuration to automatic, edit a tool and click **[!UICONTROL Enable Automatic Configuration]**.

1. 下載 Analytics 測量代碼:
   1. In Analytics, click **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]**.
   1. Click **[!UICONTROL JavaScript (new)]** to download the code locally.
1. In [!UICONTROL Dynamic Tag Management], [create a web property](../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123).

   ![](assets/dtm-property.png)

   建立 Web 屬性之後，您便可在[!UICONTROL 「控制面板」]的[!UICONTROL 「Web 屬性」]索引標籤上加以編輯。不需要啟動 Web 屬性實施流量分類。

1. 將「 Analytics」工具新增至屬性:
   1. On the **[!UICONTROL Web Properties]** tab, click the property.
   1. On the **[!UICONTROL Overview]** tab, click **[!UICONTROL Add a Tool]**.
   1. From the **[!UICONTROL Tool Type]** menu, select **[!UICONTROL Adobe Analytics]**.

      ![](assets/dtm-add-analytics-tool.png)

   1. 設定下列欄位:

      | 元素 | 說明 |
      |---|---|
      | 工具類型 | Experience Cloud 解決方案，例如 Analytics、Target、Social 等。 |
      | 工具名稱 | 此工具的名稱。此名稱會顯示[!UICONTROL 「概述」]索引標籤的[!UICONTROL 「已安裝工具」]下。 |
      | 生產帳戶 ID | 進行資料收集時，您要使用之生產帳戶的代表數字。動態標籤管理會自動在生產與測試環境中安裝正確帳戶。 |
      | 測試帳戶 ID | 在開發或測試環境中使用的數字。測試帳戶可讓您的測試資料與生產資料彼此分離。 |

1. Click **[!UICONTROL Create Tool]**.

   已安裝的工具便會顯示在[!UICONTROL 「概述」]索引標籤上。

1. To configure the code, click **[!UICONTROL Settings]** ![](assets/settings_gear.png).

   至少按一下&#x200B;**[!UICONTROL 「Cookies」]，然後設定您的追蹤伺服器和 SSL 追蹤伺服器。**

1. Click **[!UICONTROL General]** and [insert the core AppMeasurement code](../../implement/c-implement-with-dtm/c-aa-tool/t-appmeasurement-code.md#task_068D72664B2743359A64ADB8692D3658).
1. Define a [page load rule](../../implement/c-implement-with-dtm/c-rules/t-rules-create.md#task_B7FB5ED415AF430C952265AC2835C0DB) to collect [!DNL Analytics]data.

   您現在可以開始定義規則以收集分析資料。您可能需要先定義幾個資料元素。有了資料元素，您便可擷取頁面中的資料，以便用來設定規則。若要開始，您可以定義一個不含任何條件的頁面載入規則，以便收集每個頁面上的 [!DNL Analytics] 資料。
1. [在「內嵌」索引標籤上新增頁首與頁尾代碼](../../implement/c-implement-with-dtm/c-headers-footers/t-header-footer-code.md#task_43C8DD699A514638B0620775C06423E5)。

   在測試環境中，您可以保留預設的 Amazon 代管選項。在首度發行到生產環境之前，您可以視需要變更此選項。
1. (Optional) Click **[!UICONTROL Settings]** ![](assets/settings_gear.png) on the Options tab, and configure the Adobe Analytics code.

   >[!NOTE]
   >
   >The settings on the [!UICONTROL Adobe Analytics] page (General, Cookies, and so on) override settings in your `s_code`. 如果您的 `s_code` 中已有這些設定存在，則無需在此處重申。

