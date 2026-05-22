---
description: 了解如何啟用 Adobe Analytics 中的 Adobe Campaign Standard 報告
title: 如何將 Adobe Campaign Standard 報告整合至 Adobe Analytics？
feature: Admin Tools
exl-id: 63bae5ee-f94d-43fa-87ce-6380236745d6
role: Admin
autotag-review: '2026-05-22T12:17:50.968Z'
TQID: 'https://experienceleague.adobe.com/r-zrWBcHhMkxptxKlfZ0Xaw-UsYc9QIIqQgSbyTertA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: b13acd70-7a51-4028-8c44-5f3b1bbe3ad4
  - id: fe0a7292-80bc-407a-b456-64170267d1cc
  - id: a9364d69-0c51-44bf-8b5f-6d99c04493b8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 520
ht-degree: 65%

---

# Adobe Campaign Standard 報告

如需如何設定此整合的詳細資訊，請前往 [Adobe Campaign 文件](https://helpx.adobe.com/tw/campaign/standard/integrating/using/about-campaign-analytics-integration.html)。

>[!IMPORTANT]
>本文僅適用於 Adobe Campaign **Standard** 報告。 請參閱[此處](/help/integrate/analytics-to-campaign-classic.md)了解如何新增 Adobe Campaign **Classic** 報告。

這個 Adobe Analytics 與 Adobe Campaign Standard 之間的整合：

* 可讓您將KPI （關鍵績效指標）資料從Adobe Campaign Standard分享至Adobe Analytics。
* 使用Adobe Analytics引數豐富追蹤公式。
* 在&#x200B;**[!UICONTROL 「Analytics]** > **[!UICONTROL 報表]** > **[!UICONTROL Adobe Campaign」]**&#x200B;下方新增報表。
* 新增 5 個 Adobe Campaign 分類。
* 新增 9 個 Adobe Campaign 量度。
* 新增 6 個 Adobe Campaign 維度。
* 透過自動佈建的資料來源，每 15 分鐘就將資料同步到 Analytics。

## 步驟 1： 啟用 Adobe Campaign Standard 報告 {#section_C685EF10505045708A6536BB13F6CD58}

若要在 Analytics 中檢視 Campaign Standard 資料，您必須先在報告套裝管理器中啟用 Campaign 報告。

1. 導覽至&#x200B;**[!UICONTROL 「Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]** > **`<select report suite>`** > **[!UICONTROL 編輯設定]** > **[!UICONTROL Adobe Campaign]** > **[!UICONTROL Adobe Campaign 報表」]**。
1. 按一下&#x200B;**[!UICONTROL 啟用 Campaign 報告功能]**。

   ![](assets/enable-campaign.png)

## 步驟 2. 檢視 Adobe Campaign 報表 {#section_9C18A29F3CC54BD4AC5EA96417F17B33}

Adobe Campaign Standard 和 Adobe Analytics 之間的整合，會在「**[!UICONTROL Analytics]** > **[!UICONTROL 報告]**」下方新增以下報告

* **[!UICONTROL Adobe Campaign執行的傳遞ID]**：顯示從Adobe Campaign匯入的資料，其中有關於從Adobe Campaign傳送的電子郵件。 |

## 步驟 3： 使用 Adobe Campaign 分類 {#section_74A28AF3F4CA4091943789DE4D8B2B63}

**[!UICONTROL 「Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]** > **`<select report suite>`** > **[!UICONTROL 編輯設定]** > **[!UICONTROL Adobe Campaign]** > **[!UICONTROL Adobe Campaign 分類」]**

在您針對 Adobe Campaign 啟用報表套裝後，以下分類即可使用：

| 分類 | 說明 |
| --- | --- |
| [!UICONTROL 傳送 ID] | 您在 Campaign 中看到的「內部傳送名稱」 |
| [!UICONTROL 傳送標籤] | Campaign 提供的傳送方式：個別傳送/定期傳送/交易傳送 |
| [!UICONTROL 行銷活動 ID] | 您在 Campaign 中看到的「內部行銷活動名稱」 |
| [!UICONTROL 行銷活動標籤] | Adobe Campaign 中的行銷活動 |
| [!UICONTROL 已執行傳送標籤] | 個別已執行傳送的清單 |

## Adobe Analytics 中可用的 Adobe Campaign Standard 維度和量度 {#section_F33385C9660644AF84172EC39601469B}

以下&#x200B;**量度**&#x200B;可透過 Adobe Analytics 報表套裝中的 Campaign 使用：

* Adobe Campaign已傳送
* Adobe Campaign已開啟
* Adobe Campaign已點按
* Adobe Campaign已傳遞
* Adobe Campaign不重複開啟
* Adobe Campaign不重複點按
* Adobe Campaign已取消訂閱
* Adobe Campaign總跳出數
* Adobe Campaign執行的傳送ID例項

以下&#x200B;**維度**&#x200B;可透過 Adobe Analytics 報表套裝中的 Campaign 使用：

| Dimension名稱 | 定義 |
| --- | --- |
| 行銷活動 ID | 持續期間已傳送KPI的所有行銷活動ID |
| 行銷活動標籤 | 行銷活動ID的標籤 |
| 傳遞ID | 持續期間已傳送KPI的所有傳遞的ID。 也包括重複傳遞和交易傳遞的主要傳遞ID。 範例：已排程循環傳送 DM1，而 DM2、DM3、DM4 和 DM5 是該循環傳送的子傳送。  傳遞ID會顯示所有傳遞的結果，從DM1到DM5。 |
| 傳遞標籤 | 傳遞ID的標籤 |
| 執行的傳送 ID | 僅已執行傳遞的ID。 沒有循環/交易式主要傳遞的ID。 範例：已排程循環傳送 DM1，而 DM2、DM3、DM4 和 DM5 是該循環傳送的子傳送。 已執行的傳送ID會顯示從DM2到DM5的所有傳送（實際執行的傳送）的結果。 |
| 已執行的傳遞標籤 | 已執行傳遞ID的標籤 |
