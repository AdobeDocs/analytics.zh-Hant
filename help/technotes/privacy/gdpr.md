---
description: 本文件說明您需要在 Adobe Analytics 中執行哪些操作，以支援資料主體的 GDPR 存取和刪除權限。
title: Adobe Analytics 和 GDPR
feature: Data Governance
role: Admin
exl-id: 4cb19f63-119f-4853-84bf-5c1e8f9af9f0
TQID: https://experienceleague.adobe.com/G-3emGJR0FMicoTI8WUlWdM3SSoWjGb7sr6lxqceBdg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 478
ht-degree: 64%

---

# Adobe Analytics 和 GDPR

本文件說明您需要在 Adobe Analytics 中執行哪些操作，以支援資料主體的 GDPR 存取和刪除權限。

>[!IMPORTANT]
>
>本文件的內容不是法律建議，且用意並非取代法律建議。 請諮詢貴公司的法律部門，以獲取有關 GDPR 的建議。

歐盟通用資料保護規範 (GDPR) 已於 2018 年 5 月 25 日生效。 如需有關 Adobe 回應以及這對於您身為 Adobe 客戶所代表之意義的詳細資訊，請參閱 [GDPR 和您的業務](https://www.adobe.com/tw/privacy/general-data-protection-regulation.html)。

當 Adobe 向企業提供軟體和服務時， Adobe 對於其收到和儲存的任何個人資料，會代表客戶扮演資料處理者的角色，做為提供服務的一部分。 身為資料處理者，Adobe 會根據貴公司的權限和指示 (例如依照您與 Adobe 的合約中達成的協議) 處理個人資料。

身為資料控管方，您可以決定要由 Adobe 代表您處理和儲存哪些個人資料。 如果您使用Adobe CX Enterprise解決方案，Adobe可能會根據您使用的解決方案，以及您選擇傳送至Adobe CX Enterprise帳戶的資訊，為您託管個人資料。 如需範例清單，請參閱[Adobe CX Enterprise隱私權。](https://www.adobe.com/tw/privacy/marketing-cloud.html#collect)

![](assets/privacy_ready.png)

## Adobe 如何處理 GDPR 資料

Adobe CX Enterprise提供整合式解決方案，可連線您品牌的資料控管基礎架構，以及用來建立和管理消費者體驗的Adobe工具。 Adobe CX Enterprise的資料控管功能可將資料控管原則與資料使用方式直接連結。

請熟悉[Adobe Analytics如何處理GDPR](https://www.adobe.com/tw/data-analytics-cloud/analytics/general-data-protection-regulation.html)，瞭解GDPR整備步驟，以及如何與Adobe CX Enterprise GDPR API整合。

## GDPR 整備與您的 Adobe Analytics 資料

Adobe 瞭解您最熟悉報表套裝中的自訂資料，我們讓您能夠定義資料控管設定和偏好設定。

為此，Adobe Analytics 提供資料控管使用者介面，可讓您以資料控管者的身分，在 Analytics 報表套裝上設定[隱私標籤](/help/admin/tools/privacy-labeling/labels.md#data-governance-labels)，並在這些報表套裝中設定所有維度和量度。 您可以識別資料集中包含直接可識別資料或間接可識別資料的欄，以便提交存取和刪除請求以處理該資料。 對於每個請求，Analytics資料控管使用者介面中定義的標籤將接受對應於該請求的特定識別碼的處理。

請參閱[標籤報告套裝資料](/help/admin/tools/privacy-labeling/labeling-overview.md)，以了解如何設定標籤的更多資訊。
