---
description: 在啟用這項整合之前，請針對您部署的 Adobe Analytics® 和您的電子郵件軟體檢閱下列項目。
title: 啟動這項整合的事前準備
uuid: b911edc6-2265-48ed-9e3c-c79cc20dd9b2
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 啟動這項整合的事前準備{#before-you-activate-this-integration}

在啟用這項整合之前，請針對您部署的 Adobe Analytics® 和您的電子郵件軟體檢閱下列項目。

如此可確保在啟用之前已有適當的最佳實務或必要條件，進而產生最佳且成功的整合。

## Adobe Analytics{#adobe-analytics}

檢閱與 Adobe Analytics 相關的下列 Data Connectors 整合資訊：

* **報表套裝特定：**&#x200B;請注意，這項整合是報表套裝專用的。在啟用整合之前，請確定您已選取所需的報表套裝。
* **可用和已設定的 Analytics 變數**：此整合需要 5 個自訂事件和 2 個自訂 eVar，以及選用的其他 3 個事件和其他 3 個 eVar。請參閱 [Analytics 整合變數](/help/import/data-connectors/silverpop-overview/silverpop-variables.md)。

* **授權代表：**&#x200B;請注意，啟用此項整合可能會使貴公司根據您與 Adobe, Inc. 的服務合約或您與 Adobe 信任合作夥伴之一 (如適用) 的服務合約產生費用。啟用這項整合，即表示您是貴公司的授權代表；因此，貴公司同意支付上述服務合約所載之費用 (若有的話)。
* **Data Warehouse™：**&#x200B;這項整合需要啟用 Data Warehouse，才能產生再行銷區段。如果您尚未啟用 Data Warehouse，請聯絡 Adobe 瞭解詳情。
* **收件者 ID：**&#x200B;整合需要我們在 Analytics 變數 (eVar) 中擷取並儲存「訪客 ID」。訪客 ID (通常稱為「收件者 ID」) 是來自 Silverpop 系統之電子郵件地址的編碼或數值表示法。此「收件者 ID」與網站上的下游訪客行為 (購物車放棄、購買等等) 相關聯此項目會被拉入 Silverpop 系統，且可用於再行銷用途。作為設定程序的一部分，當精靈提示時，您必須識別用於此目的的 eVar 。
* **外部追蹤：**&#x200B;如果您目前未遵循針對您傳送之每個電子郵件促銷活動啟用外部追蹤的最佳實務，您必須這麼做以確保成功整合。如需詳細資訊，請參閱下文的 Silverpop 一節。
* **隱私權法規遵循：**&#x200B;您應瞭解，一旦啟用收件者或訪客 ID 追蹤功能，此功能便可追蹤您網站訪客的個人識別資訊。這隱含隱私權問題，需要您的組織實施適當的程序，例如向您的網站訪客提供通知並授予同意。

## Silverpop Data Connector 整合{#silverpop-data-connector-integration}

檢閱下列資訊，瞭解這個與 Silverpop 相關的 Data Connectors 整合：

* **有效的 Silverpop 帳戶：**&#x200B;若要使用 Data Connectors 電子郵件整合，客戶必須有已啟用電子郵件的有效 Silverpop 帳戶，以及有效的使用者憑證。
* **請聯絡您的 Silverpop 代表**。Silverpop 不會自動啟用此整合。您必須先聯絡 Silverpop 代表以起始 Silverpop 設定，才能從 Analytics 匯入或匯出資料。

> [!NOTE] 此整合僅適用於 Engage 組織 (Transact 組織不適用)。

## 定價{#pricing}

此 Data Connectors 整合包括啟動前您需思考的定價考量事項。

### Adobe 定價考量事項 {#section-2d1c79c895a5479bad8fdd97961ba6a3}

此整合可能會產生週期性和實施的相關費用。如需價格方面的詳細資訊，請聯絡您的 Adobe 客戶代表。

### 合作夥伴定價考量事項 {#section-c6afad08c34b43e3a7a3637eea3328c3}

此整合可能會產生相關費用。如需定價資訊，請聯絡您的關係經理。
