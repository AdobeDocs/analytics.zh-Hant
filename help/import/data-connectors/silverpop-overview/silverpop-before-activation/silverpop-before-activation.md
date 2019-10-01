---
description: 在啟動此整合之前，請針對您部署的Adobe Analytics®和電子郵件軟體檢視下列項目。
seo-description: 在啟動此整合之前，請針對您部署的Adobe Analytics®和電子郵件軟體檢視下列項目。
seo-title: 啟動此整合之前
title: 啟動此整合之前
uuid: b911edc6-2265-48ed-9e3c-c79cc20dd9b2
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# 啟動此整合之前{#before-you-activate-this-integration}

在啟動此整合之前，請針對您部署的Adobe Analytics®和電子郵件軟體檢視下列項目。

如此可確保在啟動前已有適當的最佳實務或先決條件，進而產生最佳且成功的整合。

## Adobe Analytics{#adobe-analytics}

檢視與Adobe Analytics相關之此「資料連接器」整合的下列資訊：

* **** 報表套裝特定：請注意，此整合是報表套裝專用的。 在啟動整合之前，請確定您已選取所需的報表套裝。
* **** 可用和設定的Analytics變數：此整合需要5個自訂事件和2個自訂eVar，以及（可選）3個額外事件和3個額外eVar。 請參 [閱Analytics整合變數](../../silverpop-overview/silverpop-variables.md#concept-6c8a359719fd4794a42f5f6fb118f8b2)。

* **** 授權代表：請注意，啟用此項整合可能會使貴公司根據您與Adobe, Inc.的服務合約或您與Adobe信任的合作夥伴之一（視情況而定）的服務合約產生費用。 啟動此整合後，您即表示您是您公司的授權代表；因此，貴公司同意支付上述服務協定所載之費用（如有）。
* **** Data Warehouse™:此整合需要啟用「資料倉庫」才能產生再行銷區段。 如果您尚未啟用「資料倉庫」，請聯絡Adobe以取得詳細資訊。
* **** 收件者ID:整合需要我們擷取並儲存Analytics變數(eVar)中的「訪客ID」。 訪客ID（通常稱為「收件者ID」）是來自Silverpop系統之電子郵件地址的編碼或數值表示法。 此「收件者ID」與網站上的下游訪客行為（購物車放棄、購買等）相關聯這個功能被拉進Silverpop系統，並可用於再行銷目的。 在設定程式中，當精靈提示時，您必須識別eVar以用於此目的。
* **** 外部追蹤：如果您目前未遵循針對您傳送的每個電子郵件促銷活動啟用外部追蹤的最佳實務，您必須這麼做，以確保成功整合。 如需詳細資訊，請參閱下方的Silverpop區段。
* **** 隱私權規範：您應瞭解，透過啟用「收件者」或「訪客ID」追蹤，此功能可追蹤您網站訪客的個人識別資訊。 這涉及隱私權問題，需要貴組織實施適當的程式，例如向網站訪客提供通知並給予同意。

## Silverpop Data Connector整合{#silverpop-data-connector-integration}

檢視與Silverpop相關之此資料連接器整合的下列資訊：

* **** 有效的Silverpop帳戶：若要使用Data Connectors電子郵件整合，用戶端必須有啟用電子郵件的作用中Silverpop帳戶，以及作用中的使用者憑證。
* **請連絡您的Silverpop代表**。 此整合不會由Silverpop自動啟用。 您必須先連絡您的Silverpop代表，以啟動Silverpop設定，才能從Analytics匯入或匯出資料。

>[!NOTE]
>
>此整合僅適用於「參與」組織（而非「交易」）。

## 定價{#pricing}

此Data Connectors整合包括啟動前您需要考慮的價格考量。

### Adobe定價考量事項 {#section-2d1c79c895a5479bad8fdd97961ba6a3}

此整合可能會產生經常性和實施費用。 如需價格詳細資訊，請連絡您的Adobe客戶代表。

### 合作夥伴定價考慮事項 {#section-c6afad08c34b43e3a7a3637eea3328c3}

此整合可能會產生相關費用。 如需價格資訊，請連絡您的關係經理。