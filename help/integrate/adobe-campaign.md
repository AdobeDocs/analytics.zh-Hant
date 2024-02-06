---
description: 瞭解如何在Adobe Analytics中啟用Adobe Campaign Standard報告
title: 如何將Adobe Campaign Standard報表整合至Adobe Analytics？
feature: Campaign Integration
exl-id: 63bae5ee-f94d-43fa-87ce-6380236745d6
role: Admin
source-git-commit: d3d5b01fe17f88d07a748fac814d2161682837c2
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 67%

---


# Adobe Campaign Standard報告

如需如何設定整合的詳細資訊，請前往 [Adobe Campaign 文件](https://helpx.adobe.com/campaign/standard/integrating/using/about-campaign-analytics-integration.html)。

>[!IMPORTANT]
>本文適用於Adobe Campaign **標準** 僅限報告。 另請參閱 [此處](https://experienceleague.adobe.com/docs/analytics/integration/analytics-to-campaign-classic.html?lang=en) 新增Adobe Campaign **Classic** 報告。

Adobe Analytics與Adobe Campaign Standard之間的整合：

* 讓您從 Adobe Campaign Standard 共用您的 KPI (關鍵績效指標) 資料至 Adobe Analytics。
* 使用 Adobe Analytics 參數充實追蹤公式。
* 在&#x200B;**[!UICONTROL 「Analytics]** > **[!UICONTROL 報表]** > **[!UICONTROL Adobe Campaign」]**&#x200B;下方新增報表。
* 增加 5 個全新 Adobe Campaign 分類。
* 增加 9 個全新 Adobe Campaign 量度。
* 增加 6 個全新 Adobe Campaign 維度。
* 透過自動布建的資料來源，每15分鐘將資料同步至Analytics。

## 步驟 1.啟用Adobe Campaign Standard報告 {#section_C685EF10505045708A6536BB13F6CD58}

若要在Analytics中檢視Campaign Standard資料，必須先在「報表套裝管理器」中啟用「促銷活動報表」 。

1. 導覽至&#x200B;**[!UICONTROL 「Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]** > **`<select report suite>`** > **[!UICONTROL 編輯設定]** > **[!UICONTROL Adobe Campaign]** > **[!UICONTROL Adobe Campaign 報表」]**。
1. 按一下&#x200B;**[!UICONTROL 啟用 Campaign 報告功能]**。

   ![](assets/enable-campaign.png)

## 步驟 2.檢視 Adobe Campaign 報表 {#section_9C18A29F3CC54BD4AC5EA96417F17B33}

Adobe Campaign Standard 和 Adobe Analytics 之間的整合會在 **[!UICONTROL 「Analytics]** > **[!UICONTROL 報表」]**&#x200B;下新增報表

* **[!UICONTROL Adobe Campaign執行的傳送ID]**：顯示從Adobe Campaign匯入的、有關從Adobe Campaign傳送之電子郵件的資料。 |

## 步驟 3.使用 Adobe Campaign 分類 {#section_74A28AF3F4CA4091943789DE4D8B2B63}

**[!UICONTROL 「Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]** > **`<select report suite>`** > **[!UICONTROL 編輯設定]** > **[!UICONTROL Adobe Campaign]** > **[!UICONTROL Adobe Campaign 分類」]**

在您針對 Adobe Campaign 啟用報表套裝後，以下分類即可使用：

| 分類 | 說明 |
| --- | --- |
| [!UICONTROL 傳遞ID] | 您在Campaign中看到的內部傳遞名稱 |
| [!UICONTROL 傳遞標籤] | Campaign中的傳遞 — 個別傳遞/循環傳遞/交易傳遞 |
| [!UICONTROL 行銷活動 ID] | 您在Campaign中看到的內部行銷活動名稱 |
| [!UICONTROL 行銷活動標籤] | Adobe Campaign中的行銷活動 |
| [!UICONTROL 已執行的傳遞標籤] | 個別執行的傳遞清單 |

## Adobe Analytics中可用的Adobe Campaign Standard維度和量度 {#section_F33385C9660644AF84172EC39601469B}

以下&#x200B;**量度**&#x200B;可透過 Adobe Analytics 報表套裝中的 Campaign 使用：

* Adobe Campaign 已傳送
* Adobe Campaign 已打開
* Adobe Campaign 已點擊
* Adobe Campaign 已傳送
* Adobe Campaign 不重複打開
* Adobe Campaign 不重複點擊
* Adobe Campaign 取消訂閱
* Adobe Campaign 彈回數總計
* Adobe Campaign 執行的傳送 ID 例項

以下&#x200B;**維度**&#x200B;可透過 Adobe Analytics 報表套裝中的 Campaign 使用：

| 維度名稱 | 定義 |
| --- | --- |
| 行銷活動 ID | 在活動期間傳送的 KPI 之所有行銷活動的 ID |
| 行銷活動標籤 | 行銷活動 ID 標籤 |
| 傳送 ID | 在活動期間傳送的 KPI 之所有傳送 ID亦包括循環傳送和交易傳送的主傳送 ID。範例：已排程循環傳送 DM1，而 DM2、DM3、DM4 和 DM5 是該循環傳送的子傳送。「傳送 ID」會顯示所有傳送的結果，從 DM1 至 DM5 都會顯示。 |
| 傳送標籤 | 傳送 ID 標籤 |
| 執行的傳送 ID | 僅限已執行傳送的 ID。沒有循環/交易主傳送的 ID。範例：已排程循環傳送 DM1，而 DM2、DM3、DM4 和 DM5 是該循環傳送的子傳送。已執行傳送 ID 會顯示從 DM2 到 DM5，實際已執行的傳送之所有傳送結果。 |
| 已執行傳送標籤 | 已執行傳送 ID 標籤 |
